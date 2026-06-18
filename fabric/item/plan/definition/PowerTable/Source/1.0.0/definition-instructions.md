---
title: PowerTable Source item definition
description: Learn how to create a PowerTable Source item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: PowerTable Source item definition
ms.service: fabric
ms.date: 2026-06-18
---

# PowerTable Source definition

This article provides a breakdown of the structure for PowerTable Source definition items.

## Supported formats

PowerTable Source items support the JSON format.

## Definition parts

This table lists the PowerTable Source definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | PowerTable Source (JSON) | {required_placeholder} | Database source configuration for a PowerTable visual. |

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

## PowerTable Source

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `connection` | ConnectionReferenceOrVar | true | No description provided |
| `database` | ItemReferenceOrVar | true | No description provided |
| `schema` | string | true | No description provided |
| `tableName` | string | true | No description provided |

### PowerTable Source file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/powerTable/source/1.0.0/schema.json",
  "connection": {},
  "tableName": "string",
  "schema": "string",
  "database": {}
}
```
