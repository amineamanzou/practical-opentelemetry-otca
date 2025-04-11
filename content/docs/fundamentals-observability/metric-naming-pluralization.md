---
title: "Metric Naming Conventions Regarding Pluralization"
weight: 12
description: "Explains OpenTelemetry's guidelines on using singular vs. plural nouns in metric names."
---

This note covers the OpenTelemetry guidelines concerning the use of pluralization in metric names, a key aspect of semantic conventions for clarity and consistency.

## Metric Naming Conventions: Pluralization

**Question:** Which of the following metric names adheres to OpenTelemetry's naming conventions regarding pluralization?

**Answer Principle:** OpenTelemetry metric naming conventions generally recommend using **singular nouns** for metric names. Units, when included, must also be singular.

**Explanation:**
The preference for singular nouns in metric names promotes consistency and reduces ambiguity.

- **Clarity:** The instrument type (Counter, UpDownCounter, Gauge) often implies the nature of the measurement (e.g., a count, a current value). Using a singular noun for the *thing* being measured (e.g., `http.server.request.duration`, not `http.server.request.durations`) keeps the name focused.
- **Units:** Units associated with metrics *must* be singular (e.g., `ms` for milliseconds, `By` for bytes) according to the [UCUM](https://unitsofmeasure.org/ucum.html) standard adopted by OpenTelemetry. Pluralizing the metric name itself alongside a singular unit would be inconsistent.
- **Exceptions:** While singular is the strong recommendation, pluralization *might* be acceptable if it significantly enhances clarity or aligns with a very well-established external convention for that specific term. However, the default should always be singular.

For example, `system.network.packets` (plural) might be used if it refers distinctly to counts of packets over an interval, but `system.network.packet.count` (singular noun `packet`) would often be preferred if feasible.

**Reference:**

- OpenTelemetry Documentation: [Metric Naming Guidelines](https://opentelemetry.io/docs/specs/otel/metrics/semantic_conventions/#metric-naming) (Specifically mentions preferring singular nouns).
- OpenTelemetry Documentation: [Units](https://opentelemetry.io/docs/specs/otel/metrics/semantic_conventions/#instrument-units) (Mandates singular units based on UCUM case-sensitive abbreviations).
