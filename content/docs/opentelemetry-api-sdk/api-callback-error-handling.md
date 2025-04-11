---
title: "Error Handling in OpenTelemetry API External Callbacks"
weight: 12
description: "Best practices for error handling within external callbacks used by the OpenTelemetry API."
---

This note outlines the recommended practice for handling errors within developer-provided callbacks invoked by the OpenTelemetry API.

## Error Handling for API Callbacks

**Question:**
Which practice should developers follow when implementing external callbacks in OpenTelemetry API methods to ensure robust error handling?

**Answer:**
Handle all potential errors within the callback implementations to prevent unhandled exceptions.

**Explanation:**
The OpenTelemetry API itself is designed to be safe and generally avoids throwing exceptions that could crash the application. However, when the API calls external code provided by the user (e.g., in custom processors, exporters, or other extensions), it cannot guarantee the safety of that external code. Therefore, developers must implement robust error handling (like try-catch blocks or equivalent mechanisms) within their callback functions. This prevents errors in the custom code from propagating uncaught, which could otherwise lead to application instability or crashes.

**Reference:**
[OpenTelemetry Specification - Error Handling](https://opentelemetry.io/docs/specs/otel/error-handling/) (While focusing on API/SDK internal handling, the principle that external code is the developer's responsibility regarding exceptions applies.)
