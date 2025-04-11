---
title: "Practices for Metric Discoverability and Comparison"
weight: 10
description: "Discusses OpenTelemetry best practices for defining metrics to enhance discoverability and ad-hoc comparison."
---

This note outlines the practices recommended by OpenTelemetry for defining metrics in a way that makes them easy to find, understand, and compare across different systems and services.

## Enhancing Metric Discoverability and Comparison

**Question:** When defining new metrics in OpenTelemetry, which of the following practices helps facilitate discoverability and ad-hoc comparison?

**Answer Principle:** Adhering to OpenTelemetry's **Semantic Conventions** for naming, units, and attributes is crucial for metric discoverability and comparison.

**Explanation:**
Using standardized names, units (like seconds, bytes), and attribute keys ensures that metrics representing similar concepts (e.g., HTTP request duration) are expressed consistently, regardless of the source. This consistency allows users and tooling to:

- **Discover:** Easily find relevant metrics using predictable names and attributes.
- **Compare:** Perform meaningful ad-hoc comparisons and aggregations across different services or components because the units and meanings are aligned.
- **Correlate:** Relate metrics to other signals (like traces and logs) that also follow semantic conventions.

Failing to follow these conventions leads to ambiguity and makes it difficult to build reliable dashboards, alerts, or perform cross-system analysis.

**Reference:**

- OpenTelemetry Documentation: [Metrics Semantic Conventions](https://opentelemetry.io/docs/specs/semconv/general/metrics/)
- OpenTelemetry Documentation: [Metrics General Guidelines](https://opentelemetry.io/docs/specs/otel/metrics/semantic_conventions/) - See sections on Naming and Units.
