Four indicators of high-performing teams.

---

The DevOps Research Institute has distilled four factors that contribute to the success of high-performing teams. Here I want to go into how you can improve each one.

## lead time for changes

- how soon is your commit in prod?
- 24hr turnaround for PR review (usually less)
- fast builds

## deployment frequency

- hours 👍🏼 vs. weeks/months 👎🏼
- hourly build train
- no Change Approval Boards, no gatekeeping
    - use feature flags, canary deploys to reduce blast radius and build confidence
- deploy on merge (or on a cron)

## time to restore service

- minutes 👍🏼 vs. hours 🤷‍♀ vs. days 👎🏼
- restore service first, investigate later (with good observability!)
- make it easy to rollback to previous build/version
- fast builds, in case you need to revert/push a fix

## change failure rate

- what % of changes cause a user-facing issue?
- small PRs reduce blast radius, facilitate thorough review
- rigorous CI testing
- every PR gets code review
- feature flags, canary deploys help you catch prod-only issues before it hits mainstream traffic

In the talk [Fast & Simple](https://konghq.com/videos/fast-and-simple-observing-code-and-infra-deployments-at-honeycomb/), Liz and I describe about how the Honeycomb engineering team created a virtuous cycle, shortening lead time first and then building on that to improve the other metrics.