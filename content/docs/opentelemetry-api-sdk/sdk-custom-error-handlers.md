---
title: "Customizing OpenTelemetry SDK Error Handling"
weight: 13
description: "Explains how to modify the default error handling behavior within the OpenTelemetry SDK."
---

This note describes the mechanism for customizing error handling in the OpenTelemetry SDK.

## Customizing SDK Error Handling

**Question:**
How can developers change the default error handling behavior in the OpenTelemetry SDK?

**Answer:**
By registering custom error handlers following language-specific conventions.

**Explanation:**
While the OpenTelemetry API aims to handle errors internally and avoid throwing exceptions, the SDK implementations often provide mechanisms to customize this behavior. This typically involves registering custom error handler functions or classes that the SDK will invoke when it encounters internal issues (e.g., problems exporting telemetry). The exact method for registering these handlers (e.g., specific configuration options, interfaces to implement) varies depending on the programming language SDK being used. Developers should consult the documentation for their specific language SDK.

**Reference:**
[OpenTelemetry Specification - Error Handling](https://opentelemetry.io/docs/specs/otel/error-handling/) (Provides general principles)
*Note: Specific implementation details are found in language-specific SDK documentation.*
