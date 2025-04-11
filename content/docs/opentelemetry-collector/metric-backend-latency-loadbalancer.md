---
title: "Metric for Monitoring Backend Export Latency (Load Balancer)"
weight: 25
description: "Identifying the OpenTelemetry Collector metric used to understand backend latency when using the load balancing exporter."
---

**Question:**
In the OpenTelemetry Collector, what metric would you monitor to understand if your backend is slowing down the export process?

**Answer:**
`otelcol_loadbalancer_backend_latency`

**Explanation:**
When using the `loadbalancing` exporter to distribute telemetry data across multiple backend instances (e.g., multiple OTLP-compatible servers), it's crucial to monitor the performance of each individual backend. The `otelcol_loadbalancer_backend_latency` metric specifically measures the latency of export calls to each resolved backend managed by the load balancing exporter. High values for this metric for one or more backends indicate that those specific backends are slow to respond, potentially causing backpressure in the Collector.

**Reference:**
[Load Balancing Exporter Documentation](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/exporter/loadbalancingexporter#metrics)
