---
aliases: [instrumentation ergonomics]
---

## developer experience

instrumenting for observability shouldn't be significantly more work than adding a print statement.

I encourage people to move away from agents that gather telemetry from outside the application and toward tracing code that captures the actual state at runtime. (see also: [why instrument your code?](https://www.notion.so/why-instrument-your-code-30e8a97a2afd49d7a0bff8d88d578cf3))

improving the developer experience for instrumenting code helps more teams cross that threshold and get more insight into their systems. it encourages production ownership that sets devs up for success.

## instrumentation libraries

lean on shared conventions to make instrumentation a part of your workflow.

### SDKs

these are external packages that you import into your code, making an API available for you to add instrumentation to your app.

(code example)

you can import the SDK into each file separately, but sometimes it makes more sense to wrap the file in an instrumentation layer.

### app-level instrumentation layer

you can create an instrumentation module in your app's lib/ directory to handle not only importing and configuring your desired SDK, but also managing a global namespace for custom field names referenced frequently across the application. assigning field names to variables in a single place and then referencing them elsewhere saves developers from dealing with hard-coded strings, and it allows the team to agree on naming conventions.

(code example)

note that when using observability tooling that employs a columnar backend, nothing is stopping you from adding whatever fields you need ad-hoc throughout the codebase. the purpose of the centralized schema isn't for gatekeeping instrumentation, it's to help teams stay organized and ensure their fields are queryable. there's very little cost in adding ad-hoc fields, and inconsistent field names will generally be caught at the PR review stage.

(code example with temporary field, e.g. for A/B testing)

a central library can also help protect teams from accidentally creating columns with dynamically-generated values for the name field. many languages support grabbing the name of the current class or method, you can do this automatically in a helper function in your library

(how? code example)

### organization-level

for organizations requiring consistent instrumentation conventions across many services, it often makes sense to manage custom instrumentation in an org-wide library that wraps your desired SDK—basically hosting your own custom distro. there are a number of tradeoffs to this approach.

benefits:

- telemetry is queryable by anyone in the org, because you're all following the same pattern. this is a boon for support teams and incident responders
- for orgs with strict dependency management needs, the centralized library can insulate teams from the risks of updating dependency versions, as long as the library's maintainers have bandwidth to support progressive upgrades

drawbacks:

- maintenance burden of hosting and updating the distro
- entropy and inertia
- teams using the distro but not following conventions in their own custom instrumentation
- teams avoiding the distro altogether

### framework-level

while OpenTelemetry offers auto-instrumentation for number of popular frameworks, framework maintainers can absorb some of that maintenance burden by building instrumentation in at the framework level that's compatible with OpenTelemetry's tracing spec.

---

## resources

[Domain-Oriented Observability](https://martinfowler.com/articles/domain-oriented-observability.html)