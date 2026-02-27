# Get Tab

Retrieve the properties and relationships of a specific tab in a channel within a team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `GET /teams/{team-id}/channels/{channel-id}/tabs/{tab-id}`
- **operationId**: `getTab`
- **Tag**: Tabs

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `TeamsTab.Read.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |
| channel-id | string | Yes | The unique identifier of the channel |
| tab-id | string | Yes | The unique identifier of the tab |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}/tabs/{tab-id}" \
  -H "Authorization: Bearer {access_token}"
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

1. Obtain a valid access token with the `TeamsTab.Read.All` scope.
2. Identify the `team-id`, `channel-id`, and `tab-id` for the target tab.
3. Send a GET request to the endpoint with the required path parameters.
4. Parse the response to retrieve the tab properties and configuration.
