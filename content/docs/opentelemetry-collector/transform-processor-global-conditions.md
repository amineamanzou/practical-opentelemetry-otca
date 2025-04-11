---
title: "Combining Multiple Global Conditions in Transform Processor"
weight: 26
description: "How multiple global conditions (top-level `where` clauses) are combined within a single OTTL context in the Transform Processor."
---

**Question:**
In the transform processor's configuration, how are multiple global conditions within a context combined?

**Answer:**
ORed together; at least one condition must be true.

**Explanation:**
The Transform Processor allows defining OTTL statements that apply only under certain conditions using `where` clauses. When you define multiple top-level `where` clauses for a specific context (like `trace` or `metric`), these conditions are logically ORed. This means the associated list of OTTL function invocations will execute if *any* of the specified global conditions evaluate to true for a given telemetry item.

**Reference:**
[Transform Processor (OTTL) Syntax - Conditional Execution](https://opentelemetry.io/docs/collector/transformations/ottl/ottl-syntax/#conditional-execution)
