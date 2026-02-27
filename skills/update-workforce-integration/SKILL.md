# Update Workforce Integration

Update the properties of an existing workforce integration using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: PATCH /teamwork/workforceIntegrations/{workforceIntegration-id}
- **Operation ID**: updateWorkforceIntegration
- **Tag**: WorkforceIntegrations

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations/{workforceIntegration-id}`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `WorkforceIntegration.ReadWrite.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| workforceIntegration-id | string | Yes | The unique identifier of the workforce integration to update. |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| displayName | string | No | The updated display name of the workforce integration. |
| apiVersion | integer | No | The updated API version. |
| isActive | boolean | No | Whether the workforce integration is active. |
| url | string | No | The updated URL of the workforce integration endpoint. |
| supportedEntities | string | No | Updated comma-separated list of supported entities. |

## Example Request

```bash
curl -X PATCH \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations/wfi-001" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}" \
  -d '{
    "displayName": "Kronos Integration v2",
    "apiVersion": 2,
    "isActive": true
  }'
```

## Example Response

```json
{
  "id": "wfi-001",
  "displayName": "Kronos Integration v2",
  "apiVersion": 2,
  "isActive": true,
  "url": "https://kronos.example.com/api/v1/teams",
  "supportedEntities": "shift,timeCard,timeOff"
}
```

## Instructions

1. Obtain a valid access token with the `WorkforceIntegration.ReadWrite.All` scope.
2. Identify the workforce integration to update by its `workforceIntegration-id`.
3. Construct the request body with only the properties you want to update.
4. Send the PATCH request to the workforceIntegrations endpoint.
5. A 200 OK response indicates the workforce integration was successfully updated.
6. The response body contains the full updated workforce integration object.
