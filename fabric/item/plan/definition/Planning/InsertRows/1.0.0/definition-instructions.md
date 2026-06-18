---
title: Insert Rows item definition
description: Learn how to create a Insert Rows item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: Insert Rows item definition
ms.service: fabric
ms.date: 2026-06-18
---

# Insert Rows definition

This article provides a breakdown of the structure for Insert Rows definition items.

## Supported formats

Insert Rows items support the JSON format.

## Definition parts

This table lists the Insert Rows definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | Insert Rows (JSON) | {required_placeholder} | Array of custom (inserted) rows for a Planning visual, including static rows and calculated rows. |

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

## Insert Rows

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `rows` | InsertRow[] | true | No description provided |

### InsertRow

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | Unique row identifier. |
| `visualId` | string | true | ID of the visual this row belongs to. |
| `visualRowConfigId` | string or null | false | Optional visual row configuration reference. |
| `rowMeta` | RowMeta | true | No description provided |
| `name` | string | true | Display name of the row. |
| `status` | integer | true | Status code of the row. |
| `dimensionId` | string | true | Dimension this row belongs to. |

### RowMeta

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | No description provided |
| `row_type` | RowType | true | No description provided |
| `title` | string | true | No description provided |
| `scaling_factor` | string | false | Scaling factor for display (e.g., Auto). |
| `include_in_total` | boolean | false | No description provided |
| `parent_id` | string | false | Parent row ID for hierarchy. |
| `level` | integer | false | No description provided |
| `previous_row_id` | string | false | ID of the preceding row for ordering. |
| `disabled` | boolean | false | No description provided |
| `bind_for_cross_filter` | boolean or null | false | No description provided |
| `description` | string or null | false | No description provided |
| `column_aggregation` | string | false | No description provided |

### RowType

| Property | Type | Required | Description |
|---|---|---|---|
| `StaticRow` | StaticRowType | false | No description provided |
| `CalculatedRow` | CalculatedRowType | false | No description provided |

### StaticRowType

| Property | Type | Required | Description |
|---|---|---|---|
| `distribute_parent_value_to_child` | boolean | false | No description provided |
| `default_value` | object | false | Default value configuration. |
| `row_edit_mode` | string | false | No description provided |

### CalculatedRowType

| Property | Type | Required | Description |
|---|---|---|---|
| `formula` | string | true | Calculation formula for this row. |
| `description` | string | false | No description provided |
| `include_in_chart` | boolean | false | No description provided |
| `deferred` | boolean or null | false | No description provided |
| `bind_for_cross_filter` | boolean | false | No description provided |

### Insert Rows file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/planning/insertRows/1.0.0/schema.json",
  "rows": [
    {
      "id": "string",
      "visualId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "rowMeta": {
        "id": "string",
        "row_type": {
          "StaticRow": {}
        },
        "title": "string"
      },
      "name": "string",
      "status": 0,
      "dimensionId": "string"
    }
  ]
}
```
