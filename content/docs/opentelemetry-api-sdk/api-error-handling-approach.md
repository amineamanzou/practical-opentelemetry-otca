---
title: "OpenTelemetry API Error Handling Approach"
weight: 35
description: "Describes the general approach OpenTelemetry API methods take towards handling internal errors."
---

This note explains the design philosophy behind error handling within the core OpenTelemetry API methods.

## OpenTelemetry API Error Handling Approach

**Question:**
Which of the following best describes OpenTelemetry's approach to handling errors within its API methods?

**Answer:**
OpenTelemetry API methods handle errors internally and provide safe default values without throwing exceptions.

**Explanation:**
A core design goal of the OpenTelemetry API is to be safe to use, even if the SDK is not configured or encounters issues. Instrumenting code with API calls (e.g., `tracer.start_span()`, `meter.create_counter()`, `span.set_attribute()`) should not cause the application to crash. Therefore, the API methods themselves are specified to handle potential internal errors gracefully. This typically means:

* They avoid throwing exceptions back to the caller.
* If an operation cannot be completed (e.g., due to no SDK being configured), they often return no-op implementations (like a non-recording span) or safe default values.
* Error reporting might happen internally via logging or dedicated error handlers within the SDK, but the application flow isn't interrupted by exceptions from the API call itself.

This makes it safe for library authors to add instrumentation using the API without worrying about breaking applications that consume the library but haven't configured OpenTelemetry.

**Reference:**
[OpenTelemetry Specification - Error Handling](https://opentelemetry.io/docs/specs/otel/error-handling/)
[OpenTelemetry Specification - API Guarantees](https://opentelemetry.io/docs/specs/otel/overview/#api-guarantees)
