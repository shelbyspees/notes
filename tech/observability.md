---
aliases: []
---

## what is observability?

**Observability** ("o11y" for short) is a trait of your system.
How well can you understand the internal health of your system just from its external outputs?
The better you can understand your system from the data it gives you, the more observable it is.

Beyond whatever your system outputs for its main purpose, it probably also spits out data to tell you about its health.
The word for this is **telemetry**, which comes from the Greek tele- ("remote") and -metry ("measurement").
You're measuring something inside the system and then reading those measurements somewhere else.
The process of adding code or tooling to your system to get telemetry data is called **instrumentation**.

Most importantly, good observability comes from how you interact with your system's telemetry data.
This means there are two sides to improving observability:

- improving the data
- improving the interactions

The first comes from better instrumentation.
The second comes from tooling designed to let you explore that data in novel ways, asking new questions that you didn't think of when you originally wrote the code.

## resources
[Observability 101: Terminology and Concepts](https://www.honeycomb.io/blog/observability-101-terminology-and-concepts/) by Shelby Spees (me)

[Observability and your business](https://leaddev.com/monitoring-observability/observability-and-your-business) by Liz Fong-Jones

[Observability - A 3-Year Retrospective](https://thenewstack.io/observability-a-3-year-retrospective/)

[Why Observability Needs to Stay Weird](https://thenewstack.io/why-observability-needs-to-stay-weird/)

[How the '3 Pillars of Observability' Miss the Big Picture](https://thenewstack.io/how-the-3-pillars-of-observability-miss-the-big-picture/)

[DevOps measurement: Monitoring and observability | Google Cloud](https://cloud.google.com/solutions/devops/devops-measurement-monitoring-and-observability)

note this quote from the Google docs page:

> **Monitoring** is tooling or a technical solution that allows teams to watch and understand the state of their systems. Monitoring is based on gathering predefined sets of metrics or logs.
> **Observability is tooling or a technical solution that allows teams to actively debug their system. Observability is based on exploring properties and patterns not defined in advance.**

[Journey into Observability: Reading material](https://mads-hartmann.com/sre/2019/08/04/journey-into-observability-reading-material.html) by Mads Hartmann

[Monitoring and Observability](https://copyconstruct.medium.com/monitoring-and-observability-8417d1952e1c) by Cindy Sridharan

### whitepapers

The following Honeycomb whitepapers are gated by a form to fill out in order to download them. You can opt out of Honeycomb's marketing emails at any time.

- [Honeycomb whitepaper: Achieving Observability](https://www.honeycomb.io/guide-achieving-observability/)
- [Honeycomb whitepaper: Observability for Developers](https://www.honeycomb.io/guide-observability-for-developers/)

## notes: about observability



<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Periodic reminder that &quot;AIOps&quot; really just means &quot;bayesian statistical analysis of your time series data in a loop.&quot;</p>&mdash; Alex Hidalgo (@ahidalgosre) <a href="https://twitter.com/ahidalgosre/status/1368040546380505090?ref_src=twsrc%5Etfw">March 6, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

