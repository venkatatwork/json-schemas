---
title: PowerTable Settings item definition
description: Learn how to create a PowerTable Settings item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: PowerTable Settings item definition
ms.service: fabric
ms.date: 2026-06-18
---

# PowerTable Settings definition

This article provides a breakdown of the structure for PowerTable Settings definition items.

## Supported formats

PowerTable Settings items support the JSON format.

## Definition parts

This table lists the PowerTable Settings definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | PowerTable Settings (JSON) | {required_placeholder} | Settings/permission configurations for a PowerTable visual. |

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

## PowerTable Settings

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `settings` | Setting[] | true | No description provided |

### Setting

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | Setting name. |
| `accessType` | string | false | Who has access to this setting. |
| `meta` | object | false | No description provided |
| `rules` | AccessRule[] | false | Access rules for this setting. |
| `settings` | object (see schema) | false | Setting-specific configuration. |

### AccessRule

| Property | Type | Required | Description |
|---|---|---|---|
| `ruleId` | string | true | No description provided |
| `ruleName` | string | true | No description provided |
| `filter` | object | false | No description provided |
| `filterUsers` | string[] | false | No description provided |

### RowIdentifierSettings

| Property | Type | Required | Description |
|---|---|---|---|
| `rowIdentifier` | string | true | Column name used as the row identifier. |

### CommentSettings

| Property | Type | Required | Description |
|---|---|---|---|
| `notification` | boolean | false | No description provided |
| `rowLevelComments` | boolean | false | No description provided |
| `toggleAddonColumns` | boolean | false | No description provided |
| `displayComment` | boolean | false | No description provided |

### SCDSettings

| Property | Type | Required | Description |
|---|---|---|---|
| `type` | integer | true | SCD type (2 or 3). |
| `enabled` | boolean | true | No description provided |
| `config` | object | false | No description provided |

### PowerTable Settings file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/powerTable/settings/1.0.0/schema.json",
  "settings": [
    {
      "name": "ROW_ADD"
    }
  ]
}
```
