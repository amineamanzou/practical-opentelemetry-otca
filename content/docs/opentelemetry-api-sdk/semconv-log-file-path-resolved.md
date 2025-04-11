---
title: "Semantic Convention for Resolved Log File Path"
weight: 17
description: "Defines the OpenTelemetry semantic attribute for the resolved log file path."
---

This note identifies the standard OpenTelemetry attribute used to specify the fully resolved path of a log file.

## Semantic Convention: log.file.path_resolved

**Question:**
In OpenTelemetry, which attribute specifies the full path to the log file with all symbolic links resolved?

**Answer:**
`log.file.path_resolved`

**Explanation:**
OpenTelemetry semantic conventions define attributes for common log metadata. When logs originate from a file, the `log.file.path` attribute stores the original path as specified or configured. However, this path might contain symbolic links. The `log.file.path_resolved` attribute is specifically defined to store the absolute path to the log file after resolving any symbolic links. This provides an unambiguous reference to the physical file location.

**Reference:**
[OpenTelemetry Semantic Conventions - Log Media Attributes: log.file.path_resolved](https://opentelemetry.io/docs/specs/semconv/general/log/#log-media)
