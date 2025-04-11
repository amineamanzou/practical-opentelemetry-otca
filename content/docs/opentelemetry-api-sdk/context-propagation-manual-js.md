---
title: "Necessity of Manual Context Propagation (JS SDK)"
weight: 22
description: "Explains when manual context propagation is required with the OpenTelemetry JS SDK."
---

This note describes scenarios where automatic context propagation in the OpenTelemetry JavaScript SDK is insufficient and manual propagation becomes necessary.

## Manual Context Propagation Need (JS SDK)

**Question:**
In the OpenTelemetry JS SDK, when is it necessary to use manual context propagation instead of relying on automatic context propagation?

**Answer:**
When communicating between services using a library without existing OpenTelemetry instrumentation.

**Explanation:**
The OpenTelemetry JavaScript SDK provides automatic context propagation for many common asynchronous operations and networking libraries (like `fetch`, `XMLHttpRequest`, Node.js `http`). However, this automatic propagation relies on instrumentation patching these libraries. If you use a communication mechanism (e.g., a specific WebSocket library, a custom RPC protocol, a message queue client) that does *not* have built-in or available OpenTelemetry instrumentation, the context (TraceId, SpanId, etc.) will not be automatically injected into outgoing requests or extracted from incoming ones. In these cases, developers must manually use the Propagation API (`inject` and `extract` methods) to serialize the context into the message headers or payload and deserialize it on the receiving side to maintain the trace continuity.

**Reference:**
[OpenTelemetry Documentation - JavaScript SDK: Context Propagation](https://opentelemetry.io/docs/languages/js/propagation/)
[OpenTelemetry Specification - Context Propagation API](https://opentelemetry.io/docs/specs/otel/context/api-propagators/)
