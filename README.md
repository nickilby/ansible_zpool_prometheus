# ansible_zpool_prometheus

This is taking all the work done by Richard Elling https://github.com/richardelling/zpool_prometheus and wrapping it in an ansible role for deployment on Ubuntu. For all documentation on collecting the metrics please refer to his Github page.

This example expects that the Prometheus Node exporter is already installed and zpool_prometheus metrics are collected by the text collecter. This is to avoid having an additional /metrics endpoint to scrape on another port.

Or using a flask app to expose the metrics on :9188/metrics

The zpool_prometheus program produces prometheus-compatible metrics from zpools. In the UNIX tradition, zpool_prometheus does one thing: read statistics from a pool and print them to stdout. In many ways, this is a metrics-friendly output of statistics normally observed via the zpool command.
