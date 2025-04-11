---
title: "Process of Trace Creation in OpenTelemetry"
weight: 23
description: "Explains the process of creating individual spans and linking them via context propagation to form traces."
---

This note describes the fundamental process by which OpenTelemetry creates distributed traces: generating individual spans and linking them together across process boundaries.

## Process of Trace Creation

**Question:** In OpenTelemetry, which process involves creating individual spans and linking them to form a complete trace?

**Answer Principle:** Trace creation involves **instrumentation** (using the OpenTelemetry API/SDK to create individual spans representing units of work) and **context propagation** (passing the `trace_id` and parent `span_id` across process boundaries, often via HTTP headers or messaging metadata, to link spans into a single trace).

**Explanation:**
A distributed trace visualizes the path of a request as it travels through various services. This is achieved through two core mechanisms:

1. **Span Creation (Instrumentation):**
    - Code within each service is instrumented using the OpenTelemetry API/SDK.
    - When a service receives a request or starts a significant unit of work, it uses the SDK to:
        - Check if incoming context exists (via context propagation).
        - Start a new `Span`.
        - If no incoming context, a new `trace_id` is generated (this span becomes the root span or the root of a sub-trace).
        - If incoming context exists, the new span inherits the `trace_id` and sets its `parent_id` to the `span_id` from the incoming context.
    - Attributes (tags, metadata) and events (logs within the span) are added.
    - The `Span` is ended when the unit of work completes.

2. **Context Propagation:**
    - Before a service makes a call to another service (e.g., via HTTP, RPC, message queue), it uses the OpenTelemetry SDK to *inject* the current trace context (`trace_id`, `span_id` of the current span) into the outgoing request (e.g., as W3C Trace Context headers `traceparent` and `tracestate`).
    - The receiving service uses the SDK to *extract* this context from the incoming request.
    - This extracted context is then used when creating the next span (as described in step 1), establishing the parent-child link.

By creating spans locally within each service and propagating the context between services, OpenTelemetry links these individual spans together into a complete, distributed trace.

**Reference:**

- OpenTelemetry Documentation: [Traces - Concepts](https://opentelemetry.io/docs/concepts/signals/traces/)
- OpenTelemetry Documentation: [Context Propagation](https://opentelemetry.io/docs/concepts/context-propagation/)
- OpenTelemetry Documentation: [API Specification - Trace API](https://opentelemetry.io/docs/specs/otel/trace/api/)
- W3C Trace Context Specification: [Trace Context](https://www.w3.org/TR/trace-context/)
