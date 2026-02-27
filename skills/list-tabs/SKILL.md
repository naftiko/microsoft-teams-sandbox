# List Channel Tabs

Retrieve the list of tabs in a specific channel within a team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `GET /teams/{team-id}/channels/{channel-id}/tabs`
- **operationId**: `listTabs`
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

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $filter | string | No | OData filter expression |
| $expand | string | No | OData expand expression |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}/tabs" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "tab-id-001",
      "displayName": "Project Wiki",
      "webUrl": "https://teams.microsoft.com/l/entity/com.microsoft.teamspace.tab.wiki"
    },
    {
      "id": "tab-id-002",
      "displayName": "Task Board",
      "webUrl": "https://teams.microsoft.com/l/entity/com.microsoft.teamspace.tab.planner"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `TeamsTab.Read.All` scope.
2. Identify the `team-id` and `channel-id` for the target channel.
3. Send a GET request to the endpoint with the required path parameters.
4. Optionally include `$filter` or `$expand` query parameters to refine results.
5. Parse the response to retrieve the list of tabs in the channel.
