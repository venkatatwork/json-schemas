---
title: Scenarios item definition
description: Learn how to create a Scenarios item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: Scenarios item definition
ms.service: fabric
ms.date: 2026-06-18
---

# Scenarios definition

This article provides a breakdown of the structure for Scenarios definition items.

## Supported formats

Scenarios items support the JSON format.

## Definition parts

This table lists the Scenarios definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | Scenarios (JSON) | {required_placeholder} | Array of scenario definitions for a Planning visual. |

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

## Scenarios

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `scenarios` | Scenario[] | true | No description provided |

### Scenario

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | Display name of the scenario. |
| `status` | string | true | Current status of the scenario. |
| `meta` | ScenarioMeta | true | No description provided |
| `autoWritebackEnabled` | string | false | Whether auto-writeback is enabled. |
| `simulations` | array or null | false | List of simulations associated with this scenario. |
| `userPermission` | object[] | false | User permissions for this scenario. |

### ScenarioMeta

| Property | Type | Required | Description |
|---|---|---|---|
| `measureIds` | string[] | true | List of measure IDs included in this scenario. |
| `scenarioGuid` | string | true | Unique identifier for the scenario. |
| `order` | integer | true | Display order of the scenario. |
| `dimensionHash` | string | false | Hash representing the dimension configuration. |

### Scenarios file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/planning/scenarios/1.0.0/schema.json",
  "scenarios": [
    {
      "name": "string",
      "status": "ACTIVE",
      "meta": {
        "measureIds": [
          "string"
        ],
        "scenarioGuid": "string",
        "order": 0
      }
    }
  ]
}
```
