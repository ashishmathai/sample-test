# Datadog ECS Dashboard using Terraform

Terraform module for deploying pre-defined set of Dataodog dashboards in [datadog](https://www.datadoghq.com) using [terraform](https://www.terraform.io/)

## Dependencies

- terraform 0.13
- Datadog Integration Credential: `datadog_app_key` and `datadog_api_key`, retrieve from [Datadog: Intergration/APIs](https://app.datadoghq.com/account/settings#api)

## Usage

```
terraform init
terraform apply -var "datadog_api_key=xxxxxxxxxxxx" -var "datadog_app_key=xxxxxxxxxxxx"
```
### Or
Create `terraform.tfvars` add the api and app key.

```
datadog_api_key   = "******************************"
datadog_app_key   = "***********************************"
```

## Management
As dashboard is a single resource and there is no option yet for reusing the widgets as modules.

## Schema
Reqired
- `layout_type` (String) The layout type of the dashboard, either 'free' or 'ordered'.
- `title` (String) The title of the dashboard.
- `widget` (Block List, Min: 1) The list of widgets to display on the dashboard.

List of some widget definition
```
- alert_graph_definition	- group_definition
- alert_value_definition	- service_level_objective_definition
- change_definition		- event_stream_definition
- distribution_definition	- event_timeline_definition
- check_status_definition	- free_text_definition
- heatmap_definition		- iframe_definition
- hostmap_definition		- image_definition
- note_definition		- log_stream_definition
- query_table_definition	- manage_status_definition
- query_value_definition	- trace_service_definition
- scatterplot_definition	- toplist_definition
- servicemap_definition		- timeseries_definition
```
