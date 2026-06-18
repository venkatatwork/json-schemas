---
title: PowerTable Automations item definition
description: Learn how to create a PowerTable Automations item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: PowerTable Automations item definition
ms.service: fabric
ms.date: 2026-06-18
---

# PowerTable Automations definition

This article provides a breakdown of the structure for PowerTable Automations definition items.

## Supported formats

PowerTable Automations items support the JSON format.

## Definition parts

This table lists the PowerTable Automations definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | PowerTable Automations (JSON) | {required_placeholder} | Array of automation definitions for a PowerTable visual, defining triggers and action flows. |

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

## PowerTable Automations

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `automations` | Automation[] | true | No description provided |

### Automation

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | Display name of the automation. |
| `triggerType` | integer | true | Numeric code for the trigger type. |
| `config` | AutomationConfig | true | No description provided |

### AutomationConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | No description provided |
| `trigger` | Trigger | true | No description provided |
| `entryGroupId` | string | true | ID of the first action group to execute. |
| `groups` | object | true | Map of group IDs to action groups. |

### Trigger

| Property | Type | Required | Description |
|---|---|---|---|
| `id` | string | true | Unique trigger identifier. |
| `triggerType` | string | true | Trigger type code. |
| `description` | string | false | No description provided |
| `triggerConfig` | object | false | No description provided |

### ActionGroup

| Property | Type | Required | Description |
|---|---|---|---|
| `groupId` | string | true | No description provided |
| `groupType` | string | true | Group type code. |
| `previousGroupId` | string or null | false | No description provided |
| `nextGroupId` | string or null | false | No description provided |
| `entryActionId` | string | true | ID of the first action in this group. |
| `actions` | object | true | Map of action IDs to action definitions. |
| `position` | integer | false | No description provided |

### Action

| Property | Type | Required | Description |
|---|---|---|---|
| `actionId` | string | true | No description provided |
| `actionType` | string | true | Action type code. |
| `previousActionId` | string or null | false | No description provided |
| `nextActionId` | string or null | false | No description provided |
| `config` | object | true | Action-specific configuration. |

### CreateRecordConfig

| Property | Type | Required | Description |
|---|---|---|---|
| `description` | string | false | No description provided |
| `fields` | object | false | Field name to value mapping for the new record. |
| `connectionId` | string | true | Connection identifier (may use variable substitution). |
| `table` | string | true | Target table for the record. |

### PowerTable Automations file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/powerTable/automations/1.0.0/schema.json",
  "automations": [
    {
      "name": "string",
      "triggerType": 0,
      "config": {
        "name": "string",
        "trigger": {
          "id": "string",
          "triggerType": "string"
        },
        "entryGroupId": "string",
        "groups": {}
      }
    }
  ]
}
```
