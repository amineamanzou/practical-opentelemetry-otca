---
title: "Package Types Not Part of OpenTelemetry Signals"
weight: 31
description: "Identifies package types that are not considered fundamental components of an OpenTelemetry signal."
---

This note clarifies the standard package types associated with OpenTelemetry signals (like Traces, Metrics, Logs) and identifies what is not typically considered one of these core package types.

## Signal Package Type Exclusions

**Question:**
Which of the following is NOT a type of package that each OpenTelemetry signal consists of?

**Answer:**
Agent

**Explanation:**
Each primary OpenTelemetry signal (Traces, Metrics, Logs) is typically defined by three core components or package types:

1. **API:** Defines the language-specific interfaces for instrumenting code (e.g., `Tracer`, `Meter`). Libraries depend on this.
2. **SDK:** Provides the language-specific implementation of the API, handling configuration, processing, and exporting. Applications depend on this.
3. **Data Model/Semantic Conventions:** Define the structure of the telemetry data (e.g., Span format, TimeSeries model) and the standard names and meanings for attributes (e.g., `http.method`, `service.name`). These are defined in the cross-language specification.

An "Agent" (often referring to auto-instrumentation agents like the Java agent) is a *distribution mechanism* or *implementation detail* for applying the SDK and instrumentation, not a fundamental package type inherent to the definition of *every* signal itself in the same way as the API, SDK, and Data Model/Conventions are.

**Reference:**
[OpenTelemetry Concepts - API vs SDK](https://opentelemetry.io/docs/concepts/api-sdk/)
[OpenTelemetry Specification - Overview](https://opentelemetry.io/docs/specs/otel/) (Implicitly shows structure through different spec sections)
