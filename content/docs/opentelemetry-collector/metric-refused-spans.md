---
title: "Metric for Spans Refused Due to Memory Limits"
weight: 23
description: "Identifying the OpenTelemetry Collector metric that indicates spans are being refused by a processor due to memory limitations."
---

**Question:**
Which metric indicates that the OpenTelemetry Collector is refusing spans due to memory limitations?

**Answer:**
`otelcol_processor_refused_spans`

**Explanation:**
Processors within the OpenTelemetry Collector pipeline, particularly queuing or buffering processors like the `memory_limiter` processor, might refuse to accept new data points (like spans) if internal limits (e.g., memory usage) are exceeded. The `otelcol_processor_refused_spans` metric (and its counterparts `otelcol_processor_refused_metric_points`, `otelcol_processor_refused_log_records`) tracks the number of data points refused by a specific processor instance, often indicating backpressure or resource exhaustion.

**Reference:**
[Collector Telemetry - Processor Metrics](https://opentelemetry.io/docs/collector/monitoring/#processor-metrics)
[Memory Limiter Processor](https://github.com/open-telemetry/opentelemetry-collector/tree/main/processor/memorylimiterprocessor)
