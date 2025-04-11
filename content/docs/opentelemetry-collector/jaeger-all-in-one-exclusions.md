---
title: "Components Excluded from Jaeger All-in-One Deployment"
weight: 27
description: "Identifying components typically not included in the single pod deployment strategy for Jaeger (All-in-One)."
---

**Question:**
When deploying Jaeger using the All-in-One strategy, which component is not included in the single pod?

**Answer:**
Prometheus Exporter

**Explanation:**
The Jaeger All-in-One deployment strategy is designed for development, testing, and small workloads. It bundles the core Jaeger backend components (Agent, Collector, Query, and typically an in-memory or Badger storage) into a single binary or container image, run as a single pod/process. While Jaeger *can* expose its own metrics in Prometheus format, the Prometheus Exporter itself is a separate component responsible for scraping metrics *from* other applications (or Jaeger) and exposing them *to* a Prometheus server. It's not a core part of the Jaeger backend functionality bundled in the All-in-One image.

**Reference:**
[Jaeger Documentation - Deployment Strategies](https://www.jaegertracing.io/docs/latest/deployment/#all-in-one)
