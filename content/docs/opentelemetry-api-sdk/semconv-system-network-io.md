---
title: "Semantic Convention for System Network IO"
weight: 14
description: "Defines the standard OpenTelemetry instrument name for bidirectional network traffic."
---

This note specifies the correct OpenTelemetry semantic convention instrument name for measuring bidirectional network data flow.

## Semantic Convention: System Network IO

**Question:**
A developer needs to monitor the bidirectional data flow on a network interface. According to OpenTelemetry's naming conventions, which instrument name should they use?

**Answer:**
`system.network.io`

**Explanation:**
The OpenTelemetry semantic conventions define standard names for common metrics. `system.network.io` is the instrument name used to measure the amount of data transmitted and received over a network interface. This is typically reported as a Sum (Counter) in bytes. Using standardized names like this ensures consistency and allows observability platforms to correctly interpret and visualize the data, regardless of the source application or library.

**Reference:**
[OpenTelemetry Semantic Conventions - System Network Metrics: system.network.io](https://opentelemetry.io/docs/specs/semconv/system/network/#metric-systemnetworkio)
