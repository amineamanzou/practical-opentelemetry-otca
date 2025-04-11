---
title: "Invalid Environment Variable Substitution"
weight: 23
description: "Identifies invalid syntax for environment variable substitution in OpenTelemetry configuration."
---

This note highlights an example of invalid syntax for environment variable substitution within the OpenTelemetry configuration model.

## Invalid Environment Variable Substitution

**Question:**
Which of the following environment variable substitutions is invalid according to the OpenTelemetry configuration data model?

**Answer:**
`${1INVALID_VAR}`

**Explanation:**
OpenTelemetry configuration mechanisms (often used in collectors or SDK configuration files) may support environment variable substitution using the `${VAR_NAME}` syntax. However, environment variable names themselves have restrictions. They typically cannot start with a number and usually consist of alphanumeric characters and underscores. Therefore, `${1INVALID_VAR}` is invalid because `1INVALID_VAR` is not a valid environment variable name in most shell environments and contexts where this substitution would be used.

**Reference:**
*Note: Direct specification for substitution syntax might be implicit or within specific component documentation (like the Collector). The invalidity stems from general environment variable naming rules.*
[POSIX Standard - Environment Variables](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap08.html)
