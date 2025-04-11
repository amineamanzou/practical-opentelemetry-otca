---
title: "Failed Questions for the opentelemetry API and SDK domain"
weight: 1
description: "A list of failed questions for opentelemetry API and SDK domain to help focus study efforts."
---

This document organizes failed questions for the fundamentals of observability to help identify knowledge gaps and focus further study.

## Failed questions

- In OpenTelemetry's Metrics data model, what does the TimeSeries model represent?
  - How exporters should interpret the in-flight metrics data.
- According to OpenTelemetry's semantic conventions, what is the correct instrument name for measuring the fraction of memory in use relative to its limit?
  - system.memory.utilization
- Which practice should developers follow when implementing external callbacks in OpenTelemetry API methods to ensure robust error handling?
  - Handle all potential errors within the callback implementations to prevent unhandled exceptions.
- How can developers change the default error handling behavior in the OpenTelemetry SDK?
  - By registering custom error handlers following language-specific conventions.
- A developer needs to monitor the bidirectional data flow on a network interface. According to OpenTelemetry's naming conventions, which instrument name should they use?
  - system.network.io
- You want to disable specific instrumentation provided by the OpenTelemetry agent without modifying the agent's code. Which type of extension should you create?
  - An extension with new default settings.
- In OpenTelemetry's logging support, what is the primary purpose of a Log Appender or Bridge?
  - To enable logging libraries to emit logs into an OpenTelemetry LogRecordExporter.
- In OpenTelemetry, which attribute specifies the full path to the log file with all symbolic links resolved?
  - log.file.path_resolved
- A development team is using a vendor-provided implementation of the OpenTelemetry SDK for their application written in Python. According to OpenTelemetry specifications, what should they set the 'telemetry.sdk.name' attribute to?
  - The fully-qualified module name of the SDK's main entry point
- If you need to modify span attributes based on a specific database connection instance, which extension approach should you use?
  - Create an extension with new instrumentation that injects custom advice.
- Which of the following resource attributes can be configured via a dedicated environment variable according to OpenTelemetry semantic conventions?
  - service.name
- Which of the following is NOT a component of the SpanContext in OpenTelemetry?
  - SpanName
- In the OpenTelemetry JS SDK, when is it necessary to use manual context propagation instead of relying on automatic context propagation?
  - When communicating between services using a library without existing OpenTelemetry instrumentation.
- Which of the following environment variable substitutions is invalid according to the OpenTelemetry configuration data model?
  - ${1INVALID_VAR}
- Which of the following properties is NOT part of the Timeseries model in OpenTelemetry's metrics data model?
  - Instrument type
- According to OpenTelemetry Protocol (OTLP) producer recommendations, how should producers handle a conflict involving a non-identifying property such as the metric description?
  - Choose the longer description string
- When instrumenting a library intended to be consumed by a runnable binary, which OpenTelemetry components should you include as dependencies?
  - Only the OpenTelemetry API
- What benefit do Telemetry Schemas provide regarding the independent evolution of OpenTelemetry components?
  - They allow OpenTelemetry semantic conventions, telemetry sources, and consumers to evolve independently without breaking integration.
- How can you prevent OpenTelemetry SDK autoloading for specific request URLs such as health checks in PHP?
  - Including the URLs in OTEL_PHP_EXCLUDED_URLS environment variable.
- What is the role of Views in the OpenTelemetry API regarding metric aggregation?
  - To customize the aggregation method and select specific metric attributes to report.
- Which of the following fields is included in the Span Context in OpenTelemetry?
Trace ID
- Which of the following is NOT a type of package that each OpenTelemetry signal consists of?
  - Agent
- In the OpenTelemetry Protocol (OTLP) data model, how is a Sum point translated into the Timeseries model based on its monotonicity?
  - Translated into a Counter if monotonic, otherwise a Gauge
- In systems utilizing gRPC for communication, which OpenTelemetry feature is used for context propagation?
  - gRPC Metadata
- Which of the following properties is NOT considered identifying in the OpenTelemetry Protocol (OTLP) data model?
  - Metric stream's description
- Which of the following best describes OpenTelemetry's approach to handling errors within its API methods?
  - OpenTelemetry API methods handle errors internally and provide safe default values without throwing exceptions.
- When creating a Meter using a MeterProvider, what happens if an invalid name (null or empty string) is specified?
  - A working Meter is returned with the invalid name retained, and a message is logged.
- In the OpenTelemetry Protocol (OTLP) data model, how is a Sum data point translated into the Timeseries model based on its monotonicity?
  - Monotonic Sum is translated into a Counter, and non-monotonic Sum into a Gauge.
- Which method is used to set a global composite propagator combining W3C Trace Context and B3 Propagators in OpenTelemetry?
  - propagators.set_global_textmap()
- Why is it important to handle missing or corrupted context gracefully in OpenTelemetry?
  - To allow continued operation and enable logging and alerting.
- Which propagator format is commonly used by systems like Zipkin and is supported by OpenTelemetry?
  - B3

## Analysis

The failed questions highlight several key areas within the OpenTelemetry API and SDK domain that require deeper understanding:

- **Data Models (Metrics, OTLP):** Precise knowledge of the structure and behavior of the Metrics data model (e.g., TimeSeries, Sum point translation) and the OTLP data model (e.g., identifying vs. non-identifying properties) is essential.
- **Semantic Conventions:** Mastery of specific, standardized names for instruments (e.g., `system.memory.utilization`), resources (e.g., `service.name`), and log attributes (e.g., `log.file.path_resolved`) is frequently tested.
- **API/SDK Behavior:** Understanding the internal error handling guarantees of the API, how to customize SDK error handling, and the defined behavior for edge cases (like invalid inputs) is crucial.
- **Configuration & Extensibility:** Knowledge of configuration methods, particularly via environment variables (including syntax and precedence) and language-specific settings (e.g., `OTEL_PHP_EXCLUDED_URLS`), is important. Understanding how SDK extensions modify behavior is also key.
- **Context Propagation:** This is a major topic, covering the differences between automatic and manual propagation, the mechanisms used (e.g., gRPC Metadata), standard formats (W3C Trace Context, B3), combining propagators, and robust handling of context issues.
- **Core Concepts:** A clear grasp of fundamental concepts like the components of a `SpanContext`, the role of Log Appenders/Bridges, the distinction between API and SDK dependencies, the purpose of Views, and the function of Telemetry Schemas is necessary.

**Recommendations:**

- **Study the Specifications:** Thoroughly review the official OpenTelemetry specifications, focusing on the data models, semantic conventions, configuration, context propagation, and error handling sections.
- **Review Language SDK Details:** Consult the documentation for the specific language SDKs you work with to understand implementation details related to configuration, context propagation, and extensions.
- **Focus on Precision:** Pay close attention to the exact names, fields, and behavioral descriptions outlined in the documentation, as the exam questions often test this level of detail.
- **Understand API vs. SDK:** Solidify your understanding of the roles and guarantees of the API versus the SDK.

Refer to the official [OpenTelemetry Documentation](https://opentelemetry.io/docs/specs/otel/) for detailed information on these topics.
