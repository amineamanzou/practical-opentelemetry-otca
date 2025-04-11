---
title: "OpenTelemetry Metrics TimeSeries Model"
weight: 10
description: "Explains the purpose of the TimeSeries model within the OpenTelemetry Metrics data model."
---

This note details the role and significance of the TimeSeries model in the OpenTelemetry metrics data model, particularly how it relates to exporters.

## OpenTelemetry Metrics TimeSeries Model

**Question:**
In OpenTelemetry's Metrics data model, what does the TimeSeries model represent?

**Answer:**
How exporters should interpret the in-flight metrics data.

**Explanation:**
The TimeSeries model is the fundamental structure defined in the OpenTelemetry Metrics data model specification. It represents a series of data points for a specific metric instrument, resource, and attribute set over time. Exporters use this model to understand the structure and meaning of the metric data they receive (e.g., whether it's a counter, gauge, histogram) and how to translate it into the format required by the target observability backend. It essentially defines the schema for aggregated metric data ready for export.

**Reference:**
[OpenTelemetry Specification - Metrics Data Model: TimeSeries](https://opentelemetry.io/docs/specs/otel/metrics/data-model/#timeseries-model)
