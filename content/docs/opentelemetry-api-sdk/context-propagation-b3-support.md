---
title: "OpenTelemetry Support for B3 Propagation Format"
weight: 40
description: "Confirms OpenTelemetry's support for the B3 propagation format, commonly used by Zipkin."
---

This note confirms that the B3 context propagation format is supported by OpenTelemetry.

## OpenTelemetry Support for B3 Format

**Question:**
Which propagator format is commonly used by systems like Zipkin and is supported by OpenTelemetry?

**Answer:**
B3

**Explanation:**
B3 propagation is a context propagation format originally developed for the Zipkin distributed tracing system. It defines specific HTTP headers (like `X-B3-TraceId`, `X-B3-SpanId`, `X-B3-Sampled`, and potentially `X-B3-Flags` and `X-B3-ParentSpanId`, or a single `b3` header) to carry trace context. Because many systems adopted Zipkin and the B3 format before the W3C Trace Context standard emerged, OpenTelemetry includes built-in support for B3 propagation to ensure interoperability with these existing systems. Developers can configure OpenTelemetry SDKs to use the B3 propagator (often alongside W3C Trace Context via a composite propagator) for extracting and injecting context when communicating with services that expect the B3 format.

**Reference:**
[OpenTelemetry Specification - Propagators: B3](https://opentelemetry.io/docs/specs/otel/context/propagators/#b3)
