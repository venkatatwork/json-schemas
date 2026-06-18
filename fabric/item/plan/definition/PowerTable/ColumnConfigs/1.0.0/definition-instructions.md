---
title: PowerTable Column Configs item definition
description: Learn how to create a PowerTable Column Configs item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: PowerTable Column Configs item definition
ms.service: fabric
ms.date: 2026-06-18
---

# PowerTable Column Configs definition

This article provides a breakdown of the structure for PowerTable Column Configs definition items.

## Supported formats

PowerTable Column Configs items support the JSON format.

## Definition parts

This table lists the PowerTable Column Configs definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | PowerTable Column Configs (JSON) | {required_placeholder} | Array of column configuration definitions for a PowerTable visual. |

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

## PowerTable Column Configs

| Property | Type | Required | Description |
|---|---|---|---|

### ColumnConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `columnGuid` | string | true | Unique identifier for the column. |
| `columnName` | string | true | Database column name. |
| `columnType` | integer | true | Column type code (1=text, 2=single select, 3=multi select, 4=date, etc.). |
| `columnMeta` | ColumnMeta | true | No description provided |
| `hideColumn` | integer | false | Whether the column is hidden (0=visible, 1=hidden). |
| `mandatory` | integer | false | Whether the column is mandatory (0=optional, 1=required). |
| `allowEdit` | integer | false | Whether the column allows editing (0=readonly, 1=editable). |
| `visualColumnType` | integer | false | Visual representation type. |
| `displayName` | string | true | User-facing column name. |
| `description` | string | false | No description provided |

### ColumnMeta

| Property | Type | Required | Description |
|---|---|---|---|
| `defaultValueType` | string | false | No description provided |
| `defaultValue` | string or null | false | No description provided |
| `isPrimaryKey` | boolean | false | No description provided |
| `updateValueOnRowModify` | boolean | false | No description provided |
| `resetToDefaultOnRowModify` | boolean | false | No description provided |
| `maximumAllowedLength` | string | false | No description provided |
| `textFieldColumnType` | string | false | No description provided |
| `options` | object[] | false | Static dropdown options. |
| `selectionMethod` | string | false | How dropdown options are sourced. |
| `optionLinking` | OptionLinking | false | No description provided |
| `isFilterBasedOnAnotherValue` | boolean | false | No description provided |
| `fcVisualName` | string or null | false | No description provided |
| `fcVisualIdColumnName` | string or null | false | No description provided |
| `fcVisualLabelColumnName` | string or null | false | No description provided |

### OptionLinking

| Property | Type | Required | Description |
|---|---|---|---|
| `lookupConfig` | LookupConfig[] | false | No description provided |
| `filters` | object[] | false | No description provided |

### LookupConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `schema` | string | false | No description provided |
| `table` | string | true | Lookup table name. |
| `label` | string | true | Column used for display label. |
| `id` | string | true | Column used for the value. |
| `order` | integer | false | No description provided |
| `linkingColumn` | string | false | Column in the main table this links to. |

### PowerTable Column Configs file example

```json
[
  {
    "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/powerTable/columnConfigs/1.0.0/schema.json",
    "columnGuid": "string",
    "columnName": "string",
    "columnType": 0,
    "columnMeta": {},
    "displayName": "string"
  }
]
```
