---
title: "Distributing Prometheus Scrape Targets Across Collectors (Sharding)"
weight: 28
description: "Method for effectively distributing Prometheus scrape targets using sharding across multiple OpenTelemetry Collector instances."
---

**Question:**
Which method effectively distributes Prometheus scrape targets across multiple OpenTelemetry Collector instances to avoid duplicate scraping and out-of-order samples?

**Answer:**
Sharding endpoints by assigning each Collector to specific Kubernetes namespaces or workload labels

**Explanation:**
When running multiple OpenTelemetry Collector instances configured with the Prometheus Receiver to scrape targets (like pods or services), simply replicating the same scrape configuration across all Collectors will lead to duplicate scraping (each Collector scrapes the same target) and potential out-of-order sample issues in the backend (Prometheus). An effective method to distribute the load and avoid duplication is **target sharding**. This involves configuring each Collector instance to scrape only a *subset* of the total targets. In Kubernetes, this is commonly achieved by using Prometheus `relabel_configs` within the receiver configuration, often based on Kubernetes labels (like `kubernetes_namespace` or custom workload labels), to assign specific targets to specific Collector shards.

**Reference:**
[Prometheus Receiver Documentation - Relabeling/Sharding Examples](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/receiver/prometheusreceiver#kubernetes-service-discovery)
[Scaling and High Availability for Prometheus scraping](https://opentelemetry.io/docs/collector/deployment/prometheus/#scaling-and-high-availability)
