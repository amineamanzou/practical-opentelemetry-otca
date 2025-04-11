---
title: "Semantic Convention for System Memory Utilization"
weight: 11
description: "Defines the standard OpenTelemetry instrument name for memory utilization."
---

This note specifies the correct OpenTelemetry semantic convention instrument name for measuring system memory utilization.

## Semantic Convention: System Memory Utilization

**Question:**
According to OpenTelemetry's semantic conventions, what is the correct instrument name for measuring the fraction of memory in use relative to its limit?

**Answer:**
`system.memory.utilization`

**Explanation:**
OpenTelemetry defines semantic conventions for common telemetry data to ensure consistency across different tools and backends. For system metrics, the convention specifies `system.memory.utilization` as the instrument name for reporting the fraction (value between 0 and 1) of memory currently in use compared to the total available memory limit. This applies to various memory types like heap or non-heap memory. Using standardized names allows for easier correlation and analysis in observability platforms.

**Reference:**
[OpenTelemetry Semantic Conventions - System Metrics: Memory - system.memory.utilization](https://opentelemetry.io/docs/specs/semconv/system/system-metrics/#metric-systemmemoryutilization)
