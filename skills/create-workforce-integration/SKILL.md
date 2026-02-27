# Create Workforce Integration

Create a new workforce integration using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /teamwork/workforceIntegrations
- **Operation ID**: createWorkforceIntegration
- **Tag**: WorkforceIntegrations

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `WorkforceIntegration.ReadWrite.All`

## Parameters

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| displayName | string | Yes | The display name of the workforce integration. |
| apiVersion | integer | No | The API version of the workforce integration. |
| isActive | boolean | No | Whether the workforce integration is active. |
| url | string | Yes | The URL of the workforce integration endpoint. |
| supportedEntities | string | No | Comma-separated list of supported entities (e.g., shift, timeCard, timeOff). |
| encryption | object | No | Encryption configuration for the integration. |

## Example Request

```bash
curl -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}" \
  -d '{
    "displayName": "Kronos Integration",
    "apiVersion": 1,
    "isActive": true,
    "url": "https://kronos.example.com/api/v1/teams",
    "supportedEntities": "shift,timeCard,timeOff"
  }'
```

## Example Response

```json
{
  "id": "wfi-001",
  "displayName": "Kronos Integration",
  "apiVersion": 1,
  "isActive": true,
  "url": "https://kronos.example.com/api/v1/teams",
  "supportedEntities": "shift,timeCard,timeOff"
}
```

## Instructions

1. Obtain a valid access token with the `WorkforceIntegration.ReadWrite.All` scope.
2. Construct the request body with the workforce integration details including display name, URL, and supported entities.
3. Send the POST request to the workforceIntegrations endpoint.
4. A 201 Created response indicates the workforce integration was successfully created.
5. The response body contains the created workforce integration object with its assigned id.
