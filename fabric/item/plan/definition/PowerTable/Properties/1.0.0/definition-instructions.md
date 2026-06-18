---
title: PowerTable Properties item definition
description: Learn how to create a PowerTable Properties item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: PowerTable Properties item definition
ms.service: fabric
ms.date: 2026-06-18
---

# PowerTable Properties definition

This article provides a breakdown of the structure for PowerTable Properties definition items.

## Supported formats

PowerTable Properties items support the JSON format.

## Definition parts

This table lists the PowerTable Properties definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | PowerTable Properties (JSON) | {required_placeholder} | Properties definition for a PowerTable visual, including assignments, filters, styles, and visual state. |

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

## PowerTable Properties

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `properties` | PowerTableProperties | true | No description provided |

### PowerTableProperties

| Property | Type | Required | Description |
|---|---|---|---|
| `pivotAssignments` | array | true | No description provided |
| `sortingConfig` | array | true | No description provided |
| `superFilterAssignments` | SuperFilterAssignment[] | true | No description provided |
| `visualInteractions` | object | false | No description provided |
| `groupName` | string | false | No description provided |
| `visualType` | integer | false | No description provided |
| `chartType` | string | false | No description provided |
| `originEntityId` | string | false | No description provided |
| `splitByCategory` | object | false | No description provided |
| `transformMeasure` | string | false | No description provided |
| `groupMeasureAssignments` | array | false | No description provided |
| `mobileProperties` | object | false | No description provided |
| `preVisualId` | string | false | No description provided |
| `dimension` | Dimension | false | No description provided |
| `position` | Position | false | No description provided |
| `visualStyles` | object | false | No description provided |
| `lockAspectRatio` | boolean | false | No description provided |
| `layerProperties` | object | false | No description provided |
| `shapeType` | string | false | No description provided |
| `visualState` | VisualState | true | No description provided |

### SuperFilterAssignment

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | No description provided |
| `filter` | array | true | No description provided |
| `position` | string | true | No description provided |
| `configuration` | object | true | No description provided |
| `filterLevel` | string | true | No description provided |
| `pivotAssignments` | PivotAssignment[] | true | No description provided |

### PivotAssignment

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | No description provided |
| `sourceId` | string | true | No description provided |
| `name` | string | true | No description provided |
| `columnName` | string | true | No description provided |
| `tableName` | string | true | No description provided |
| `order` | integer | true | No description provided |
| `bucketId` | string | false | No description provided |
| `dataType` | string | true | No description provided |
| `columnType` | string | true | No description provided |
| `sourceType` | string | true | No description provided |

### Dimension

| Property | Type | Required | Description |
|---|---|---|---|
| `width` | number | true | No description provided |
| `height` | number | true | No description provided |

### Position

| Property | Type | Required | Description |
|---|---|---|---|
| `x` | number | true | No description provided |
| `y` | number | true | No description provided |

### VisualState

| Property | Type | Required | Description |
|---|---|---|---|
| `assignmentColumnMap` | object | false | No description provided |
| `superFilterAssignments` | array | false | No description provided |
| `superFilter` | object | false | No description provided |
| `manageMeasures` | array | false | No description provided |
| `columnMeta` | object | false | No description provided |
| `superFilterMetaConfig` | object | false | No description provided |

### PowerTable Properties file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/powerTable/properties/1.0.0/schema.json",
  "properties": {
    "pivotAssignments": [
      "string"
    ],
    "sortingConfig": [
      "string"
    ],
    "superFilterAssignments": [
      {
        "id": "string",
        "filter": [
          "string"
        ],
        "position": "string",
        "configuration": {},
        "filterLevel": "string",
        "pivotAssignments": [
          {
            "id": "string",
            "sourceId": "string",
            "name": "string",
            "columnName": "string",
            "tableName": "string",
            "order": 0,
            "dataType": "string",
            "columnType": "string",
            "sourceType": "string"
          }
        ]
      }
    ],
    "visualState": {}
  }
}
```
