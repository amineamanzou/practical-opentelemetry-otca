---
title: "Properties Not Part of the Metrics TimeSeries Model"
weight: 24
description: "Identifies properties that are not part of the OpenTelemetry Metrics TimeSeries model."
---

This note lists elements related to metrics that are not included as direct properties of the TimeSeries model itself.

## TimeSeries Model Exclusions

**Question:**
Which of the following properties is NOT part of the Timeseries model in OpenTelemetry's metrics data model?

**Answer:**
Instrument type

**Explanation:**
The OpenTelemetry Metrics TimeSeries model represents the aggregated data points for a specific metric, resource, and attribute set. It contains the actual data points (e.g., Sum, Gauge, Histogram values), start/end timestamps, and potentially exemplars. The *metadata* about the metric stream, such as the originating instrument's name, description, unit, and *type* (Counter, Gauge, Histogram, etc.), are considered properties of the parent `Metric` or `MetricStream` entity, not direct properties repeated within every `TimeSeries` data structure. The `TimeSeries` assumes this context is known from the stream it belongs to.

**Reference:**
[OpenTelemetry Specification - Metrics Data Model: TimeSeries Model](https://opentelemetry.io/docs/specs/otel/metrics/data-model/#timeseries-model)
[OpenTelemetry Specification - Metrics Data Model: Metric Points](https://opentelemetry.io/docs/specs/otel/metrics/data-model/#metric-points) (Shows point structure within TimeSeries)
