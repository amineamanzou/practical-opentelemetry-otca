---
title: "Preventing Metric Name Reuse"
weight: 13
description: "Outlines OpenTelemetry guidelines for checking existing configurations to prevent metric name reuse, especially with renaming."
---

This note explains the process recommended by OpenTelemetry to avoid reusing metric names, particularly focusing on checks related to metric transformation configurations.

## Preventing Metric Name Reuse

**Question:** According to OpenTelemetry guidelines, what should be checked to prevent name reuse when introducing a new metric name?

**Answer Principle:** Verify the name does not appear as a key in any existing **`rename_metrics` sections** within relevant configurations (e.g., OpenTelemetry Collector).

**Explanation:**
To prevent name reuse when introducing a new metric name, OpenTelemetry guidelines suggest verifying that the intended name does not appear as a key in any existing `rename_metrics` transformation rules or similar configurations.

This check is important because metric renaming is a mechanism used in observability pipelines (often within the OpenTelemetry Collector) to modify metric names, for instance, to align with different conventions or to correct inconsistencies. If a new metric is introduced with a name that is already targeted by a rename operation (i.e., it's the *output* name specified in a `rename_metrics` rule), it can lead to conflicts or unexpected behavior.

Ensuring the new name isn't designated as a target in existing rename configurations helps maintain clarity and avoids confusion by preventing clashes with metrics that have been explicitly renamed. While adhering to Semantic Conventions when initially defining metrics is fundamental, checking rename configurations adds another layer of safety against naming collisions within the processing pipeline.

**Reference:**

- OpenTelemetry Documentation: [General Metric Semantic Conventions](https://opentelemetry.io/docs/specs/semconv/general/metrics/) (Provides context on naming and transformations)
- OpenTelemetry Documentation: [Semantic Conventions Overview](https://opentelemetry.io/docs/specs/semconv/)
