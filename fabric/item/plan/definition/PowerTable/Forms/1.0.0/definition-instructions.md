---
title: PowerTable Forms item definition
description: Learn how to create a PowerTable Forms item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: PowerTable Forms item definition
ms.service: fabric
ms.date: 2026-06-18
---

# PowerTable Forms definition

This article provides a breakdown of the structure for PowerTable Forms definition items.

## Supported formats

PowerTable Forms items support the JSON format.

## Definition parts

This table lists the PowerTable Forms definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | PowerTable Forms (JSON) | {required_placeholder} | Array of form definitions for a PowerTable visual, defining data entry layouts. |

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

## PowerTable Forms

| Property | Type | Required | Description |
|---|---|---|---|

### Form

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `title` | string | true | Form title. |
| `description` | string | false | No description provided |
| `layoutMeta` | LayoutMeta | true | No description provided |
| `config` | FormConfig | false | No description provided |

### LayoutMeta

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | false | Optional layout ID. |
| `children` | FormElement[] | true | Ordered list of form elements. |
| `type` | string | true | No description provided |
| `layoutType` | string | false | No description provided |

### FormElement

| Property | Type | Required | Description |
|---|---|---|---|
| `type` | string | true | Element type. |
| `name` | string | true | Field/column name. |
| `mandatory` | integer | false | No description provided |
| `allowEdit` | integer | false | No description provided |
| `props` | object | false | No description provided |

### FormConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `showTitle` | boolean | false | No description provided |
| `showLogo` | boolean | false | No description provided |
| `submissionMessage` | string | false | No description provided |
| `fieldLabel` | string | false | No description provided |

### PowerTable Forms file example

```json
[
  {
    "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/powerTable/forms/1.0.0/schema.json",
    "title": "string",
    "layoutMeta": {
      "children": [
        {
          "type": "field",
          "name": "string"
        }
      ],
      "type": "form"
    }
  }
]
```
