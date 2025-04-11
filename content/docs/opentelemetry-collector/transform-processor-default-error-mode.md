---
title: "Default Error Mode for Transform Processor"
weight: 20
description: "Identifying the default error handling behavior ('propagate') of the OpenTelemetry Collector's Transform Processor."
---

**Question:**
If the 'error_mode' is not specified in the transform processor configuration, what is the default mode?

**Answer:**
`propagate`

**Explanation:**
When using the Transform Processor (OTTL) in the OpenTelemetry Collector, if the `error_mode` configuration option is omitted, it defaults to `propagate`. This means that if an error occurs during the execution of an OTTL statement, the processor will stop processing the current telemetry item (e.g., span, metric) for that statement list and will propagate the error up. This might cause the entire batch of data to be rejected or handled according to the pipeline's overall error handling strategy.

**Reference:**
[Transform Processor Error Handling](https://opentelemetry.io/docs/collector/transformations/#error-handling)
