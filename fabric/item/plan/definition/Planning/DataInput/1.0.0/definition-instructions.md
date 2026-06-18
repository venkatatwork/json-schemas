---
title: Data Input Columns item definition
description: Learn how to create a Data Input Columns item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: Data Input Columns item definition
ms.service: fabric
ms.date: 2026-06-18
---

# Data Input Columns definition

This article provides a breakdown of the structure for Data Input Columns definition items.

## Supported formats

Data Input Columns items support the JSON format.

## Definition parts

This table lists the Data Input Columns definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | Data Input Columns (JSON) | {required_placeholder} | Array of data input column definitions for a Planning visual, including forecasts, text inputs, number inputs, and native measures. |

## Definition example

```json
{
  "parts": [
    {
      "path": "{fileName}",
      "payload": "{base64_placeholder}",
      "payloadType": "InlineBase64"
    }
  ]
}
```

## Data Input Columns

| Property | Type | Required | Description |
|---|---|---|---|

### DataInputColumn

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `measureGuid` | string | true | Unique identifier for the measure/column. |
| `visualId` | string | true | ID of the visual this column belongs to. |
| `columnMeta` | ColumnMeta | true | No description provided |
| `name` | string | true | Display name of the column. |
| `description` | string or null | false | Optional description. |
| `dataInputType` | integer | true | Numeric code for the data input type. |
| `disableWriteAccess` | boolean | false | Whether write access is disabled. |
| `forecastAllowedUserPermissions` | boolean | false | Whether user permissions are allowed for forecast. |

### ColumnMeta

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | Unique column meta identifier. |
| `label` | string | true | Display label. |
| `measure_type` | MeasureType | true | No description provided |
| `data_type` | string | true | Data type of the column. |
| `description` | string or null | false | No description provided |

### MeasureType

| Property | Type | Required | Description |
|---|---|---|---|
| `Forecast` | ForecastMeasure | false | No description provided |
| `DataInput` | DataInputMeasure | false | No description provided |
| `VisualColumn` | VisualColumnMeasure | false | No description provided |
| `Native` | NativeMeasure | false | No description provided |

### ForecastMeasure

| Property | Type | Required | Description |
|---|---|---|---|
| `forecast_version` | integer | true | No description provided |
| `forecast_period` | object | true | No description provided |
| `closed_period_till` | string or null | false | No description provided |
| `auto_close_forecast_settings` | object or null | false | No description provided |
| `forecast_value_display` | string | false | No description provided |
| `open_period_config` | object | false | No description provided |
| `closed_period_config` | object | false | No description provided |
| `forecast_allowed_user_permissions` | boolean | false | No description provided |
| `disable_write_access` | boolean | false | No description provided |
| `edit_config` | EditConfig | false | No description provided |

### DataInputMeasure

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | No description provided |
| `column_type` | object | true | Discriminated union of column types (Number, ShortText, etc.). |
| `title` | string | true | No description provided |
| `disable_write_access` | boolean | false | No description provided |
| `on_change_formula` | string | false | No description provided |
| `allow_input` | string | false | No description provided |

### VisualColumnMeasure

| Property | Type | Required | Description |
|---|---|---|---|
| `DataInput` | DataInputMeasure | false | No description provided |

### NativeMeasure

| Property | Type | Required | Description |
|---|---|---|---|
| `measure_role` | string | true | Role of the native measure (e.g., ACMeasure). |

### EditConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `aggregate_total` | string or null | false | No description provided |
| `allow_input` | string or null | false | No description provided |
| `on_change_formula` | string or null | false | No description provided |
| `number_column_metadata` | NumberColumnType | false | No description provided |

### NumberColumnType

| Property | Type | Required | Description |
|---|---|---|---|
| `min_value` | number or null | false | No description provided |
| `max_value` | number or null | false | No description provided |
| `distribute_parent_value_to_children` | boolean | false | No description provided |
| `default_value` | number or null | false | No description provided |

### ShortTextColumnType

| Property | Type | Required | Description |
|---|---|---|---|
| `default_value` | string or null | false | No description provided |
| `allow_entry_on_totals_or_subtotals` | boolean | false | No description provided |
| `prevent_null` | boolean | false | No description provided |
| `field_validation` | string | false | No description provided |
| `minimum_length` | integer or null | false | No description provided |
| `maximum_length` | integer or null | false | No description provided |

### Data Input Columns file example

```json
[
  {
    "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/planning/dataInput/1.0.0/schema.json",
    "measureGuid": "string",
    "visualId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "columnMeta": {
      "id": "string",
      "label": "string",
      "measure_type": {
        "Forecast": {
          "forecast_version": 0,
          "forecast_period": {
            "start": "2026-01-01T00:00:00Z",
            "end": "2026-01-01T00:00:00Z"
          }
        }
      },
      "data_type": "Number"
    },
    "name": "string",
    "dataInputType": 0
  }
]
```
