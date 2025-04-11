---
title: "OpenTelemetry Dependencies for Instrumented Libraries"
weight: 26
description: "Specifies the correct OpenTelemetry dependency for libraries intended for consumption by other applications."
---

This note clarifies which OpenTelemetry component should be included as a dependency when instrumenting a library.

## Library Dependencies: API Only

**Question:**
When instrumenting a library intended to be consumed by a runnable binary, which OpenTelemetry components should you include as dependencies?

**Answer:**
Only the OpenTelemetry API

**Explanation:**
Libraries (e.g., database clients, HTTP frameworks, utility packages) should only depend on the OpenTelemetry **API** package (`opentelemetry-api` in most languages). The API defines the interfaces for creating traces, metrics, and logs (e.g., `Tracer`, `Meter`, `Logger`, `Span`). It contains no concrete implementation or configuration logic. The final application (the runnable binary) that *uses* the library is responsible for including the OpenTelemetry **SDK** package (`opentelemetry-sdk`). The SDK provides the actual implementation of the API interfaces, handles sampling, processing, and exporting of telemetry. This separation prevents dependency conflicts if the final application wants to use a different SDK implementation (e.g., a vendor distribution) or configure the SDK differently than the library might assume. The library instruments against the stable API, and the application wires it up with an SDK at runtime.

**Reference:**
[OpenTelemetry Concepts - API vs SDK](https://opentelemetry.io/docs/concepts/api-sdk/)
[OpenTelemetry Documentation - Library Authors Guide](https://opentelemetry.io/docs/instrumentation/libraries/)
