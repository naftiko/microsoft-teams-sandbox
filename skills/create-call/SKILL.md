# Create Call

Create a new call in Microsoft Teams communications.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /communications/calls
- **Operation ID**: createCall
- **Tag**: Calls

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Calls.Initiate.All`

## Parameters

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| callbackUri | string | Yes | The callback URL for call state notifications |
| requestedModalities | array | Yes | The modalities for the call (audio, video) |
| targets | array | No | The list of participants to call |
| tenantId | string | No | The tenant identifier |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "callbackUri": "https://bot.example.com/api/calls",
    "requestedModalities": ["audio"],
    "tenantId": "tenant-001"
  }'
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

**Status Code**: 201 Created

## Instructions

1. Obtain a valid access token with the `Calls.Initiate.All` scope.
2. Construct the request body with the required `callbackUri` and `requestedModalities`.
3. Optionally specify `targets` to define the participants and `tenantId` for the tenant context.
4. Send a POST request to the `/communications/calls` endpoint.
5. A successful request returns a 201 status code with the created call object.
6. Monitor the `callbackUri` for call state change notifications.
