---
title: ConnectedPlanning Infobridge item definition
description: Learn how to create a ConnectedPlanning Infobridge item definition when using the Microsoft Fabric REST API.
author: {author_placeholder}
ms.author: {author_placeholder}
ms.title: ConnectedPlanning Infobridge item definition
ms.service: fabric
ms.date: 2026-06-18
---

# ConnectedPlanning Infobridge definition

This article provides a breakdown of the structure for ConnectedPlanning Infobridge definition items.

## Supported formats

ConnectedPlanning Infobridge items support the JSON format.

## Definition parts

This table lists the ConnectedPlanning Infobridge definition parts.

| Definition part path | Type | Required | Description |
|---|---|---|---|
| `{fileName}` | ConnectedPlanning Infobridge (JSON) | {required_placeholder} | InfoBridge configuration defining data sources, queries, transformation steps, and writeback destinations for connected planning. |

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

## ConnectedPlanning Infobridge

| Property | Type | Required | Description |
|---|---|---|---|
| `$schema` | string | true | No description provided |
| `sources` | Source[] | true | List of InfoBridge data sources. |
| `queryGroups` | QueryGroup[] | false | Optional groupings of queries for organizational purposes. |

### Source

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | The display name of the source. |
| `type` | object (see schema) | true | The source type. Supports known string or numeric codes. |
| `visualId` | object (see schema) | false | The visual identifier this source is associated with. Can be numeric internal ID or UUID in external definitions. |
| `meta` | object (see schema) | false | Source metadata. |
| `queries` | Query[] | false | List of queries for this source. |
| `dependentQueries` | string[] | false | List of dependent query GUIDs for join sources. |

### SourceMeta

| Property | Type | Required | Description |
|---|---|---|---|
| `includeMeasures` | string[] | false | No description provided |
| `includeScenarios` | string[] | false | No description provided |
| `queries` | JoinQueryReference[] | false | Join query references (for join sources). |
| `joinType` | string | false | The join type (e.g, INNER, LEFT, etc.). |
| `sql` | string | false | Optional SQL text for SQL source. |

### JoinQueryReference

| Property | Type | Required | Description |
|---|---|---|---|
| `queryId` | string | false | The GUID of the referenced query. |
| `sourceId` | object (see schema) | false | Internal numeric source/query identifier. |
| `sourceName` | string | true | The display name of the source query. |
| `joinColumnName` | string[] | true | Column names used for the join. |
| `isBaseQuery` | boolean | false | Whether this is the base query in the join. |

### Query

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | The display name of the query. |
| `type` | object (see schema) | false | The query type (string or numeric code). |
| `visualId` | object (see schema) | false | The visual identifier (numeric internal ID or UUID in external definitions). |
| `meta` | object | false | Query-level metadata. |
| `queryId` | string | true | The unique GUID for this query. |
| `transformationSteps` | TransformationStep[] | false | Ordered list of transformation steps. |
| `writebackSettings` | WritebackSettings | false | Writeback settings for this query. |
| `writebackDestinations` | WritebackDestination[] | false | List of writeback destinations. |

### TransformationStep

| Property | Type | Required | Description |
|---|---|---|---|
| `stepIndex` | integer | true | The ordinal index of this step. |
| `meta` | TransformationStepMeta | true | Step metadata including type, name, and description. |
| `notes` | object (see schema) | false | Optional notes for the step. |

### TransformationStepMeta

| Property | Type | Required | Description |
|---|---|---|---|
| `type` | object (see schema) | true | The transformation type (e.g., PLANNING, XLSX, or numeric code). |
| `name` | string | true | The display name of the step. |
| `value` | object | false | Step-specific configuration values. |
| `description` | string | false | A human-readable description of the step. |

### WritebackSettings

| Property | Type | Required | Description |
|---|---|---|---|
| `writebackMeta` | object | false | No description provided |

### WritebackDestination

| Property | Type | Required | Description |
|---|---|---|---|
| `connection` | ConnectionReferenceOrVar | false | No description provided |
| `database` | ItemReferenceOrVar | false | No description provided |
| `schema` | string | false | No description provided |
| `tableName` | string | true | No description provided |
| `connectionId` | string | false | No description provided |
| `dmtsConnectionId` | string | false | Legacy/writeback connection id variable used by connected planning examples. |
| `databaseId` | string | false | No description provided |
| `connectionIdVariable` | string | false | No description provided |
| `settingsHash` | string | false | No description provided |
| `settings` | object | false | No description provided |

### QueryGroup

| Property | Type | Required | Description |
|---|---|---|---|
| `name` | string | true | The group display name. |
| `description` | string | false | Optional group description. |
| `parentGroupId` | integer | false | Optional parent group id for hierarchy. |
| `queryIds` | string[] | true | List of query GUIDs belonging to this group. |

### ConnectedPlanning Infobridge file example

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/plan/definition/connectedPlanning/infobridge/1.0.0/schema.json",
  "sources": [
    {
      "name": "string",
      "type": "PLANNING"
    }
  ]
}
```
