---
title: "Unsupported OpenTelemetry Collector Operation Modes"
weight: 17
description: "Identifying operation modes not supported by the standard OpenTelemetry Collector deployments."
---

**Question:**
Which mode of operation does the OpenTelemetry Collector NOT support?

**Answer:**
Serverless mode, integrating directly with cloud functions.

**Explanation:**
The OpenTelemetry Collector is typically deployed as a standalone process, either as an agent (often a sidecar or DaemonSet) or a gateway (usually a Deployment). While it can *receive* data from serverless functions (e.g., via OTLP), it doesn't operate *as* a serverless function itself. There isn't a built-in mode where the Collector binary integrates directly into the lifecycle or execution environment of platforms like AWS Lambda or Google Cloud Functions in the way the question implies.

**Reference:**
Review the standard deployment patterns:
[Collector Deployment Modes](https://opentelemetry.io/docs/collector/deployment/#deployment-modes)
