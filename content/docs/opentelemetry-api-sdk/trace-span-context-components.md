---
title: "Components of the OpenTelemetry SpanContext"
weight: 21
description: "Lists the required components of the OpenTelemetry SpanContext."
---

This note identifies the essential components that make up an OpenTelemetry SpanContext.

## SpanContext Components

**Question:**
Which of the following is NOT a component of the SpanContext in OpenTelemetry?

**Answer:**
SpanName *(Note: Span Name is part of the Span itself, not the immutable SpanContext)*

**Explanation:**
The `SpanContext` represents the portion of a `Span` that must be propagated across process boundaries. It contains the identifiers that link spans together into a trace. According to the OpenTelemetry specification, the `SpanContext` MUST include:

* **TraceId:** The ID of the trace the span belongs to.
* **SpanId:** The unique ID of the span itself.
* **TraceFlags:** Flags indicating properties like whether the trace is sampled.
* **TraceState:** Additional vendor-specific trace propagation information.

The `SpanName`, while a crucial part of a `Span`, is not part of the `SpanContext` because it's not required for context propagation and linking spans; the IDs serve that purpose. Span names are typically descriptive and mutable during the span's lifetime, whereas the SpanContext is immutable once created.

**Reference:**
[OpenTelemetry Specification - Trace API: SpanContext](https://opentelemetry.io/docs/specs/otel/trace/api/#spancontext)
