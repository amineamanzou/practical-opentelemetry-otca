---
title: "Identifying the Jaeger Exporter in Configuration"
weight: 13
description: "Identifying the component responsible for exporting trace data to Jaeger in an OpenTelemetry Collector configuration."
---

**Question:**
In the provided OpenTelemetry Collector YAML configuration, which component is responsible for exporting trace data to Jaeger?

**Answer:**
`jaeger`

**Explanation:**
OpenTelemetry Collector configurations define components under top-level keys like `receivers`, `processors`, `exporters`, and `service`. An exporter component defined under the `exporters` key is responsible for sending telemetry data to a specific backend. If an exporter is configured with the name `jaeger` (or `jaeger/something`), it typically signifies the use of the Jaeger exporter, which sends trace data to a Jaeger backend (like Jaeger Query/Collector).

**Reference:**
[Jaeger Exporter Documentation](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/exporter/jaegerexporter)
[Collector Configuration Structure](https://opentelemetry.io/docs/collector/configuration/#exporters)
