---
title: "Trace ID in OpenTelemetry SpanContext"
weight: 30
description: "Confirms that Trace ID is a required component of the OpenTelemetry SpanContext."
---

This note confirms the inclusion of the Trace ID within the OpenTelemetry SpanContext.

## Trace ID in SpanContext

**Question:**
Which of the following fields is included in the Span Context in OpenTelemetry?

**Answer:**
Trace ID

**Explanation:**
The OpenTelemetry `SpanContext` is designed to carry the essential information needed to correlate spans across process boundaries. A fundamental piece of this information is the **Trace ID**, a unique identifier for the entire trace (a collection of related spans representing a single request or workflow). Every span within a trace shares the same Trace ID. Along with the Span ID, TraceFlags, and TraceState, the Trace ID is a mandatory component of the `SpanContext` as defined by the specification.

**Reference:**
[OpenTelemetry Specification - Trace API: SpanContext](https://opentelemetry.io/docs/specs/otel/trace/api/#spancontext)
