---
title: "OpAMP Client Implementation Methods"
weight: 22
description: "Understanding how the client side of the OpAMP (Open Agent Management Protocol) can be implemented relative to the OpenTelemetry Collector."
---

**Question:**
In an OpAMP setup, how can the OpAMP client side be implemented?

**Answer:**
Both in-process within the Collector or out-of-process using a supervisor

**Explanation:**
OpAMP allows for remote management of OpenTelemetry agents like the Collector. The OpAMP client logic, which communicates with the OpAMP server, can be integrated in two main ways:

1. **In-process:** The OpAMP client code runs directly within the OpenTelemetry Collector process itself. This is often achieved using specific Collector extensions or built-in capabilities.
2. **Out-of-process:** A separate agent or supervisor process runs alongside the Collector. This supervisor handles the OpAMP communication and manages the Collector process based on instructions from the OpAMP server.

**Reference:**
[OpAMP Support in Collector](https://opentelemetry.io/docs/collector/management/opamp/)
