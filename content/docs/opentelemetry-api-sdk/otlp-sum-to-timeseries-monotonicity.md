---
title: "OTLP Sum Point Translation to TimeSeries Based on Monotonicity"
weight: 32
description: "Explains how OTLP Sum data points are translated into the TimeSeries model depending on their monotonicity."
---

This note describes the conversion rule for OTLP Sum data points into the OpenTelemetry TimeSeries model, specifically based on the monotonicity property.

## OTLP Sum to TimeSeries Translation (Monotonicity)

**Question:**
In the OpenTelemetry Protocol (OTLP) data model, how is a Sum point translated into the Timeseries model based on its monotonicity?

**Answer:**
Translated into a Counter if monotonic, otherwise a Gauge.

**Explanation:**
The OTLP data model includes a `Sum` data point type. A crucial property of a `Sum` is its `is_monotonic` flag.

* If `is_monotonic` is `true`, it means the sum represents a value that only ever increases (like the total number of requests handled). When translating this to the conceptual TimeSeries model used by backends, it maps directly to a **Counter**. Counters represent monotonically increasing values.
* If `is_monotonic` is `false`, it means the sum can increase or decrease (like the current number of active requests). This type of value maps to a **Gauge** in the TimeSeries model. Gauges represent values that can arbitrarily go up and down.

This translation rule ensures that the semantic meaning of the metric (cumulative count vs. current state) is preserved when moving from the OTLP wire format to the conceptual model used for storage and querying.

**Reference:**
[OpenTelemetry Specification - OTLP: Sum](https://opentelemetry.io/docs/specs/otlp/#sum)
[OpenTelemetry Specification - Metrics Data Model: Sum](https://opentelemetry.io/docs/specs/otel/metrics/data-model/#sums) (Describes monotonicity)
[OpenTelemetry Specification - Metrics Data Model: Metric Points](https://opentelemetry.io/docs/specs/otel/metrics/data-model/#metric-points) (Implies Counter/Gauge mapping)
