---
title: "Preventing Null Map Configuration Overwrites"
weight: 12
description: "How to use empty maps `{}` to prevent null maps from removing previous configuration values in the OpenTelemetry Collector."
---

**Question:**
How can null maps be prevented from removing earlier configuration values in the OpenTelemetry Collector?

**Answer:**
Use `{}` to represent empty maps in the configuration.

**Explanation:**
The OpenTelemetry Collector uses a layered configuration system (e.g., merging configuration from multiple sources or using environment variable substitution). When a configuration layer defines a map key with a `null` value, it can inadvertently remove or unset configurations defined in previous layers. To explicitly define an empty map without overriding previous non-map values or removing nested configurations, use the empty map literal `{}` instead of `null`.

**Reference:**
This behavior is related to the configuration merging logic.
[Collector Configuration Sources](https://opentelemetry.io/docs/collector/configuration/#configuration-sources)
