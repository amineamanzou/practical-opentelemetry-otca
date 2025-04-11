---
title: "Semantics-Preserving Metric Transformations"
weight: 20
description: "Discusses semantics-preserving data transformations allowed by the OpenTelemetry Metrics data model, including temporal reaggregation."
---

This note explores the types of data transformations that can be applied to metrics within the OpenTelemetry ecosystem (e.g., by the Collector) while preserving the original meaning and intent of the metric data.

## Semantics-Preserving Metric Transformations

**Question:** Which of the following is a semantics-preserving data transformation supported by the OpenTelemetry Metrics data model?

**Answer Principle:** Semantics-preserving transformations modify the *representation*, *granularity*, or *aggregation level* of metric data without changing its underlying meaning. Examples include **changing aggregation temporality, temporal reaggregation, adjusting units, filtering attributes, or aggregating data points across attributes**.

**Explanation:**
The OpenTelemetry Metrics data model allows for certain transformations, often performed by components like the OpenTelemetry Collector, that help adapt metric data for different backends or analysis needs without altering the fundamental information conveyed.

Key semantics-preserving transformations include:

1. **Temporality Conversion:** Converting between Cumulative (reporting the value since a start time) and Delta (reporting the change since the last report) aggregation temporalities. This changes how the value is reported over time, but not the underlying measurement.
2. **Unit Conversion:** Changing the unit of measurement (e.g., `ms` to `s`, `By` to `KiBy`) as long as the conversion factor is precise. The magnitude changes, but the represented quantity remains the same.
3. **Attribute Filtering/Modification:** Removing or adding attributes (metadata dimensions) to metric data points. Removing attributes leads to broader aggregation.
4. **Aggregation (including Temporal Reaggregation):** Combining multiple data points into fewer points. This can be done by summing values or calculating averages across certain attribute dimensions.
A key example is **Temporal Reaggregation**: This allows metrics collected at high-frequency intervals (e.g., every second) to be aggregated into longer intervals (e.g., every minute) without altering their semantic meaning. This transformation is crucial for managing data granularity, reducing storage requirements, and facilitating efficient analysis over longer timeframes, while still preserving the meaning of the measurement (e.g., the total count or average value over the longer interval).

Transformations that *change* the metric type (e.g., converting a Gauge to a Counter) or apply arbitrary mathematical functions that alter the core meaning are generally *not* considered semantics-preserving.

**Reference:**

- OpenTelemetry Documentation: [Metrics Data Model](https://opentelemetry.io/docs/specs/otel/metrics/data-model/) (Overall model including transformations)
- OpenTelemetry Documentation: [Metrics Data Model - Aggregation Temporality](https://opentelemetry.io/docs/specs/otel/metrics/data-model/#aggregation-temporality)
- OpenTelemetry Documentation: [Collector Processors](https://opentelemetry.io/docs/collector/configuration/#processors) (Examples like `metricstransform` or `attributes` processor can perform some of these transformations).
