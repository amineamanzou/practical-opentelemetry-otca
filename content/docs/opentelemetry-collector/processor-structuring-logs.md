---
title: "Processor for Converting Raw Logs to Structured Data"
weight: 31
description: "Identifying the OpenTelemetry Collector processor responsible for parsing and structuring raw event logs."
---

**Question:**
Which processor in the OpenTelemetry Collector is responsible for converting raw event logs into structured data?

**Answer:**
Transform Processor

**Explanation:**
While several processors might manipulate log data, the **Transform Processor** is the primary component designed for general-purpose data manipulation, including parsing and structuring logs using the OpenTelemetry Transformation Language (OTTL). OTTL provides functions for parsing text (e.g., using regex, JSON, key-value pairs) found in the log record's body and extracting values into attributes, effectively converting unstructured or semi-structured logs into structured data with meaningful key-value pairs. Other processors like `logstransform` exist, but `transform` with OTTL is the modern and flexible approach.

**Reference:**
[Transform Processor](https://opentelemetry.io/docs/collector/transformations/)
[OTTL Log Context Functions](https://opentelemetry.io/docs/collector/transformations/ottl/ottl-functions/#log-functions)
