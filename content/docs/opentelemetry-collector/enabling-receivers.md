---
title: "Enabling Receivers in the OpenTelemetry Collector"
weight: 34
description: "How receivers are enabled and activated within the OpenTelemetry Collector configuration."
---

**Question:**
How are receivers enabled in the OpenTelemetry Collector?

**Answer:**
By adding them to the appropriate pipelines within the service section.

**Explanation:**
Defining a receiver under the top-level `receivers:` key in the OpenTelemetry Collector configuration only specifies its settings (e.g., endpoint, protocol). To actually *activate* the receiver and make it start listening for or collecting data, you must reference its name (e.g., `otlp`) in the `receivers:` list of one or more pipelines defined under the `service.pipelines:` section. Data collected by an enabled receiver flows into the pipeline(s) it is attached to.

**Reference:**
[Collector Configuration - Service Section](https://opentelemetry.io/docs/collector/configuration/#service)
