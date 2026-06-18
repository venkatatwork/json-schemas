---
title: Definition item definition
description: Learn how to create a Definition item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: Definition item definition
ms.service: fabric
ms.date: 2026-06-18
---

# Definition definition

This article provides a breakdown of the structure for Definition definition items.

## Supported formats

Definition items support the JSON format.

## Definition parts

This table lists the Definition definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | Definition (JSON) | {required_placeholder} | Root definition for a Plan artifact containing semantic model references and sheet declarations. |

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

## Definition

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `semanticModelReference` | SemanticModelReference | true | No description provided |
| `sheets` | SheetReference[] | true | List of sheets in the plan. |

### SemanticModelReference

| Property | Type | Required | Description |
|---|---|---|---|
| `connection` | ConnectionReferenceOrVar | true | No description provided |
| `semanticModel` | ItemReferenceOrVar | true | No description provided |

### SheetReference

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | Unique identifier for the sheet. |
| `displayName` | string | true | User-facing name of the sheet. |
| `sheetType` | string | true | The type of sheet. |

### Definition file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/definition/1.0.0/schema.json",
  "semanticModelReference": {
    "connection": {},
    "semanticModel": {}
  },
  "sheets": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "displayName": "string",
      "sheetType": "Planning"
    }
  ]
}
```
