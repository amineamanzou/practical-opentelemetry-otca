---
title: "Kubernetes Attributes Processor for Metadata Enrichment"
weight: 15
description: "Using the k8sattributes processor to automatically add Kubernetes metadata to telemetry data."
---

**Question:**
Which OpenTelemetry Collector processor should be configured to automatically add Kubernetes-specific metadata, such as pod name and node name, to incoming telemetry data?

**Answer:**
`k8sattributes` Processor

**Explanation:**
The `k8sattributes` processor (Kubernetes Attributes Processor) is designed specifically for Kubernetes environments. When included in a pipeline, it interacts with the Kubernetes API server (often via the Downward API or direct API access) to discover metadata associated with the source of the telemetry data (e.g., the pod IP address). It then enriches the data by adding attributes like `k8s.pod.name`, `k8s.namespace.name`, `k8s.node.name`, etc.

**Reference:**
[Kubernetes Attributes Processor Documentation](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/processor/k8sattributesprocessor)
