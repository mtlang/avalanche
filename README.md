# Avalanche

Avalanche serves a text-based [Prometheus metrics](https://prometheus.io/docs/instrumenting/exposition_formats/) endpoint for load testing [Prometheus](https://prometheus.io/) and possibly other [OpenMetrics](https://github.com/OpenObservability/OpenMetrics) consumers.

Avalanche also supports load testing for services accepting data via Prometheus remote_write API such as [Thanos](https://github.com/improbable-eng/thanos), [Cortex](https://github.com/weaveworks/cortex), [M3DB](https://m3db.github.io/m3/integrations/prometheus/), [VictoriaMetrics](https://github.com/VictoriaMetrics/VictoriaMetrics/) and other services [listed here](https://prometheus.io/docs/operating/integrations/#remote-endpoints-and-storage).

Metric names and unique series change over time to simulate series churn.

Checkout the [blog post](https://blog.freshtracks.io/load-testing-prometheus-metric-ingestion-5b878711711c).

## Configuration Flags 
```bash 
avalanche --help
```

## Run Docker Image

```bash
docker run quay.io/freshtracks.io/avalanche --help
```

## Build and Run Go Binary
```bash
go get github.com/mtlang/avalanche/cmd/...
avalanche --help
```

## My Fork
This repo was forked from [open-fresh/avalanche](https://github.com/open-fresh/avalanche). At the time of forking, the only major change I have made is to support disabling the --series-interval and --metric-interval settings. If either flag is set to 0, avalanche will either never change the "series" labels of its metrics or never change the names of its metrics, respectively. 