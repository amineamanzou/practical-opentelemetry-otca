---
title: "OpenTelemetry API and SDK"
weight: 1
description: "Detailed notes on specific questions regarding the OpenTelemetry API, SDK, OTLP, Semantic Conventions, and related concepts for OTCA preparation."
---

## OpenTelemetry API and SDK

This section contains atomic notes addressing specific questions about the OpenTelemetry API and SDK domain, based on previously failed OTCA exam questions. Each note focuses on a single concept or question.

{{< cards >}}
  {{< card link="metrics-timeseries-model" title="OpenTelemetry Metrics TimeSeries Model" icon="code" subtitle="Explains the purpose of the TimeSeries model within the OpenTelemetry Metrics data model." >}}
  {{< card link="semconv-system-memory-utilization" title="Semantic Convention for System Memory Utilization" icon="code" subtitle="Defines the standard OpenTelemetry instrument name for memory utilization." >}}
  {{< card link="api-callback-error-handling" title="Error Handling in OpenTelemetry API External Callbacks" icon="code" subtitle="Best practices for error handling within external callbacks used by the OpenTelemetry API." >}}
  {{< card link="sdk-custom-error-handlers" title="Customizing OpenTelemetry SDK Error Handling" icon="code" subtitle="Explains how to modify the default error handling behavior within the OpenTelemetry SDK." >}}
  {{< card link="semconv-system-network-io" title="Semantic Convention for System Network IO" icon="code" subtitle="Defines the standard OpenTelemetry instrument name for bidirectional network traffic." >}}
  {{< card link="agent-disable-instrumentation-extension" title="Disabling Specific Agent Instrumentation via Extension/Configuration" icon="code" subtitle="Explains how to disable specific instrumentation provided by an OpenTelemetry agent/auto-instrumentation." >}}
  {{< card link="logging-log-appender-bridge" title="Role of OpenTelemetry Log Appenders and Bridges" icon="code" subtitle="Explains the purpose of Log Appenders (or Bridges) in OpenTelemetry logging." >}}
  {{< card link="semconv-log-file-path-resolved" title="Semantic Convention for Resolved Log File Path" icon="code" subtitle="Defines the OpenTelemetry semantic attribute for the resolved log file path." >}}
  {{< card link="semconv-telemetry-sdk-name-python" title="Semantic Convention for Telemetry SDK Name (Python)" icon="code" subtitle="Explains how to set the telemetry.sdk.name attribute for a Python OpenTelemetry SDK implementation." >}}
  {{< card link="extension-modify-span-attributes-advice" title="Modifying Span Attributes via Instrumentation Extension" icon="code" subtitle="Explains using extensions with custom advice to modify span attributes based on specific instances." >}}
  {{< card link="config-env-var-service-name" title="Configuring service.name via Environment Variable" icon="code" subtitle="Describes configuring the service.name resource attribute using the OTEL_SERVICE_NAME environment variable." >}}
  {{< card link="trace-span-context-components" title="Components of the OpenTelemetry SpanContext" icon="code" subtitle="Lists the required components of the OpenTelemetry SpanContext." >}}
  {{< card link="context-propagation-manual-js" title="Necessity of Manual Context Propagation (JS SDK)" icon="code" subtitle="Explains when manual context propagation is required with the OpenTelemetry JS SDK." >}}
  {{< card link="config-invalid-env-var-substitution" title="Invalid Environment Variable Substitution Syntax" icon="code" subtitle="Identifies invalid syntax for environment variable substitution in OpenTelemetry configuration." >}}
  {{< card link="metrics-timeseries-model-exclusions" title="Properties Not Part of the Metrics TimeSeries Model" icon="code" subtitle="Identifies properties that are not part of the OpenTelemetry Metrics TimeSeries model." >}}
  {{< card link="otlp-conflict-non-identifying-property" title="OTLP Conflict Resolution for Non-Identifying Properties" icon="code" subtitle="Describes the recommended OTLP producer behavior when handling conflicts in non-identifying properties like description." >}}
  {{< card link="library-dependencies-api-only" title="OpenTelemetry Dependencies for Instrumented Libraries" icon="code" subtitle="Specifies the correct OpenTelemetry dependency for libraries intended for consumption by other applications." >}}
  {{< card link="telemetry-schema-benefits" title="Benefits of OpenTelemetry Telemetry Schemas" icon="code" subtitle="Explains how Telemetry Schemas facilitate independent evolution of OpenTelemetry components." >}}
  {{< card link="config-php-exclude-urls" title="Excluding URLs from PHP Auto-Instrumentation" icon="code" subtitle="Describes how to prevent OpenTelemetry SDK autoloading for specific URLs in PHP using environment variables." >}}
  {{< card link="metrics-views-role" title="Role of Views in OpenTelemetry Metric Aggregation" icon="code" subtitle="Explains the function of Views in customizing metric aggregation and attribute selection within the OpenTelemetry API/SDK." >}}
  {{< card link="trace-span-context-trace-id" title="Trace ID in OpenTelemetry SpanContext" icon="code" subtitle="Confirms that Trace ID is a required component of the OpenTelemetry SpanContext." >}}
  {{< card link="signals-package-types-exclusions" title="Package Types Not Part of OpenTelemetry Signals" icon="code" subtitle="Identifies package types that are not considered fundamental components of an OpenTelemetry signal." >}}
  {{< card link="otlp-sum-to-timeseries-monotonicity" title="OTLP Sum Point Translation to TimeSeries Based on Monotonicity" icon="code" subtitle="Explains how OTLP Sum data points are translated into the TimeSeries model depending on their monotonicity." >}}
  {{< card link="context-propagation-grpc-metadata" title="OpenTelemetry Context Propagation using gRPC Metadata" icon="code" subtitle="Explains the use of gRPC Metadata for OpenTelemetry context propagation." >}}
  {{< card link="otlp-non-identifying-properties-description" title="Non-Identifying Properties in OTLP Data Model (Metric Description)" icon="code" subtitle="Identifies metric stream description as a non-identifying property in the OTLP data model." >}}
  {{< card link="api-error-handling-approach" title="OpenTelemetry API Error Handling Approach" icon="code" subtitle="Describes the general approach OpenTelemetry API methods take towards handling internal errors." >}}
  {{< card link="api-meter-invalid-name" title="Behavior When Creating a Meter with an Invalid Name" icon="code" subtitle="Describes the specified behavior of MeterProvider when requested to create a Meter with an invalid name." >}}
  {{< card link="otlp-sum-translation-monotonic-vs-nonmonotonic" title="OTLP Sum Translation: Monotonic vs Non-monotonic" icon="code" subtitle="Specifies the translation of monotonic and non-monotonic OTLP Sum points to the TimeSeries model (Counter/Gauge)." >}}
  {{< card link="context-propagation-set-global-composite" title="Setting a Global Composite Propagator (W3C + B3)" icon="code" subtitle="Describes the method for configuring a global composite text map propagator in OpenTelemetry." >}}
  {{< card link="context-propagation-graceful-handling" title="Importance of Graceful Handling of Missing/Corrupted Context" icon="code" subtitle="Explains why gracefully handling missing or corrupted context during propagation is important." >}}
  {{< card link="context-propagation-b3-support" title="OpenTelemetry Support for B3 Propagation Format" icon="code" subtitle="Confirms OpenTelemetry's support for the B3 propagation format, commonly used by Zipkin." >}}
{{< /cards >}}
