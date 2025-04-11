---
title: "Drawback of Agent Collector Deployment Pattern"
weight: 18
description: "Identifying a significant drawback of the agent deployment pattern for the OpenTelemetry Collector, particularly regarding scalability."
---

**Question:**
What is a significant drawback of the agent collector deployment pattern in OpenTelemetry?

**Answer:**
It has limited scalability and can become inflexible under increased load.

**Explanation:**
In the agent pattern, a Collector instance runs alongside each application instance (e.g., as a sidecar in Kubernetes or directly on a host). While this minimizes network hops for initial data collection, managing and scaling a large number of individual agents can become complex. Each agent consumes resources, requires individual configuration (though this can be centralized), and the overall processing capacity is tied to the number of application instances. Centralized processing or complex aggregation is often better handled by a gateway/collector tier, which the agent pattern alone doesn't provide robustly, leading to potential inflexibility and scalability challenges under high load compared to a tiered approach.

**Reference:**
[Collector Deployment Modes - Agent](https://opentelemetry.io/docs/collector/deployment/#agent)
