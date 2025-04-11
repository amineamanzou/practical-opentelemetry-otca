---
title: "Fundamentals of Observability"
weight: 1
description: "Explore the core concepts of observability, including telemetry signals (metrics, traces, logs), data collection, processing, and essential OpenTelemetry terminology."
---

This section covers the foundational knowledge required to understand observability and the role OpenTelemetry plays within it. It delves into the different types of telemetry data, how they are generated and used, and the core principles behind effective system monitoring and analysis.

## Fundamentals of Observability

{{% cards %}}
  {{% card title="Failed Questions for the fundamentals of observability" description="A list of failed questions for the fundamentals of observability domain to help focus study efforts." link="failed-questions" icon="book-open" %}}
  {{% card title="Benefits of Local Preprocessing with OpenTelemetry Agent" description="Explains scenarios where using an OpenTelemetry Agent (Collector) for local data preprocessing is advantageous." link="agent-local-preprocessing" icon="book-open" %}}
  {{% card title="Practices for Metric Discoverability and Comparison" description="Discusses OpenTelemetry best practices for defining metrics to enhance discoverability and ad-hoc comparison." link="metric-discoverability-practices" icon="book-open" %}}
  {{% card title="Naming Convention for system.process UpDownCounter" description="Specifies the OpenTelemetry preferred naming convention for an UpDownCounter tracking active processes." link="metric-naming-system-process-count" icon="book-open" %}}
  {{% card title="Metric Naming Conventions Regarding Pluralization" description="Explains OpenTelemetry's guidelines on using singular vs. plural nouns in metric names." link="metric-naming-pluralization" icon="book-open" %}}
  {{% card title="Preventing Metric Name Reuse" description="Outlines OpenTelemetry guidelines for checking existing configurations to prevent metric name reuse, especially with renaming." link="metric-naming-reuse-prevention" icon="book-open" %}}
  {{% card title="Characteristics of Semistructured Logs" description="Describes key characteristics of semistructured logs, focusing on pattern consistency and parsing requirements." link="semistructured-logs-characteristics" icon="book-open" %}}
  {{% card title="Defining Telemetry Data" description="Provides a definition of telemetry data focusing on its automatic collection and transmission for observability." link="telemetry-data-definition" icon="book-open" %}}
  {{% card title="Leveraging Performance Monitoring via Telemetry" description="Explains how the Performance Monitoring benefit of telemetry helps proactively identify and fix application issues." link="telemetry-benefits-proactive-debugging" icon="book-open" %}}
  {{% card title="Log Sources Difficult to Inject Trace Context Into" description="Identifies types of log sources where injecting OpenTelemetry trace context is typically not feasible." link="log-sources-without-trace-context" icon="book-open" %}}
  {{% card title="Span Relationships Based on Trace ID and Parent ID" description="Explains the relationship between spans sharing the same trace ID but having different parent IDs." link="span-relationships-trace-parent-id" icon="book-open" %}}
  {{% card title="Typical Network Telemetry Metrics" description="Lists examples of metrics commonly associated with network telemetry data, including device resource usage." link="network-telemetry-metrics-examples" icon="book-open" %}}
  {{% card title="Semantics-Preserving Metric Transformations" description="Discusses semantics-preserving data transformations allowed by the OpenTelemetry Metrics data model, including temporal reaggregation." link="metric-data-model-transformations" icon="book-open" %}}
  {{% card title="Example of a Kubernetes Failed Event Scenario" description="Provides examples of events or states in Kubernetes that signify critical failures, such as container crashes." link="kubernetes-failed-event-example" icon="book-open" %}}
  {{% card title="Essential Actions for Telemetry Data Privacy" description="Highlights essential actions to address data privacy concerns when collecting telemetry, emphasizing data minimization." link="telemetry-data-privacy-actions" icon="book-open" %}}
  {{% card title="Process of Trace Creation in OpenTelemetry" description="Explains the process of creating individual spans and linking them via context propagation to form traces." link="trace-creation-process" icon="book-open" %}}
{{% /cards %}}
