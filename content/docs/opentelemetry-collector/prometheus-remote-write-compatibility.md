---
title: "OpenTelemetry Data Model Compatibility with Prometheus Remote Write"
weight: 24
description: "How the OpenTelemetry data model ensures compatibility when exporting metrics via the Prometheus Remote Write protocol."
---

**Question:**
How does the OpenTelemetry data model ensure compatibility with the Prometheus Remote Write protocol?

**Answer:**
By providing well-defined translations, including automatic attribute removal and histogram resolution lowering.

**Explanation:**
The OpenTelemetry (OTLP) metrics data model is richer than the Prometheus exposition format. To ensure compatibility when using the Prometheus Remote Write exporter, the Collector performs specific, well-defined translations:

* **Attributes:** Only attributes that are valid Prometheus labels (string key/value pairs) are kept; others are dropped.
* **Metric Types:** OTLP types are mapped to Prometheus types (e.g., Sum -> Counter/Gauge, Gauge -> Gauge).
* **Histograms:** OTLP histograms (exponential or explicit) are translated to Prometheus native histograms or classic histograms, potentially involving down-sampling (lowering resolution) or converting to summaries depending on configuration.
* **Summaries:** OTLP summaries are translated to Prometheus summaries.

These translations allow OTLP metric data to be ingested by Prometheus-compatible backends.

**Reference:**
[Prometheus and OpenTelemetry Compatibility](https://opentelemetry.io/docs/specs/otel/compatibility/prometheus_and_openmetrics/)
[Prometheus Remote Write Exporter](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/exporter/prometheusremotewriteexporter)
