---
title: "Naming Convention for system.process UpDownCounter"
weight: 11
description: "Specifies the OpenTelemetry preferred naming convention for an UpDownCounter tracking active processes."
---

This note details the correct naming convention according to OpenTelemetry semantic conventions for a specific metric: an `UpDownCounter` measuring the count of active processes within the `system.process` namespace.

## Naming Convention: system.process Active Count

**Question:** What is the preferred naming convention for an `UpDownCounter` representing the number of active processes in an OpenTelemetry metric namespace `system.process`?

**Answer Principle:** The preferred name is `system.process.count`. OpenTelemetry semantic conventions often use a singular noun representing the *thing* being measured, combined with a unit or state where applicable, but for simple counts, just the noun is often sufficient within the namespace.

**Explanation:**
OpenTelemetry's metric semantic conventions aim for consistency and clarity. While general guidelines exist, specific conventions are defined for common operating system and runtime metrics.

- **Namespace:** `system.process` clearly indicates the domain.
- **Instrument:** An `UpDownCounter` is appropriate because the number of processes can increase or decrease.
- **Metric Name:** `count` is the standard term used within the `system.process` namespace to represent the number of processes. While the documentation might not explicitly list *every* possible metric name, the convention for counts within namespaces is generally to use `count` or a similar simple term if the namespace itself provides enough context (like `system.process`). Other examples might include `system.cpu.utilization` or `process.memory.usage`.

Using `system.process.count` ensures alignment with standard conventions, improving discoverability and interoperability.

**Reference:**

- OpenTelemetry Documentation: [System Metric Conventions](https://opentelemetry.io/docs/specs/semconv/system/system-metrics/) (While `system.process.count` might not be explicitly listed as of a certain date, the pattern follows from other system-level counts and general naming guidelines).
- OpenTelemetry Documentation: [Metric Naming Guidelines](https://opentelemetry.io/docs/specs/otel/metrics/semantic_conventions/#metric-naming)
