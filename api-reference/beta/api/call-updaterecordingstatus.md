---
title: "call: updateRecordingStatus"
description: "Update the application's recording status associated with a call."
author: "VinodRavichandran"
localization_priority: Normal
ms.prod: "cloud-communications"
doc_type: apiPageType
---

# call: updateRecordingStatus

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the application's recording status associated with a call.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)      |
|:---------------------------------------|:-------------------------------------------------|
| Delegated (work or school account)     | Not Supported                                    |
| Delegated (personal Microsoft account) | Not Supported                                    |
| Application                            | Calls.JoinGroupCalls.All, Calls.AccessMedia.All  |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /app/calls/{id}/updateRecordingStatus
POST /communications/calls/{id}/updateRecordingStatus
```
> **Note:** The `/app` path is deprecated. Going forward, use the `/communications` path.

## Request headers
| Name          | Description               |
|:--------------|:--------------------------|
| Authorization | Bearer {token}. Required. |
| Content-type | application/json. Required. |

## Request body
In the request body, provide a JSON object with the following parameters.

| Parameter       | Type    | Description                                                                           |
|:----------------|:--------|:--------------------------------------------------------------------------------------|
| clientContext   | String  | Unique Client Context string. Max limit is 256 chars.                                 |
| status          | String  | The recording status. Possible values are: `notRecording`, `recording`, or `failed`.  |

## Response
This method returns a `200 OK` response code and a Location header with a URI to the [updateRecordingStatusOperation](../resources/updaterecordingstatusoperation.md) object created for this request.

## Example
The following example shows how to call this API.

### Request
The following example shows the request.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "call-updateRecordingStatus"
}-->
```http
POST https://graph.microsoft.com/beta/communications/calls/{id}/updateRecordingStatus
Content-Type: application/json
Content-Length: 79

{
  "clientContext": "clientContext-value",
  "status": "notRecording | recording | failed"
}
```

---


### Response

> **Note:** The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "name": "call-updateRecordingStatus",
  "truncated": true,
  "@odata.type": "microsoft.graph.updateRecordingStatusOperation"
} -->
```http
HTTP/1.1 200 OK
Location: https://graph.microsoft.com/beta/communications/calls/57dab8b1-894c-409a-b240-bd8beae78896/operations/0fe0623f-d628-42ed-b4bd-8ac290072cc5

{
  "@odata.type": "#microsoft.graph.updateRecordingStatusOperation",
  "clientContext": "clientContext-value",
  "id": "0fe0623f-d628-42ed-b4bd-8ac290072cc5",
  "resultInfo": null,
  "status": "completed"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "call: updateRecordingStatus",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
