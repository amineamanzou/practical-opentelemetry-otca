---
title: "OTLP Conflict Resolution for Non-Identifying Properties"
weight: 25
description: "Describes the recommended OTLP producer behavior when handling conflicts in non-identifying properties like description."
---

This note explains how OTLP producers should handle conflicts involving non-identifying metric stream properties.

## OTLP Conflict: Non-Identifying Property

**Question:**
According to OpenTelemetry Protocol (OTLP) producer recommendations, how should producers handle a conflict involving a non-identifying property such as the metric description?

**Answer:**
Choose the longer description string.

**Explanation:**
In OTLP, metric streams are uniquely identified by properties like name, type, unit, resource, and attributes. Properties like the metric description or aggregation temporality are considered non-identifying. It's possible, though generally discouraged, for a producer to encounter multiple definitions for the same logical metric stream (based on identifying properties) but with differing non-identifying properties (e.g., different descriptions). The OTLP specification recommends a resolution strategy for such conflicts: for the description, the producer should choose the longer string, assuming it's likely more informative. For other conflicts like aggregation temporality, specific rules apply (e.g., preferring Delta over Cumulative if both are seen for a monotonic sum).

**Reference:**
[OpenTelemetry Specification - OTLP: Producer Recommendations - Metric Description Conflict](https://opentelemetry.io/docs/specs/otlp/#producer-recommendations)
