---
title: "Non-Identifying Properties in OTLP Data Model (Metric Description)"
weight: 34
description: "Identifies metric stream description as a non-identifying property in the OTLP data model."
---

This note clarifies which properties are considered non-identifying for a metric stream in the OTLP data model, using description as an example.

## OTLP Non-Identifying Properties (Metric Description)

**Question:**
Which of the following properties is NOT considered identifying in the OpenTelemetry Protocol (OTLP) data model?

**Answer:**
Metric stream's description

**Explanation:**
The OTLP specification defines how telemetry data (metrics, traces, logs) is serialized for transport. For metrics, a "metric stream" is uniquely identified by a combination of core properties:

* Resource attributes
* Instrumentation Scope attributes
* Metric name
* Metric unit
* Metric data type (e.g., Sum, Gauge, Histogram)
* For Sums: Aggregation Temporality (Delta vs. Cumulative) and Monotonicity
* For Gauges: (No extra identifying properties)
* For Histograms: Aggregation Temporality
* Attributes attached to the metric points

Properties like the metric stream's **description** or the **start time** are considered *non-identifying*. This means two streams with identical identifying properties but different descriptions are considered the same stream, and producers/consumers need rules to handle such conflicts (e.g., OTLP producers choosing the longer description).

**Reference:**
[OpenTelemetry Specification - OTLP: Identifying vs Non-identifying Properties](https://opentelemetry.io/docs/specs/otlp/#identifying-vs-non-identifying-properties)
