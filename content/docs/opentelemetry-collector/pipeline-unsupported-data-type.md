---
title: "Handling Unsupported Data Types in Collector Pipelines"
weight: 32
description: "Understanding the outcome when an OpenTelemetry Collector pipeline is configured with a data type not supported by a receiver."
---

**Question:**
What happens when a pipeline in the OpenTelemetry Collector is configured with a data type that a receiver does not support?

**Answer:**
The Collector throws a `pipeline.ErrSignalNotSupported` exception

**Explanation:**
OpenTelemetry Collector components (receivers, processors, exporters) declare which telemetry signals (traces, metrics, logs) they support. Pipelines defined in the `service` section connect these components. If you configure a pipeline (e.g., a `metrics` pipeline) and include a receiver in that pipeline's `receivers` list that *only* supports `traces`, the Collector's configuration validation process will detect this mismatch during startup. It will fail to start and throw an error, typically `pipeline.ErrSignalNotSupported`, indicating that a component in the pipeline does not support the signal type the pipeline is configured for.

**Reference:**
This relates to configuration validation and component capabilities.
[Collector Configuration - Service Pipelines](https://opentelemetry.io/docs/collector/configuration/#service-pipelines)
