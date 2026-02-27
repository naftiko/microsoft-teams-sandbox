# Get Call

Retrieve the details of an existing call in Microsoft Teams communications.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /communications/calls/{call-id}
- **Operation ID**: getCall
- **Tag**: Calls

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Calls.Initiate.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| call-id | string | Yes | The unique identifier of the call |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls/{call-id}" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json"
```

## Example Response

```json
{
  "id": "call-001",
  "state": "established",
  "direction": "outgoing",
  "callbackUri": "https://bot.example.com/api/calls",
  "requestedModalities": [
    "audio"
  ],
  "tenantId": "tenant-001"
}
```

## Instructions

1. Obtain a valid access token with the `Calls.Initiate.All` scope.
2. Identify the call ID for the call you want to retrieve.
3. Send a GET request to the `/communications/calls/{call-id}` endpoint.
4. The response contains the call details including state, direction, callback URI, modalities, and tenant ID.
