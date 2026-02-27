# Transfer Call

Transfer an active call to another participant or endpoint using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /communications/calls/{call-id}/transfer
- **Operation ID**: transferCall
- **Tag**: CallIvr

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls/{call-id}/transfer`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Calls.Initiate.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| call-id | string | Yes | The unique identifier of the call to transfer. |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| transferTarget | InvitationParticipantInfo | Yes | The transfer target participant information including identity and replacement. |
| clientContext | string | No | The client context for correlating the request with callbacks. |

## Example Request

```bash
curl -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls/call-001/transfer" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}" \
  -d '{
    "transferTarget": {
      "identity": {
        "user": {
          "id": "user-002",
          "displayName": "John Doe"
        }
      }
    },
    "clientContext": "transfer-context-001"
  }'
```

## Example Response

```
HTTP/1.1 202 Accepted
```

## Instructions

1. Obtain a valid access token with the required scopes.
2. Identify the active call by its `call-id`.
3. Construct the request body with the `transferTarget` containing the target participant identity.
4. Optionally include a `clientContext` string for correlating the transfer request with subsequent callbacks.
5. Send the POST request to the transfer endpoint.
6. A 202 Accepted response indicates the transfer request has been accepted and is being processed.
