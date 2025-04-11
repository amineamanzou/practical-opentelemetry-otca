---
title: "Failed Questions for the fundamentals of observability"
weight: 2
description: "A list of failed questions for the fundamentals of observability domain to help focus study efforts."
---

This document organizes failed questions for the fundamentals of observability to help identify knowledge gaps and focus further study.

## Failed questions

- When defining new metrics in OpenTelemetry, which of the following practices helps facilitate discoverability and ad-hoc comparison?
- In which scenario would using an OpenTelemetry Agent for local data preprocessing be most beneficial?
- What is the preferred naming convention for an UpDownCounter representing the number of active processes in an OpenTelemetry metric namespace 'system.process'?
- Which of the following metric names adheres to OpenTelemetry's naming conventions regarding pluralization?
- According to OpenTelemetry guidelines, what should be checked to prevent name reuse when introducing a new metric name?
- Which of the following accurately describes a characteristic of semistructured logs in production observability?
- How is telemetry data best defined in the context of system monitoring?
- A development team wants to proactively identify and fix issues like database errors and JVM problems in their application. Which telemetry benefit should they leverage?
- Which type of log source in OpenTelemetry cannot be modified to include trace context information and typically follows a predefined format like Syslog or Windows Event Logs?
- Given two spans with the same trace_id but different parent_id values, what does this imply about their relationship?
- Which of the following metrics is typically associated with network telemetry data?
- Which of the following is a semantics-preserving data transformation supported by the OpenTelemetry Metrics data model?
- Which of the following is an example of a Failed Event in Kubernetes?
- Which of the following actions is essential for addressing data privacy concerns when implementing telemetry systems?
- In OpenTelemetry, which process involves creating individual spans and linking them to form a complete trace?

## Analysis

Based on the questions listed, the primary areas needing reinforcement within the Fundamentals of Observability domain include:

1. **OpenTelemetry Metrics:**
    - **Semantic Conventions:** Naming rules (pluralization, specific instruments like `UpDownCounter`), preventing name reuse, standard structure (`namespace.instrument.unit`).
    - **Best Practices:** How metric definitions impact discoverability and analysis.
    - **Data Model:** Understanding transformations and the underlying model.
2. **OpenTelemetry Tracing:**
    - **Core Concepts:** Span relationships (`trace_id`, `parent_id`), trace formation process.
3. **OpenTelemetry Logging:**
    - **Log Types:** Characteristics of semistructured logs.
    - **Trace Context:** Limitations of injecting trace context into certain log sources (e.g., system logs).
4. **General Observability Concepts:**
    - **Definitions & Benefits:** Core definition of telemetry and its practical applications (error detection).
    - **Signal Types:** Associating metrics with specific domains (e.g., network).
    - **Data Privacy:** Essential privacy considerations.
5. **OpenTelemetry Architecture:**
    - **Agent/Collector:** Use cases for local preprocessing.
6. **Integration (Kubernetes):**
    - Recognizing specific platform event types.

## Recommendations

Focus your study on the following official OpenTelemetry documentation sections:

- **Metrics:** [Metrics Semantic Conventions](https://opentelemetry.io/docs/specs/semconv/general/metrics/) and [Metrics Data Model](https://opentelemetry.io/docs/specs/otel/metrics/data-model/).
- **Tracing:** [Tracing Concepts](https://opentelemetry.io/docs/concepts/signals/traces/).
- **Logging:** [Logs Data Model](https://opentelemetry.io/docs/specs/otel/logs/data-model/) and [Logs Semantic Conventions](https://opentelemetry.io/docs/specs/semconv/general/logs/).
- **Core Concepts:** [Observability Primer](https://opentelemetry.io/docs/concepts/observability-primer/) and [Privacy](https://opentelemetry.io/docs/concepts/privacy/).
- **Collector:** [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) architecture and processors.
- **Kubernetes:** [Kubernetes Semantic Conventions](https://opentelemetry.io/docs/specs/semconv/resource/k8s/).
