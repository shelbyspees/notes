---
aliases: [service level objectives (SLOs)]
---

see also:
- [web-services](tech/web-services.md)
- [production-excellence](tech/production-excellence.md)

## what are SLOs?

Service Level Objectives (SLOs) are a way of measuring whether a particular service is doing its job by capturing data that represents the end user experience. SLOs were first introduced to the tech community by Google's [Site Reliability Engineering (SRE) book](https://sre.google/sre-book/table-of-contents/).

Honeycomb Principal Developer Advocate Liz Fong-Jones explains the why and how of SLOs in her talk, *Cultivating Production Excellence*:

[https://youtu.be/Nl9Jn-7n2Eg](https://youtu.be/Nl9Jn-7n2Eg)

## what makes up an SLO

Two signals that often best reflect user experience are latency (how slow a response is) and error rate. An example SLO for latency might be something like:

> Over a 30-day rolling window, 99% of checkout confirmations should return `200 OK` in less than 500ms.

Let's break this down into parts:

- time window: last 30 days
- target percentage: 99%
- type of event: checkout confirmations
- success criteria:
    - `200 OK`
    - <500ms

From here we do a few types of calculations on our actual traffic. First, we filter down to only the relevant events: checkout confirmations. Then, for each checkout confirmation, we determine whether it meets or fails the success criteria: did it return a `200 OK` within 500ms? From there, we calculate the percentage: how many of our checkout confirmations over the past 30 days met our threshold for success?

Let's say that over the past 30 days we had 5 million checkout confirmations, and 4,981,500 of them met the threshold: both successful and fast. That gives us 99.63%, which is actually pretty far above our target percentage of 99%.

## error budgets

With an SLO target of 99% for 5 million events, we're allowed to have 50,000 events not meet the threshold during our window. This is our **error budget**.

In the above example, we had 18,500 bad events over the 30-day window, and with our error budget we would have been okay having 31,500 more bad events.

TODO

## how to decide on a target percentage

TODO

## minute-based SLOs vs. event-based SLOs


use your [observability](tech/observability.md) data to measure system reliability with event-based SLOs:
- generate structured event data
- use that data to calculate and monitor important values:
    --> uptime
    --> error rate
    --> latency

# resources

You can read the Service Level Objectives chapter of the Site Reliability Engineering book in full here:

[Google - Site Reliability Engineering](https://sre.google/sre-book/service-level-objectives/)