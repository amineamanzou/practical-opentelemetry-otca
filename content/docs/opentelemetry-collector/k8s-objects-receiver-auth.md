---
title: "Authentication for Kubernetes Objects Receiver"
weight: 35
description: "Identifying the typical authentication method used by the Kubernetes Objects Receiver to access the Kubernetes API."
---

**Question:**
In the OpenTelemetry Collector's configuration for collecting Kubernetes events, which authentication type is typically specified in the Kubernetes Objects Receiver to access the Kubernetes API?

**Answer:**
`serviceAccount`

**Explanation:**
The Kubernetes Objects Receiver (often part of `k8sclusterreceiver`) needs to query the Kubernetes API server to watch for events or other objects. When running within a Kubernetes cluster, the standard and recommended way to grant the Collector's pod the necessary permissions is via a Kubernetes `ServiceAccount`. The Collector configuration for the receiver would then typically specify `auth_type: serviceAccount` (or similar, depending on the exact receiver implementation). This tells the Collector to use the service account token automatically mounted into the pod (found at `/var/run/secrets/kubernetes.io/serviceaccount/token`) to authenticate its API requests. Other methods like kubeconfig exist but `serviceAccount` is idiomatic for in-cluster deployments.

**Reference:**
[Kubernetes Cluster Receiver - Authentication](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/receiver/k8sclusterreceiver#authentication) (Note: The question mentioned Kubernetes Objects Receiver, which is often a mode within the K8s Cluster Receiver)
