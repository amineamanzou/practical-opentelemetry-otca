---
title: "Schema URL Requirement in OpenTelemetry Schema Files"
weight: 5
description: "Explains the rule governing the schema_url field within an OpenTelemetry Schema File."
---

This note clarifies the requirement for the `schema_url` field specified in the OpenTelemetry Schema File format.

## Schema URL Requirement in OpenTelemetry Schema Files

**Question:** In the Schema File structure, what must the `schema_url` correspond to?

**Answer:** The highest version number listed in the `versions` section.

**Explanation:**

OpenTelemetry Schemas provide a way to describe the structure and semantics of telemetry data (attributes, resource models, etc.) and manage their evolution over time. A Schema File defines one or more versions of a specific schema.

The `schema_url` field at the root of the Schema File acts as a canonical identifier for the schema described by that file. According to the specification, this URL *must* correspond to the URL of the *highest* version defined within the `versions` block of that same file. This ensures that the main `schema_url` always points to the definition of the latest version contained within that file.

```yaml
# Example Schema File Structure
file_format: "1.0.0"
schema_url: https://opentelemetry.io/schemas/1.2.0 # Must match the highest version below

versions:
  "https://opentelemetry.io/schemas/1.0.0":
    # ... version 1.0.0 definition
  "https://opentelemetry.io/schemas/1.1.0":
    # ... version 1.1.0 definition
  "https://opentelemetry.io/schemas/1.2.0": # Highest version
    # ... version 1.2.0 definition
```

**Reference:**

* [OpenTelemetry Specification - Schema File Format](https://github.com/open-telemetry/opentelemetry-specification/blob/main/specification/schemas/file_format.md)
