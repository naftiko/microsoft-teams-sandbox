# Add Tab to Channel

Add a new tab to a specific channel within a team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `POST /teams/{team-id}/channels/{channel-id}/tabs`
- **operationId**: `createTab`
- **Tag**: Tabs

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `TeamsTab.Create`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |
| channel-id | string | Yes | The unique identifier of the channel |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}/tabs" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "Project Wiki",
    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/com.microsoft.teamspace.tab.wiki",
    "configuration": {
      "entityId": "wiki-001",
      "contentUrl": "https://teams.microsoft.com/l/entity/com.microsoft.teamspace.tab.wiki/tab-id-001",
      "websiteUrl": "https://wiki.example.com/project"
    }
  }'
```

## Example Response

```json
{
  "id": "tab-id-001",
  "displayName": "Project Wiki",
  "webUrl": "https://teams.microsoft.com/l/entity/com.microsoft.teamspace.tab.wiki",
  "configuration": {
    "entityId": "wiki-001",
    "contentUrl": "https://teams.microsoft.com/l/entity/com.microsoft.teamspace.tab.wiki/tab-id-001",
    "websiteUrl": "https://wiki.example.com/project"
  }
}
```

## Instructions

1. Obtain a valid access token with the `TeamsTab.Create` scope.
2. Identify the `team-id` and `channel-id` for the target channel.
3. Construct the request body with the tab display name, app binding, and configuration.
4. Send a POST request to the endpoint with the required path parameters and request body.
5. A successful response returns HTTP 201 with the created tab details.
