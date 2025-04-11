---
title: "Challenge Addressed by Agent Collector for Ruby/PHP Environments"
weight: 29
description: "Understanding how deploying the OpenTelemetry Collector as an agent helps in environments with languages like Ruby or PHP."
---

**Question:**
Which challenge is effectively addressed by deploying the OpenTelemetry Collector as an agent in environments using programming languages like Ruby or PHP?

**Answer:**
Facilitating the collection of raw measurements and performing aggregation externally.

**Explanation:**
Some programming languages, like Ruby and PHP (especially in traditional web request models), might have limitations or performance implications when performing complex in-process telemetry processing, such as heavy metric aggregation or batching. Deploying an OpenTelemetry Collector agent (e.g., on the same host or as a sidecar) allows the application instrumentation (SDK) to focus on efficiently exporting raw or minimally processed telemetry data (like individual requests, raw measurements) over a fast local connection (like OTLP/gRPC or OTLP/HTTP). The agent then takes on the responsibility of batching, aggregation (e.g., calculating request rate/duration histograms from individual spans), and exporting to the backend, offloading this work from the application process.

**Reference:**
[Collector Deployment Modes - Agent](https://opentelemetry.io/docs/collector/deployment/#agent)
