> [!IMPORTANT]
> **This repository is archived and read-only.**
>
> It is pinned to **HarperDB v4** and is preserved for reference.
> It is **not** kept in sync with current releases and may not be supported in latest Harper versions.
>
> For up-to-date guides and reference docs, see the [Harper docs](https://docs.harper.fast) and join our [Discord](https://harper.fast/discord).

# HarperDB Sample Grafana Dashboards
This repository is a collection of sample HarperDB Grafana dashboards. We intend to grow this collection overtime with additional monitoring dashboards and examples for specific use cases.

## Requirements
All dashboards in this collection require:
- One or more HarperDB instances with the [HarperDB Prometheus Exporter application](https://github.com/HarperDB-Add-Ons/prometheus_exporter) deployed.
- A Prometheus installation configured to scrape the HarperDB Prometheus Exporter(s).
- A Grafana installation with the Prometheus data source configured.

## Importing Dashboards
These dashboards require selecting your Prometheus datasource as part of the import. For detailed instructions, visit the [Grafana Import Dashboards documentation](https://grafana.com/docs/grafana/latest/dashboards/build-dashboards/import-dashboards/).

## Dashboards
### HarperDB Monitoring Dashboard
[`harperdb_monitoring_dashboard.json`](./harperdb_monitoring_dashboard.json)

This dashboard displays primary data associated with a standard HarperDB install. Variables are parameterized at the top of the dashboard giving configurable options for:
- Prometheus Job(s)
  - The primary grouping of data sources. An example of where you may have multiple of these is in the case of multiple deployments (prod/ stage/dev and/or regional clusters).
- Instance(s)
  - The available instances(s) that data will be sourced from filtered by the selected job(s).
- Quantile(s)
  - The available quantile(s) of the given dataset.
- Path(s)
  - The available path(s) that are monitored from the HarperDB instance(s). If the Prometheus Exporter is installed, you should see `/prometheus-exporter/metrics` at a minimum.
- Method(s)
  - The available methods(s) of the given dataset.
