---
title: "Behavior When Creating a Meter with an Invalid Name"
weight: 36
description: "Describes the specified behavior of MeterProvider when requested to create a Meter with an invalid name."
---

This note explains what happens when attempting to create an OpenTelemetry Meter using a null or empty string as the name.

## Creating a Meter with Invalid Name

**Question:**
When creating a Meter using a MeterProvider, what happens if an invalid name (null or empty string) is specified?

**Answer:**
A working Meter is returned with the invalid name retained, and a message is logged.

**Explanation:**
The OpenTelemetry API specification defines requirements for the names provided when acquiring a `Meter` (or `Tracer`) from its respective provider. These names should typically correspond to the instrumentation scope (e.g., the library or module performing the instrumentation) and should not be null or empty. However, to align with the principle of API safety and avoiding exceptions, the specification dictates that if an invalid name (like null or an empty string) *is* provided:

1. The `MeterProvider` should still return a functional `Meter` instance (it might be a no-op Meter if no SDK is configured, but it will be a valid object).
2. The invalid name provided by the caller should be associated with the returned `Meter`.
3. An error or warning message should be logged (via the SDK's internal logging or error handling mechanism) indicating that an invalid name was used.

This ensures the application doesn't crash due to the invalid input, but the issue is still surfaced to developers via logs.

**Reference:**
[OpenTelemetry Specification - Metrics API: Acquiring a Meter](https://opentelemetry.io/docs/specs/otel/metrics/api/#get-a-meter) (Specifies behavior for invalid names)
