---
title: "Benefit of Context Association in the Transform Processor"
weight: 6
description: "Explains the performance advantage of using correct contexts in the OpenTelemetry Transform Processor."
---

This note discusses why associating statements with the correct context (e.g., spans, metrics, logs) in the OpenTelemetry Collector's transform processor is beneficial.

## Benefit of Context Association in the Transform Processor

**Question:** What is the benefit of associating statements with the correct context in the transform processor?

**Answer:** It improves performance by leveraging context-specific processing.

**Explanation:**

The `transform` processor in the OpenTelemetry Collector uses the OpenTelemetry Transformation Language (OTTL) to modify telemetry data within the pipeline. OTTL statements operate on specific data items (like spans, metrics, or logs).

OTTL allows defining processing logic within specific *contexts* (`trace`, `metric`, `log`). When statements are placed within the correct context block, the processor knows it only needs to evaluate those statements when processing data of that specific type.

For example, a statement designed to modify span attributes placed within the `trace` context will only be evaluated when spans pass through the processor; it will be skipped entirely when metrics or logs are being processed. This avoids unnecessary computation and improves the overall performance and efficiency of the processor, especially in high-throughput pipelines.

```yaml
processors:
  transform:
    trace_statements:
      context: span # This statement only runs for spans
      statements:
        - set(attributes["http.method"], "POST") where name == "/login"
    metric_statements:
      context: metric # This statement only runs for metrics
      statements:
        - convert_sum_to_gauge() where name == "cpu.utilization"

service:
  pipelines:
    traces:
      processors: [transform]
    metrics:
      processors: [transform]
```

**Reference:**

* [OpenTelemetry Collector Contrib - Transform Processor](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/processor/transformprocessor)
