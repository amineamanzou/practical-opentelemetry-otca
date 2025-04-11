---
title: "Importance of Graceful Handling of Missing/Corrupted Context"
weight: 39
description: "Explains why gracefully handling missing or corrupted context during propagation is important."
---

This note discusses the rationale behind the requirement to handle missing or corrupted propagation context gracefully in OpenTelemetry.

## Graceful Handling of Missing/Corrupted Context

**Question:**
Why is it important to handle missing or corrupted context gracefully in OpenTelemetry?

**Answer:**
To allow continued operation and enable logging and alerting.

**Explanation:**
When an instrumented service receives a request, it attempts to extract context information (like Trace ID, Span ID) using a propagator. This context might be missing (if the caller wasn't instrumented) or corrupted (e.g., malformed headers). OpenTelemetry specifies that implementations MUST handle these situations gracefully:

* **Continued Operation:** The receiving service should not crash or fail simply because the incoming context is invalid or absent. It should continue processing the request.
* **Start a New Trace:** If no valid context is found, the service should typically start a *new* trace for the work it performs in response to the request. This ensures that the operation is still monitored, even if it can't be linked to an upstream trace.
* **Logging/Alerting:** While not crashing, the implementation *should* ideally log a warning or error when invalid context is detected. This helps operators diagnose propagation issues (e.g., misconfigured proxies, incompatible propagator formats between services).

Robustly handling these cases prevents cascading failures and ensures observability data is still generated, even if traces are occasionally disconnected.

**Reference:**
[OpenTelemetry Specification - Context Propagation API: Error Handling](https://opentelemetry.io/docs/specs/otel/context/api-propagators/#error-handling)
