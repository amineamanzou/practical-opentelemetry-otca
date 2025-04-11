---
title: "Purpose of the Zero Count Bucket in ExponentialHistogram"
weight: 4
description: "Defines the role of the zero_count bucket within an OpenTelemetry ExponentialHistogram."
---

This note clarifies the specific function of the `zero_count` field in the OpenTelemetry ExponentialHistogram data structure.

## Purpose of the Zero Count Bucket in ExponentialHistogram

**Question:** What is the purpose of the `zero_count` bucket in an ExponentialHistogram?

**Answer:** To store the count of values with absolute values less than or equal to `zero_threshold`.

**Explanation:**

An ExponentialHistogram is designed to efficiently represent the distribution of recorded values, particularly non-negative values. However, it includes specific handling for values that are exactly zero or very close to zero. The `zero_threshold` field defines a boundary \( \epsilon \) around zero.

The `zero_count` field specifically tracks the number of recorded values \( v \) whose absolute value \( |v| \) is less than or equal to this threshold ( \( |v| \le \epsilon \) ). This allows the histogram to accurately represent the frequency of values at or near zero separately from the exponentially scaled buckets used for other positive and negative values.

**Reference:**

* [OpenTelemetry Specification - Metrics Data Model: ExponentialHistogram](https://github.com/open-telemetry/opentelemetry-specification/blob/main/specification/metrics/data-model.md#exponentialhistogram)
