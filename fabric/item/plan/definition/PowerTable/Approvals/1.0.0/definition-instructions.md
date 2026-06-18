---
title: PowerTable Approvals item definition
description: Learn how to create a PowerTable Approvals item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: PowerTable Approvals item definition
ms.service: fabric
ms.date: 2026-06-18
---

# PowerTable Approvals definition

This article provides a breakdown of the structure for PowerTable Approvals definition items.

## Supported formats

PowerTable Approvals items support the JSON format.

## Definition parts

This table lists the PowerTable Approvals definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | PowerTable Approvals (JSON) | {required_placeholder} | Approval workflow configuration for a PowerTable visual. |

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

## PowerTable Approvals

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `ruleType` | integer | true | Numeric code for approval rule type. |
| `persistFlag` | integer | false | Numeric code controlling persistence behavior. |
| `settings` | object | false | Approval-specific settings payload. |
| `approvalLevel` | integer | false | Current or default approval level. |
| `multiLevelEnabled` | integer | false | Whether multi-level approvals are enabled (0/1). |
| `approvalLevels` | ApprovalLevel[] | false | Configured approval levels. |
| `approvalFilter` | ApprovalFilter[] | false | Filters applied to approval routing. |

### ApprovalLevel

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | No description provided |
| `description` | string | true | No description provided |
| `level` | integer | true | No description provided |

### ApprovalFilter

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | No description provided |
| `filter` | object or null | true | No description provided |
| `order` | integer | true | No description provided |

### PowerTable Approvals file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/powerTable/approvals/1.0.0/schema.json",
  "ruleType": 0
}
```
