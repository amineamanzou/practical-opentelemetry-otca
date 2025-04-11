---
title: "Sending Data to Multiple Exporters (Fan-Out)"
weight: 14
description: "How the OpenTelemetry Collector uses a fan-out mechanism to send data to multiple exporters within a single pipeline."
---

**Question:**
How does the OpenTelemetry Collector ensure that data is sent to multiple exporters within a single pipeline?

**Answer:**
Using a fan-out consumer by the last processor

**Explanation:**
Within a pipeline defined in the `service` section of the Collector configuration, telemetry data flows sequentially through receivers, processors, and finally to exporters. When multiple exporters are listed for a pipeline, the component connecting the last processor to the exporters acts as a fan-out consumer. It receives the data once from the processor chain and replicates it, sending a copy to each configured exporter in that pipeline.

**Reference:**
[Collector Config Service](https://opentelemetry.io/docs/collector/configuration/)
