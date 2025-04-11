---
title: "Semantic Convention for Telemetry SDK Name (Python)"
weight: 18
description: "Explains how to set the telemetry.sdk.name attribute for a Python OpenTelemetry SDK implementation."
---

This note details the correct value for the `telemetry.sdk.name` resource attribute when using a Python OpenTelemetry SDK, as per semantic conventions.

## Semantic Convention: telemetry.sdk.name (Python)

**Question:**
A development team is using a vendor-provided implementation of the OpenTelemetry SDK for their application written in Python. According to OpenTelemetry specifications, what should they set the `telemetry.sdk.name` attribute to?

**Answer:**
The fully-qualified module name of the SDK's main entry point.

**Explanation:**
The `telemetry.sdk.name` resource attribute identifies the specific OpenTelemetry SDK implementation being used. Semantic conventions dictate the format for this attribute. For Python SDKs, the value should be the fully-qualified Python module name that serves as the main entry point or identifier for that specific SDK distribution. For example, if using the standard `opentelemetry-sdk` package, this might be `opentelemetry.sdk`. If using a vendor-specific distribution, it would be the corresponding module name for that vendor's package.

**Reference:**
[OpenTelemetry Semantic Conventions - Resource Attributes: telemetry.sdk.name](https://opentelemetry.io/docs/specs/semconv/resource/#telemetry-sdk)
*Note: The specific value depends on the Python package used.*
