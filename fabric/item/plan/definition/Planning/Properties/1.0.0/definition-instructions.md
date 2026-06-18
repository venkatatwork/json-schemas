---
title: Visual Properties (Planning) item definition
description: Learn how to create a Visual Properties (Planning) item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: Visual Properties (Planning) item definition
ms.service: fabric
ms.date: 2026-06-18
---

# Visual Properties (Planning) definition

This article provides a breakdown of the structure for Visual Properties (Planning) definition items.

## Supported formats

Visual Properties (Planning) items support the JSON format.

## Definition parts

This table lists the Visual Properties (Planning) definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | Visual Properties (Planning) (JSON) | {required_placeholder} | Properties configuration for a Planning visual, including pivot assignments, sorting, and filter configurations. |

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

## Visual Properties (Planning)

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `visuals` | object | true | Map of visual ID to visual properties. |

### VisualProperties

| Property | Type | Required | Description |
|---|---|---|---|
| `schema` | string | true | Properties schema version. |
| `properties` | object | true | No description provided |

### PivotAssignment

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | Unique identifier for the assignment (Table[Column] format). |
| `sourceId` | string | true | No description provided |
| `bucketId` | string | true | Target bucket for the assignment. |
| `columnName` | string | true | No description provided |
| `dataType` | string | true | No description provided |
| `order` | integer | false | No description provided |
| `columnType` | string | false | No description provided |
| `formatString` | string or null | false | No description provided |
| `contents` | string | false | No description provided |
| `sourceType` | string | false | No description provided |
| `name` | string | false | No description provided |
| `customName` | string | false | No description provided |
| `aggregationType` | string | false | No description provided |
| `isFlatHierarchy` | boolean | false | No description provided |
| `isHierarchyItemInMeasure` | boolean | false | No description provided |
| `distinctValueCount` | integer | false | No description provided |
| `hierarchyName` | string | false | No description provided |
| `group` | string | false | No description provided |
| `tableName` | string | false | No description provided |
| `dataRoleType` | string | false | No description provided |
| `groupDataType` | string | false | No description provided |
| `measureGuid` | string | false | No description provided |

### SuperFilterAssignment

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | Unique filter assignment ID. |
| `pivotAssignments` | PivotAssignment[] | true | No description provided |
| `isDefault` | boolean | false | No description provided |
| `isDefaultMeasure` | boolean | false | No description provided |
| `isDaxMeasure` | boolean | false | No description provided |
| `bucketId` | string | false | No description provided |
| `configuration` | FilterConfiguration | false | No description provided |
| `filter` | object[] | false | No description provided |
| `position` | string | false | No description provided |
| `filterLevel` | string | false | No description provided |

### FilterConfiguration

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | false | No description provided |
| `hide` | boolean | false | No description provided |
| `isExpanded` | boolean | false | No description provided |
| `locked` | boolean | false | No description provided |
| `filterMode` | string | false | No description provided |
| `visualType` | string | false | No description provided |
| `scale` | string | false | No description provided |
| `enableNumericToFacet` | boolean | false | No description provided |
| `filterOperator` | string | false | No description provided |
| `singleSelect` | boolean | false | No description provided |
| `selectAll` | boolean | false | No description provided |
| `slider` | boolean | false | No description provided |
| `regex` | string | false | No description provided |
| `measureSearch` | boolean | false | No description provided |
| `alphaNumericValues` | object | false | No description provided |
| `sort` | object[] | false | No description provided |
| `topN` | object | false | No description provided |
| `sheetDataItemAggregationType` | string | false | No description provided |

### Visual Properties (Planning) file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/planning/properties/1.0.0/schema.json",
  "visuals": {}
}
```
