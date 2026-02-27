# List Installed Apps

Retrieve the list of apps installed in a specific team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `GET /teams/{team-id}/installedApps`
- **operationId**: `listTeamInstalledApps`
- **Tag**: AppInstallations

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `TeamsAppInstallation.ReadForTeam`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $expand | string | No | OData expand expression |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/installedApps" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "install-001",
      "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/app-id-001"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `TeamsAppInstallation.ReadForTeam` scope.
2. Identify the `team-id` for the target team.
3. Send a GET request to the endpoint with the required path parameter.
4. Optionally include the `$expand` query parameter to retrieve additional details.
5. Parse the response to retrieve the list of installed apps.
