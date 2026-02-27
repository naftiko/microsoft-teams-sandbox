# Install App to Team

Install an app to a specific team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `POST /teams/{team-id}/installedApps`
- **operationId**: `installAppToTeam`
- **Tag**: AppInstallations

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `TeamsAppInstallation.ReadWriteForTeam`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/installedApps" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/app-id-001"
  }'
```

## Example Response

```json
{
  "id": "install-001",
  "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/app-id-001"
}
```

## Instructions

1. Obtain a valid access token with the `TeamsAppInstallation.ReadWriteForTeam` scope.
2. Identify the `team-id` for the target team.
3. Construct the request body with the `teamsApp@odata.bind` reference to the app in the catalog.
4. Send a POST request to the endpoint with the required path parameter and request body.
5. A successful response returns HTTP 201 with the installation details.
