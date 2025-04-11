---
title: "Disabling Specific Agent Instrumentation via Extension/Configuration"
weight: 15
description: "Explains how to disable specific instrumentation provided by an OpenTelemetry agent/auto-instrumentation."
---

This note discusses methods for disabling specific instrumentation modules within an OpenTelemetry agent or auto-instrumentation setup without modifying the agent code itself.

## Disabling Specific Agent Instrumentation

**Question:**
You want to disable specific instrumentation provided by the OpenTelemetry agent without modifying the agent's code. Which type of extension should you create?

**Answer:**
An extension with new default settings. *(Note: This is often achieved via configuration rather than a code extension)*

**Explanation:**
Disabling specific instrumentation provided by OpenTelemetry auto-instrumentation (agents) is typically done through configuration settings, not necessarily by creating a code "extension". Most agents allow disabling specific instrumenters (e.g., for HTTP clients, database libraries) via environment variables or configuration files. For example, in the Java agent, you might set `OTEL_INSTRUMENTATION_JDBC_ENABLED=false`. While the answer mentions "an extension with new default settings," the practical mechanism is usually overriding default configuration values to disable the undesired instrumentation. The concept is to alter the agent's behavior without altering its core code.

**Reference:**

* [OpenTelemetry Specification - SDK Configuration](https://opentelemetry.io/docs/specs/otel/configuration/sdk-configuration/) (General configuration principles)
* *Refer to specific language agent documentation for exact configuration options (e.g., [Java Agent Configuration](https://opentelemetry.io/docs/languages/java/automatic/agent-config/), [Python SDK Configuration](https://opentelemetry.io/docs/languages/python/automatic/configuration/))*
