---
title: "Modifying Span Attributes via Instrumentation Extension"
weight: 19
description: "Explains using extensions with custom advice to modify span attributes based on specific instances."
---

This note describes the approach of using OpenTelemetry extensions, potentially involving custom advice or instrumentation, to modify span attributes dynamically.

## Modifying Span Attributes with Extensions

**Question:**
If you need to modify span attributes based on a specific database connection instance, which extension approach should you use?

**Answer:**
Create an extension with new instrumentation that injects custom advice.

**Explanation:**
Standard OpenTelemetry auto-instrumentation provides generic attribute collection. To add or modify attributes based on runtime specifics, such as the details of a particular database connection instance *after* the standard instrumentation has run, you often need to extend or modify the instrumentation behavior. In environments like Java bytecode instrumentation, "advice" refers to code injected before, after, or around existing methods. Creating an extension that injects custom advice into the relevant database connection or query execution methods allows you to access the connection instance details and add them as attributes to the current span. The exact mechanism (e.g., using libraries like Byte Buddy in Java, monkey-patching in Python, specific SDK extension points) depends on the language and environment.

**Reference:**

* [OpenTelemetry Concepts - Extending the SDK](https://opentelemetry.io/docs/concepts/sdk-extensions/) (General concept)
* *Specific mechanisms are detailed in language agent/SDK documentation (e.g., Java Extensions).*
