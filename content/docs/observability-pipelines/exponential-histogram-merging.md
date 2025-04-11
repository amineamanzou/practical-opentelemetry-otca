---
title: "Merging ExponentialHistograms with Different Zero Thresholds"
weight: 3
description: "Explains the specification for merging ExponentialHistograms when their zero_threshold values differ."
---

This note details the correct procedure for merging OpenTelemetry ExponentialHistograms that have different `zero_threshold` settings.

## Merging ExponentialHistograms with Different Zero Thresholds

**Question:** When merging ExponentialHistograms with different `zero_threshold` values, which approach should be taken according to the specifications?

**Answer:** Use the largest `zero_threshold` and merge lower buckets into the common wider zero bucket.

**Explanation:**

The OpenTelemetry specification defines how ExponentialHistograms should be merged to ensure consistency, even when they originate from sources with slightly different configurations. When the `zero_threshold` (which defines the boundary around zero for values counted in `zero_count`) differs between two histograms being merged, the resulting histogram must adopt the *larger* of the two `zero_threshold` values.

Consequently, any buckets from the histogram with the smaller `zero_threshold` that fall within the range defined by the larger `zero_threshold` must be merged into the `zero_count` bucket of the resulting histogram. This ensures that all values within the widest defined "zero" range are correctly accounted for in the merged `zero_count`.

**Reference:**

* [OpenTelemetry Specification - Metrics Data Model: ExponentialHistogram](https://github.com/open-telemetry/opentelemetry-specification/blob/main/specification/metrics/data-model.md#exponentialhistogram)
