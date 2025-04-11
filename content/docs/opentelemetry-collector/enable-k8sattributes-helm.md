---
title: "Enabling Kubernetes Attributes Processor via Helm"
weight: 11
description: "Helm chart configuration required to enable the Kubernetes Attributes Processor in the OpenTelemetry Collector."
---

**Question:**
Which Helm chart configuration option must be enabled to activate the Kubernetes Attributes Processor in the OpenTelemetry Collector?

**Answer:**
`kubernetesAttributes.enabled = true`

**Explanation:**
When deploying the OpenTelemetry Collector using the official Helm chart (specifically the `opentelemetry-collector` chart), the Kubernetes Attributes processor is often included but disabled by default. To enable it, you need to set the `kubernetesAttributes.enabled` value to `true` in your Helm values file or via the `--set` flag during installation/upgrade.

**Reference:**
The specific configuration options are usually found within the Helm chart's documentation or `values.yaml` file itself.
[OpenTelemetry Collector Helm Chart](https://github.com/open-telemetry/opentelemetry-helm-charts/tree/main/charts/opentelemetry-collector)
[Kubernetes Attributes Processor Documentation](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/processor/k8sattributesprocessor)
