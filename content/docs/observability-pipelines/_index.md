---
title: "Observability Pipelines"
weight: 1
description: "Details on configuring, managing, and debugging OpenTelemetry observability pipelines, primarily focusing on the Collector."
---

This section covers the setup, configuration, and maintenance aspects of OpenTelemetry observability pipelines, with a focus on the OpenTelemetry Collector and related concepts.

{{< cards >}}
  {{< card link="debugging-details/exponentialhistogram-merging-zero-threshold" title="Merging ExponentialHistograms with Different Zero Thresholds" icon="ScaleIcon" >}}
    Explains the specification for merging ExponentialHistograms when their zero_threshold values differ.
  {{< /card >}}
  {{< card link="debugging-details/exponentialhistogram-zero-count-purpose" title="Purpose of the Zero Count Bucket in ExponentialHistogram" icon="InformationCircleIcon" >}}
    Defines the role of the zero_count bucket within an OpenTelemetry ExponentialHistogram.
  {{< /card >}}
  {{< card link="debugging-details/enabling-zpages-kubernetes" title="Enabling zPages for Collector Debugging in Kubernetes" icon="BugAntIcon" >}}
    Details the configuration required to enable the zPages extension for the OpenTelemetry Collector in Kubernetes.
  {{< /card >}}
  {{< card link="debugging-details/schema-file-schema-url" title="Schema URL Requirement in OpenTelemetry Schema Files" icon="LinkIcon" >}}
    Explains the rule governing the schema_url field within an OpenTelemetry Schema File.
  {{< /card >}}
  {{< card link="debugging-details/transform-processor-context-benefit" title="Benefit of Context Association in the Transform Processor" icon="CogIcon" >}}
    Explains the performance advantage of using correct contexts in the OpenTelemetry Transform Processor.
  {{< /card >}}
{{< /cards >}}
