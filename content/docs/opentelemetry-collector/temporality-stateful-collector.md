---
title: "Temporality in Stateful Collector Scenarios"
weight: 19
description: "Understanding metric temporality (Delta) when a stateful OpenTelemetry Collector receives data from a stateless client."
---

**Question:**
In an OpenTelemetry setup, what temporality is used when the Collector receives data from a stateless client and is configured as a stateful server?

**Answer:**
Delta temporality

**Explanation:**
Stateless clients typically report metrics as changes (deltas) since the last report, as they don't maintain long-term state. When an OpenTelemetry Collector is configured to act statefully (e.g., performing aggregation using processors like `cumulativetodelta` or when dealing with certain receiver/exporter combinations), it often expects or converts incoming data to Delta temporality. Delta represents the change in a value over a specific interval, which is suitable for stateless clients reporting periodic updates.

**Reference:**
While specific processor docs might mention temporality, the core concepts are here:
[OpenTelemetry Metrics Data Model - Temporality](https://opentelemetry.io/docs/specs/otel/metrics/data-model/#temporality)
