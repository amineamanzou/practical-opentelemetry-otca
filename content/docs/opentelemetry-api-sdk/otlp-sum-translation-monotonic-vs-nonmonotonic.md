---
title: "OTLP Sum Translation: Monotonic vs Non-monotonic"
weight: 37
description: "Specifies the translation of monotonic and non-monotonic OTLP Sum points to the TimeSeries model (Counter/Gauge)."
---

This note details how OTLP Sum data points are represented in the TimeSeries model, distinguishing between monotonic and non-monotonic sums.

## OTLP Sum Translation (Monotonic vs Non-monotonic)

**Question:**
In the OpenTelemetry Protocol (OTLP) data model, how is a Sum data point translated into the Timeseries model based on its monotonicity?

**Answer:**
Monotonic Sum is translated into a Counter, and non-monotonic Sum into a Gauge.

**Explanation:**
The OTLP `Sum` data point type carries an `is_monotonic` boolean flag. This flag determines how the value should be interpreted and subsequently translated into the conceptual TimeSeries model:

* **Monotonic Sum (`is_monotonic: true`):** Represents a value that only increases over time (or resets to zero on restart). This maps directly to the **Counter** metric kind in the TimeSeries model. Examples include total requests served or bytes transmitted.
* **Non-monotonic Sum (`is_monotonic: false`):** Represents a value that can increase or decrease. This maps to the **Gauge** metric kind in the TimeSeries model. Examples include the current number of active connections or the size of a queue.

This distinction is crucial for monitoring systems to correctly interpret and aggregate the data (e.g., calculating rates from Counters, observing current values from Gauges).

**Reference:**
[OpenTelemetry Specification - OTLP: Sum](https://opentelemetry.io/docs/specs/otlp/#sum)
[OpenTelemetry Specification - Metrics Data Model: Sum](https://opentelemetry.io/docs/specs/otel/metrics/data-model/#sums)
