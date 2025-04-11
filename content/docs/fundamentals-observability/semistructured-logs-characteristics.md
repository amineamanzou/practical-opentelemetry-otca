---
title: "Characteristics of Semistructured Logs"
weight: 14
description: "Describes key characteristics of semistructured logs, focusing on pattern consistency and parsing requirements."
---

This note focuses on understanding the nature and characteristics of semistructured logs, a common log format encountered in observability.

## Characteristics of Semistructured Logs

**Question:** Which of the following accurately describes a characteristic of semistructured logs in production observability?

**Answer Principle:** They use self-consistent patterns but may require different parsers for different systems.

**Explanation:**
Semistructured logs utilize consistent internal patterns to structure the data they contain, making them machine-readable to some extent. However, the specific formatting, delimiters, and conventions used can vary significantly from one system or application to another.

For example, one application might produce logs with key-value pairs separated by `=`, while another might use a different delimiter or embed JSON within a text line.

This variability is a key characteristic:

- **Internal Consistency:** Logs from a *single source* typically follow a consistent pattern.
- **External Variability:** Logs from *different sources* may have different patterns and formats.
- **Parsing Needs:** Because of this variability across systems, different parsers are often required to effectively extract meaningful data from semistructured logs originating from various sources within an infrastructure.

This contrasts with fully structured logs (like pure JSON), which adhere to a strict schema regardless of the source, and unstructured logs, which lack consistent patterns altogether.

**Reference:**

- OpenTelemetry Documentation: [Logs Overview](https://opentelemetry.io/docs/concepts/signals/logs/) (Discusses log types and the challenges they present).
- OpenTelemetry Documentation: [Logs Data Model - Body Field](https://opentelemetry.io/docs/specs/otel/logs/data-model/#body-field) (Implicitly covers how different structures, including semistructured, can be represented).
