---
title: "Configuring service.name via Environment Variable"
weight: 20
description: "Describes configuring the service.name resource attribute using the OTEL_SERVICE_NAME environment variable."
---

This note explains how the `service.name` resource attribute can be configured using a dedicated environment variable according to OpenTelemetry conventions.

## Configuring service.name via Environment Variable

**Question:**
Which of the following resource attributes can be configured via a dedicated environment variable according to OpenTelemetry semantic conventions?

**Answer:**
`service.name`

**Explanation:**
OpenTelemetry defines a standard set of resource attributes that describe the entity producing telemetry (e.g., a service, library, process). The `service.name` attribute is arguably the most important, identifying the logical service. To simplify configuration, OpenTelemetry specifies that this attribute can be set using the `OTEL_SERVICE_NAME` environment variable. This provides a standard, language-agnostic way to configure the service name without needing code changes or complex configuration files. Other resource attributes might also be configurable via environment variables (e.g., `OTEL_RESOURCE_ATTRIBUTES`), but `service.name` has its own dedicated variable.

**Reference:**
[OpenTelemetry Specification - Resource Semantic Conventions: Service](https://opentelemetry.io/docs/specs/semconv/resource/#service)
[OpenTelemetry Specification - Environment Variable Configuration: OTEL_SERVICE_NAME](https://opentelemetry.io/docs/specs/otel/configuration/sdk-environment-variables/#general-sdk-configuration)
