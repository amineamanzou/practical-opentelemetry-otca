---
title: "Enabling zPages for Collector Debugging in Kubernetes"
weight: 3
description: "Details the configuration required to enable the zPages extension for the OpenTelemetry Collector in Kubernetes."
---

This note explains the necessary configuration step to make the OpenTelemetry Collector's `zPages` debugging endpoint accessible within a Kubernetes environment.

## Enabling zPages for Collector Debugging in Kubernetes

**Question:** A development team wants to enable `zPages` for debugging the Collector in a Kubernetes environment. Which configuration change should they implement?

**Answer:** Configure the `zPages` endpoint to listen on `0.0.0.0:55679`.

**Explanation:**

The `zPages` extension provides live data and debugging information about an OpenTelemetry Collector instance via a web interface. By default, for security reasons, it might bind to `localhost` (`127.0.0.1`), making it inaccessible from outside the Collector's pod or node.

In a Kubernetes environment, to access the `zPages` interface (e.g., via port-forwarding or a Service), the endpoint must listen on an address that accepts connections from other network interfaces. Configuring the `endpoint` to `0.0.0.0:55679` tells `zPages` to listen on all available network interfaces within the pod on port 55679 (the default `zPages` port), making it accessible from outside the pod, subject to Kubernetes networking rules.

```yaml
extensions:
  zpages:
    endpoint: 0.0.0.0:55679

service:
  extensions: [zpages]
  pipelines:
    # ... other pipeline configurations
```

**Reference:**

* [OpenTelemetry Collector Contrib - zPages Extension](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/extension/zpagesextension)
