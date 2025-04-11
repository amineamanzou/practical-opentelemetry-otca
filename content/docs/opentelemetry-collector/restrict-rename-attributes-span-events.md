---
title: "Restricting rename_attributes Transformation in span_events Context"
weight: 30
description: "Using optional fields to restrict the `rename_attributes` OTTL function to specific spans or events within the `span_events` context."
---

**Question:**
When using the 'rename_attributes' transformation in the 'span_events' section, which optional fields can be used to restrict the transformation to specific spans or events?

**Answer:**
`apply_to_spans` and `apply_to_events`

**Explanation:**
The `rename_attributes` function within the OpenTelemetry Transformation Language (OTTL) allows renaming attributes. When used within the `span_events` context of the Transform Processor, its application can be further refined. The optional `apply_to_spans` and `apply_to_events` fields (often used with `where` clauses within them) allow you to specify conditions under which the attribute renaming should apply, targeting only specific spans or specific events within those spans, rather than applying universally to all events processed in that context.

**Reference:**
This relates to the fine-grained control within OTTL functions, specifically in the context of spans and their events.
[OTTL Span Context](https://opentelemetry.io/docs/collector/transformations/ottl/ottl-contexts/#span)
[OTTL Functions](https://opentelemetry.io/docs/collector/transformations/ottl/ottl-functions/) (Check specific functions like `rename_attributes` if detailed)
