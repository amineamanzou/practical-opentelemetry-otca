---
title: "Connecting a Single Receiver to Multiple Pipelines"
weight: 21
description: "How to configure a single OpenTelemetry Collector receiver to send its data to multiple processing pipelines."
---

**Question:**
In the OpenTelemetry Collector configuration, how can a single receiver send telemetry data to multiple pipelines?

**Answer:**
By listing the receiver in the `receivers` key of each pipeline.

**Explanation:**
The `service` section of the OpenTelemetry Collector configuration defines data processing pipelines for different signals (traces, metrics, logs). Each pipeline definition includes lists of `receivers`, `processors`, and `exporters`. To have data from a single receiver (e.g., an OTLP receiver named `otlp`) processed by multiple distinct pipelines (e.g., `traces/pipeline1` and `traces/pipeline2`), you simply include the receiver's name (`otlp`) in the `receivers` list of *both* pipeline definitions within the `service.pipelines` section.

**Reference:**
[Collector Configuration - Service Pipelines](https://opentelemetry.io/docs/collector/configuration/#service-pipelines)
