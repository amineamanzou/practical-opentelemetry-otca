---
title: "Transform Processor Error Mode: Silent"
weight: 16
description: "Understanding the 'silent' error_mode option in the OpenTelemetry Collector's Transform Processor."
---

**Question:**
Which 'error_mode' configuration option for the transform processor allows the processor to ignore errors silently and continue processing the next statement?

**Answer:**
`silent`

**Explanation:**
The Transform Processor (using OTTL) can encounter errors during statement execution (e.g., type mismatches, missing attributes). The `error_mode` configuration setting dictates how these errors are handled. Setting `error_mode: silent` instructs the processor to catch any errors that occur during the execution of an OTTL statement, log them internally (if verbose logging is enabled), and then proceed to the next statement in the sequence without stopping processing or propagating the error up the pipeline.

**Reference:**
[Transform Processor Error Handling](https://opentelemetry.io/docs/collector/transformations/#error-handling)
