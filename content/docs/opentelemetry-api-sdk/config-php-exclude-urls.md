---
title: "Excluding URLs from PHP Auto-Instrumentation"
weight: 28
description: "Describes how to prevent OpenTelemetry SDK autoloading for specific URLs in PHP using environment variables."
---

This note explains the method for excluding specific request URLs, like health checks, from OpenTelemetry auto-instrumentation in PHP applications.

## Excluding URLs from PHP Auto-Instrumentation

**Question:**
How can you prevent OpenTelemetry SDK autoloading for specific request URLs such as health checks in PHP?

**Answer:**
Including the URLs in the `OTEL_PHP_EXCLUDED_URLS` environment variable.

**Explanation:**
OpenTelemetry PHP auto-instrumentation, typically enabled via an SDK autoloader (`sdk_autoregister.php`), instruments incoming HTTP requests by default. However, for certain endpoints like health checks or static file serving, generating traces might be unnecessary noise. The PHP SDK provides the `OTEL_PHP_EXCLUDED_URLS` environment variable to specify a comma-separated list of URL paths (or path prefixes) that should be excluded from automatic tracing. Requests matching these paths will not trigger the SDK's request instrumentation.

**Reference:**
[OpenTelemetry PHP SDK Documentation - sdk-autoregister.php](https://opentelemetry.io/docs/languages/php/automatic/#sdk-autoregisterphp) (Mentions exclusion capabilities, often detailed further in specific configuration options or environment variables documentation for the SDK/Extension)
*Note: Specific environment variable names can sometimes change; always refer to the latest official PHP SDK documentation.*
