---
title: "OpenTelemetry Context Propagation using gRPC Metadata"
weight: 33
description: "Explains the use of gRPC Metadata for OpenTelemetry context propagation."
---

This note identifies gRPC Metadata as the mechanism used for propagating OpenTelemetry context in gRPC-based communication.

## Context Propagation via gRPC Metadata

**Question:**
In systems utilizing gRPC for communication, which OpenTelemetry feature is used for context propagation?

**Answer:**
gRPC Metadata

**Explanation:**
gRPC provides a mechanism called "Metadata" for sending key-value pairs of information alongside a gRPC request, separate from the main request/response payload. OpenTelemetry leverages this feature for context propagation. When an instrumented gRPC client makes a call, the OpenTelemetry instrumentation uses a configured `TextMapPropagator` (like W3C Trace Context or B3) to inject the current `SpanContext` (Trace ID, Span ID, etc.) into the gRPC Metadata, typically as standard HTTP header keys. On the server side, the OpenTelemetry gRPC instrumentation extracts these values from the incoming Metadata using the same propagator, recreating the `SpanContext` and allowing the server-side span to be linked to the client-side span as its parent.

**Reference:**
[OpenTelemetry Specification - Semantic Conventions for gRPC](https://opentelemetry.io/docs/specs/semconv/rpc/grpc/) (Describes conventions, implicitly relies on Metadata)
[OpenTelemetry Specification - Context Propagation Propagators](https://opentelemetry.io/docs/specs/otel/context/api-propagators/) (Defines formats like W3C Trace Context often carried in Metadata)
*Note: gRPC documentation itself defines Metadata.*
