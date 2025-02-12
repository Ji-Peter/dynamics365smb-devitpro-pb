---
title: cloudMigrationCompany resource type
description: A cloud migration company object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: "dynamics365-business-central"
ms.topic: reference
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/25/2022
ms.author: solsen
---

# cloudMigrationCompany resource type

<!-- START>DO_NOT_EDIT -->
<!-- IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT. -->
Represents a cloud migration company in [!INCLUDE[prod_short](../../../includes/prod_short.md)].

> [!NOTE]
> For information about enabling APIs for [!INCLUDE[prod_short](../../../includes/prod_short.md)] see [guideline](../../../api-reference/v2.0/endpoints-apis-for-dynamics.md).

## Methods

| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET cloudMigrationCompany](../api/dynamics_cloudmigrationcompany_get.md)|cloudMigrationCompany|Gets a cloud migration company object.|
|[PATCH cloudMigrationCompany](../api/dynamics_cloudmigrationcompany_update.md)|cloudMigrationCompany|Updates a cloud migration company object.|

## Bound Actions

The cloudMigrationCompany resource type offers a bound action called `createCompaniesMarkedForReplication` which create companies marked for replications the corresponding cloudMigrationCompany batch.
This is illustrated in the following example:
`CREATECOMPANIESMARKEDFORREPLICATION https://<server address>:<server API port>/<server instance name>/api/v1.0/companies({id})/cloudMigrationCompanys({id})/Microsoft.NAV.createCompaniesMarkedForReplication`

The response has no content; the response code is 204.


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the cloud migration company. Non-editable.|
|name|string|Represents the cloud migration company's name.|
|replicate|boolean|This property decides if the company should be selected for cloud migration in the current batch. You can include or exclude the companies.|
|displayName|string|Specifies the cloud migration company's name. This name will appear on all sales documents for the cloud migration company.|
|estimatedSize|decimal|Read-Only property representing the approximate size of the On-Prem company. The data migrated will be smaller, since the data will be compressed and not all tables will be included.|
|status|string|Specifies the status of the company. Possible values are:<br>- “ “ –  initial status or created. Check the created property<br>- “In Progress” – Company creation is in progress <br>- Error – Company creation has failed <br>- "Missing Permission" – User has no permissions to create a company.|
|created|boolean|Specifies if the company was created. It will not reflect if the setup of the company was correct or not. For this you should check the status property. If the company has been created, however status is different.|

## JSON representation

Here is a JSON representation of the cloudMigrationCompany resource.


```json
{
    "id": "GUID",
    "name": "string",
    "replicate": "boolean",
    "displayName": "string",
    "estimatedSize": "decimal",
    "status": "string",
    "created": "boolean"
}
```
<!-- IMPORTANT: END>DO_NOT_EDIT -->

## See Also
[GET cloudMigrationCompany](../api/dynamics_cloudmigrationcompany_get.md)  
[PATCH cloudMigrationCompany](../api/dynamics_cloudmigrationcompany_update.md)
