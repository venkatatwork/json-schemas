---
title: Writeback Configuration item definition
description: Learn how to create a Writeback Configuration item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: Writeback Configuration item definition
ms.service: fabric
ms.date: 2026-06-18
---

# Writeback Configuration definition

This article provides a breakdown of the structure for Writeback Configuration definition items.

## Supported formats

Writeback Configuration items support the JSON format.

## Definition parts

This table lists the Writeback Configuration definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | Writeback Configuration (JSON) | {required_placeholder} | Writeback configuration for a Planning visual, defining destination, column mapping, and auto-writeback settings. |

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

## Writeback Configuration

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `writebackType` | integer | true | Writeback type code. |
| `destination` | WritebackDestination | true | No description provided |
| `writebackFilter` | object | false | No description provided |
| `excludedMeasureGuids` | string[] | false | Measure GUIDs excluded from writeback. |
| `isAutoWritebackEnabled` | integer | false | Auto-writeback enabled status code. |
| `autoWbEnabledScenarioIds` | string[] | false | Scenarios with auto-writeback enabled. |
| `debounce` | DebounceConfig | false | No description provided |
| `isSnapshotWbEnabled` | integer | false | Snapshot writeback enabled status code. |
| `wbTableColumnMapping` | object | false | Mapping of measure GUIDs to writeback column names. |
| `numberPrecision` | object | false | No description provided |
| `stringColumnLength` | object | false | No description provided |
| `writebackAsHTML` | boolean | false | Whether to write back as HTML. |
| `wbColumns` | WritebackColumn[] | false | Column definitions for the writeback table. |
| `hasWritebackAccess` | boolean | false | No description provided |

### WritebackDestination

| Property | Type | Required | Description |
|---|---|---|---|
| `connection` | ConnectionReferenceOrVar | true | No description provided |
| `database` | ItemReferenceOrVar | true | No description provided |
| `schema` | string | true | No description provided |
| `tableName` | string | true | No description provided |

### DebounceConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `duration` | integer | false | Debounce duration in seconds. |
| `isDebounceEnabled` | integer | false | Debounce enabled status code. |

### ColumnMapping

| Property | Type | Required | Description |
|---|---|---|---|
| `visualName` | string | true | Display name in the visual. |
| `wbColumnName` | string | true | Column name in the writeback table. |

### WritebackColumn

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | false | Column ID (for dimension columns). |
| `measureGuid` | string | false | Measure GUID (for measure columns). |
| `name` | string | true | Column name in the writeback table. |
| `dataType` | string | true | Data type of the column. |
| `isColumnDimension` | boolean | false | No description provided |
| `isTimeDimension` | boolean | false | No description provided |
| `timeIntervalUnit` | string | false | No description provided |
| `source` | string | false | Source type of the column. |

### Writeback Configuration file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/planning/writeback/1.0.0/schema.json",
  "writebackType": 0,
  "destination": {
    "connection": {},
    "tableName": "string",
    "schema": "string",
    "database": {}
  }
}
```
