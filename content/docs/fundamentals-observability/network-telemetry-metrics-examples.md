---
title: "Typical Network Telemetry Metrics"
weight: 19
description: "Lists examples of metrics commonly associated with network telemetry data, including device resource usage."
---

This note identifies common metrics used for monitoring network infrastructure health and performance, drawing from network telemetry data.

## Examples of Network Telemetry Metrics

**Question:** Which of the following metrics is typically associated with network telemetry data?

**Answer Principle:** Metrics related to network device performance, such as **CPU and memory utilization of routers** (and other network devices like switches), are key components of network telemetry.

**Explanation:**
Network telemetry involves collecting data related to the performance, health, and traffic flow of network infrastructure. While traffic metrics (bytes, packets, errors) are common, monitoring the health of the network devices themselves is also crucial.

Metrics like **CPU and memory utilization of routers** and switches fall under this category. Monitoring these resource utilization metrics provides insights into:

- **Device Capacity:** Understanding if network devices are approaching their processing or memory limits.
- **Infrastructure Health:** Detecting potential hardware issues or overloaded devices.
- **Performance Bottlenecks:** Identifying if network device performance is impacting overall network throughput or latency.

Collecting and analyzing these device-specific metrics allows network administrators and observability teams to maintain optimal network performance, proactively address resource constraints, and troubleshoot issues related to the network hardware itself.

While OpenTelemetry's semantic conventions also define network traffic metrics (like `system.network.io`), system-level metrics (`system.cpu.utilization`, `system.memory.usage`) can be applied to network devices when monitoring their internal state.

**Reference:**

- OpenTelemetry Documentation: [System Metrics](https://opentelemetry.io/docs/specs/semconv/system/system-metrics/) (Defines metrics like CPU and Memory utilization applicable to network devices)
- Splunk Blog: [What is Telemetry?](https://www.splunk.com/en_us/blog/learn/what-is-telemetry.html) (Provides broader context on telemetry data, including network examples)
- OpenTelemetry Documentation: [System Metrics - Network](https://opentelemetry.io/docs/specs/semconv/system/system-metrics/#network) (Covers network traffic metrics)
