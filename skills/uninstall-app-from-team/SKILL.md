# Uninstall App from Team

Uninstall an app from a specific team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `DELETE /teams/{team-id}/installedApps/{installation-id}`
- **operationId**: `uninstallAppFromTeam`
- **Tag**: AppInstallations

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `TeamsAppInstallation.ReadWriteForTeam`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |
| installation-id | string | Yes | The unique identifier of the app installation |

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/installedApps/{installation-id}" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```
HTTP/1.1 204 No Content
```

## Instructions

1. Obtain a valid access token with the `TeamsAppInstallation.ReadWriteForTeam` scope.
2. Identify the `team-id` and `installation-id` for the app installation to remove.
3. Send a DELETE request to the endpoint with the required path parameters.
4. A successful response returns HTTP 204 with no content.
