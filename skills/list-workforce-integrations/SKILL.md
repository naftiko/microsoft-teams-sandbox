# List Workforce Integrations

Retrieve a list of workforce integrations from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teamwork/workforceIntegrations
- **Operation ID**: listWorkforceIntegrations
- **Tag**: WorkforceIntegrations

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `WorkforceIntegration.Read.All`

## Parameters

No parameters required.

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "wfi-001",
      "displayName": "Kronos Integration",
      "apiVersion": 1,
      "isActive": true,
      "url": "https://kronos.example.com/api/v1/teams",
      "supportedEntities": "shift,timeCard,timeOff"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `WorkforceIntegration.Read.All` scope.
2. Send the GET request to the workforceIntegrations endpoint.
3. The response contains a `value` array of workforce integration objects.
4. Each integration includes its id, display name, API version, active status, URL, and supported entities.
5. Supported entities can include: shift, timeCard, timeOff, and other workforce management objects.
