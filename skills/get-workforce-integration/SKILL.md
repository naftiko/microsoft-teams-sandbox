# Get Workforce Integration

Retrieve a specific workforce integration by its identifier from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teamwork/workforceIntegrations/{workforceIntegration-id}
- **Operation ID**: getWorkforceIntegration
- **Tag**: WorkforceIntegrations

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations/{workforceIntegration-id}`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `WorkforceIntegration.Read.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| workforceIntegration-id | string | Yes | The unique identifier of the workforce integration. |

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations/wfi-001" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
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

1. Obtain a valid access token with the `WorkforceIntegration.Read.All` scope.
2. Identify the workforce integration by its `workforceIntegration-id`.
3. Send the GET request to the workforceIntegrations endpoint with the integration identifier.
4. The response contains the workforce integration details including display name, API version, active status, URL, and supported entities.
