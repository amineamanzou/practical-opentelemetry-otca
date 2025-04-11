---
title: "Renaming Span Events with OTTL"
weight: 10
description: "How to rename span events using the Transform Processor (OTTL) in the OpenTelemetry Collector."
---

**Question:**
In the 'span_events' section of an OpenTelemetry schema file, which transformation allows for changing the names of events?

**Answer:**
`rename_events`

**Explanation:**
The OpenTelemetry Transformation Language (OTTL) used within the Transform Processor provides the `rename_events` function specifically for modifying the names of events within the `span_events` context. This allows for standardization or modification of event names as they pass through the Collector pipeline.

**Reference:**
See the OTTL functions documentation for spans:
[OTTL Span Functions](https://opentelemetry.io/docs/collector/transformations/ottl/ottl-functions/#span-functions) (Note: While the direct function might be under span context, it applies to events within spans) or general [Transform Processor](https://opentelemetry.io/docs/collector/transformations/)
