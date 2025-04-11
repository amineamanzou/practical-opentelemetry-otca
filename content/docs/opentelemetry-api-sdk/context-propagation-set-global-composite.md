---
title: "Setting a Global Composite Propagator (W3C + B3)"
weight: 38
description: "Describes the method for configuring a global composite text map propagator in OpenTelemetry."
---

This note explains how to configure OpenTelemetry to use multiple context propagation formats simultaneously (e.g., W3C Trace Context and B3) using a composite propagator.

## Setting a Global Composite Propagator

**Question:**
Which method is used to set a global composite propagator combining W3C Trace Context and B3 Propagators in OpenTelemetry?

**Answer:**
`propagators.set_global_textmap()` *(Note: Exact function name varies by language, e.g., `opentelemetry.propagate.set_global_textmap_propagator` in Python, `opentelemetry.propagation.setGlobalPropagator` in JS)*

**Explanation:**
OpenTelemetry supports multiple context propagation wire formats, with W3C Trace Context being the default standard and B3 being common for compatibility with systems like Zipkin. To support interoperability, applications often need to both inject and extract context using multiple formats. OpenTelemetry SDKs provide a mechanism to configure a *composite* `TextMapPropagator`. This composite propagator typically wraps instances of individual propagators (e.g., one for W3C, one for B3).

* When **injecting** context, the composite propagator calls `inject` on *all* its contained propagators, adding headers for each format (e.g., `traceparent`, `tracestate`, `b3`, `x-b3-traceid`, etc.).
* When **extracting** context, the composite propagator typically tries each contained propagator in order until one successfully extracts a valid context.

The exact method to set this global composite propagator varies by language SDK, but it generally involves creating the individual propagator instances, creating a composite instance that combines them, and then calling a global configuration function (like `set_global_textmap_propagator` or similar) to register it for use by the SDK's instrumentation.

**Reference:**
[OpenTelemetry Specification - Context Propagation API: Composite Propagator](https://opentelemetry.io/docs/specs/otel/context/api-propagators/#composite-propagator)
*Note: See language-specific SDK documentation for exact API calls (e.g., [Python](https://opentelemetry-python.readthedocs.io/en/latest/api/propagators.html#opentelemetry.propagate.set_global_textmap_propagator), [JavaScript](https://opentelemetry.io/docs/languages/js/propagation/))*
