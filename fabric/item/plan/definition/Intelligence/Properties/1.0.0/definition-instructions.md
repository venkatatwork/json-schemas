---
title: Intelligence Properties item definition
description: Learn how to create a Intelligence Properties item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: Intelligence Properties item definition
ms.service: fabric
ms.date: 2026-06-18
---

# Intelligence Properties definition

This article provides a breakdown of the structure for Intelligence Properties definition items.

## Supported formats

Intelligence Properties items support the JSON format.

## Definition parts

This table lists the Intelligence Properties definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | Intelligence Properties (JSON) | {required_placeholder} | Properties definition for an Intelligence sheet visual, including page-level settings, variables, canvas styles, commentary, and embedded visual configurations. |

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

## Intelligence Properties

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `properties` | PageProperties | true | No description provided |
| `visuals` | Visual[] | true | List of visuals on the Intelligence sheet. |

### PageProperties

| Property | Type | Required | Description |
|---|---|---|---|
| `schema` | string | true | Schema version for the properties format. |
| `properties` | PageSettings | true | No description provided |

### PageSettings

| Property | Type | Required | Description |
|---|---|---|---|
| `pageLevelFilterAssignments` | array | false | Page-level filter assignments. |
| `entityLevelVariables` | EntityVariable[] | false | Entity-level calculated variables (actions, numbers, dropdowns, etc.). |
| `filterPanePosition` | string | false | Position of the filter pane. |
| `topPositionFilterExpandConfig` | FilterExpandConfig | false | No description provided |
| `commentary` | Commentary | false | No description provided |
| `canvasStyle` | CanvasStyle | false | No description provided |
| `assignmentColumnMap` | object | false | No description provided |
| `visualGroupMap` | object | false | No description provided |
| `sourceVisualsMeta` | object | false | No description provided |
| `controlPanePosition` | string | false | No description provided |

### EntityVariable

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | Unique variable identifier (e.g., CALC_VARIABLE_xxxxx). |
| `label` | string | true | Display label for the variable. |
| `type` | string | true | Variable type. |
| `scope` | string | true | Variable scope. |
| `technicalName` | string | true | Technical/programmatic name for the variable. |
| `description` | string | false | No description provided |
| `showInViewMode` | boolean | false | No description provided |
| `assignInterface` | boolean | false | No description provided |
| `allowDecimalValues` | boolean | false | No description provided |
| `interfaceType` | string | false | No description provided |
| `value` | object (see schema) | false | No description provided |
| `defaultValue` | object (see schema) | false | No description provided |
| `displayMode` | string | false | No description provided |
| `sourceType` | string | false | No description provided |
| `options` | array | false | No description provided |
| `datasetId` | string | false | No description provided |
| `labelColumn` | string | false | No description provided |
| `valueColumn` | string | false | No description provided |
| `selectedDimension` | string | false | No description provided |
| `radioDirection` | string | false | No description provided |
| `enableActionScript` | boolean | false | No description provided |
| `enableToggle` | boolean | false | No description provided |
| `executeOnInit` | boolean | false | No description provided |
| `onLabel` | string | false | No description provided |
| `offLabel` | string | false | No description provided |
| `activeButton` | ActionButton | false | No description provided |
| `inactiveButton` | ActionButton | false | No description provided |
| `assignValues` | boolean | false | No description provided |
| `showAsPercentage` | boolean | false | No description provided |
| `showAsSlider` | boolean | false | No description provided |
| `interval` | number | false | No description provided |
| `min` | number | false | No description provided |
| `max` | number | false | No description provided |

### ActionButton

| Property | Type | Required | Description |
|---|---|---|---|
| `label` | string | true | No description provided |
| `style` | ButtonStyle | true | No description provided |
| `actions` | ActionScript[] | true | No description provided |

### ButtonStyle

| Property | Type | Required | Description |
|---|---|---|---|
| `backgroundColor` | string | false | No description provided |
| `textColor` | string | false | No description provided |
| `borderColor` | string | false | No description provided |

### ActionScript

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | No description provided |
| `target` | string | true | No description provided |
| `script` | string | true | Action script expression (e.g., SHOW_VISUAL, HIDE_VISUAL). |

### FilterExpandConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `isFilterPaneCollapsed` | boolean | false | No description provided |
| `expandedHeight` | number | false | No description provided |

### Commentary

| Property | Type | Required | Description |
|---|---|---|---|
| `notes` | NotesConfig | false | No description provided |
| `annotation` | AnnotationConfig | false | No description provided |

### NotesConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `notesMap` | object | false | Map of visual IDs to their notes. |
| `settings` | object | false | No description provided |
| `noteOrder` | array | false | No description provided |
| `enableMarkerMode` | boolean | false | No description provided |
| `markerData` | array | false | No description provided |

### AnnotationConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `settings` | object | false | No description provided |

### CanvasStyle

| Property | Type | Required | Description |
|---|---|---|---|
| `dimension` | object | false | No description provided |
| `background` | object | false | No description provided |
| `wallpaper` | object | false | No description provided |
| `border` | object | false | No description provided |
| `shadow` | object | false | No description provided |
| `cornerRadius` | object | false | No description provided |
| `isLocked` | boolean | false | No description provided |
| `gridLineSettings` | object | false | No description provided |
| `showVisualGuide` | boolean | false | No description provided |
| `showSmartGuide` | boolean | false | No description provided |
| `verticalAlign` | string | false | No description provided |
| `scrollToZoom` | boolean | false | No description provided |
| `mobileCanvas` | object | false | No description provided |

### Visual

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | Unique visual identifier. |
| `visualType` | integer | true | Numeric visual type code. |
| `isEmbedded` | boolean | false | No description provided |
| `originEntityId` | object (see schema) | false | Origin entity ID (integer or string). |
| `properties` | VisualProperties | true | No description provided |

### VisualProperties

| Property | Type | Required | Description |
|---|---|---|---|
| `schema` | string | true | No description provided |
| `properties` | VisualConfig | true | No description provided |
| `etag` | string | false | ETag for concurrency control. |

### VisualConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `pivotAssignments` | PivotAssignment[] | false | No description provided |
| `sortingConfig` | array | false | No description provided |
| `superFilterAssignments` | array | false | Visual-level filter assignments. |
| `visualInteractions` | object | false | No description provided |
| `groupName` | string | false | No description provided |
| `visualType` | integer | false | No description provided |
| `chartType` | string | false | Chart type identifier (e.g., COLUMN_VERTICAL, LINE, PIE). |
| `originEntityId` | object (see schema) | false | No description provided |
| `splitByCategory` | object | false | No description provided |
| `transformMeasure` | string | false | No description provided |
| `groupMeasureAssignments` | array | false | No description provided |
| `mobileProperties` | object | false | No description provided |
| `preVisualId` | string | false | No description provided |
| `dimension` | object | false | No description provided |
| `position` | object | false | No description provided |
| `visualStyles` | object | false | Visual styling (background, border, corner radius, padding, shadow, tooltip). |
| `lockAspectRatio` | boolean | false | No description provided |
| `layerProperties` | object | false | No description provided |
| `shapeType` | string | false | No description provided |
| `visualState` | object | false | Internal visual state including hidden properties stored as stringified JSON. |

### PivotAssignment

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | No description provided |
| `sourceId` | string | false | No description provided |
| `bucketId` | string | true | Target bucket (axis, AC, PY, PL, FC, etc.). |
| `columnName` | string | true | No description provided |
| `dataType` | string | true | No description provided |
| `order` | integer | false | No description provided |
| `columnType` | string | false | No description provided |
| `formatString` | string | false | No description provided |
| `contents` | string | false | No description provided |
| `sourceType` | string | false | No description provided |
| `name` | string | false | No description provided |
| `customName` | string | false | No description provided |
| `aggregationType` | string | false | No description provided |
| `isFlatHierarchy` | boolean | false | No description provided |
| `distinctValueCount` | integer | false | No description provided |
| `tableName` | string | false | No description provided |
| `dataRoleType` | string | false | No description provided |

### Intelligence Properties file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/intelligence/properties/1.0.0/schema.json",
  "properties": {
    "schema": "string",
    "properties": {}
  },
  "visuals": [
    {
      "id": "string",
      "visualType": 0,
      "properties": {
        "schema": "string",
        "properties": {}
      }
    }
  ]
}
```
