---
title: "Purpose of OpenTelemetry Collector as a Kubernetes Deployment"
weight: 33
description: "Understanding the use case for deploying the OpenTelemetry Collector as a Deployment (vs. DaemonSet) in Kubernetes."
---

**Question:**
What is the purpose of deploying the OpenTelemetry Collector as a Deployment in Kubernetes?

**Answer:**
To collect cluster-wide metrics and events.

**Explanation:**
In Kubernetes, a `Deployment` manages a replicated set of pods, suitable for stateless applications or centralized services. Deploying the OpenTelemetry Collector as a Deployment typically corresponds to the **Gateway** or **Collector** pattern. These centralized instances are ideal for:

* Receiving telemetry from agents (running as DaemonSets or sidecars).
* Performing cluster-wide aggregation or processing.
* Collecting cluster-level data (like Kubernetes events via `k8sclusterreceiver` or cluster-wide metrics).
* Handling export to backends, potentially with load balancing.

This contrasts with a `DaemonSet`, which runs one Collector pod per node (Agent pattern), primarily for collecting node-local or pod-local data.

**Reference:**
[Collector Deployment in Kubernetes - Deployment](https://opentelemetry.io/docs/collector/deployment/kubernetes/#deployment)
