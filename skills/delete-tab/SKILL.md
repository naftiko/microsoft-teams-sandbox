# Remove Tab

Remove a tab from a specific channel within a team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `DELETE /teams/{team-id}/channels/{channel-id}/tabs/{tab-id}`
- **operationId**: `deleteTab`
- **Tag**: Tabs

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `TeamsTab.ReadWrite.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |
| channel-id | string | Yes | The unique identifier of the channel |
| tab-id | string | Yes | The unique identifier of the tab |

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}/tabs/{tab-id}" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```
HTTP/1.1 204 No Content
```

## Instructions

1. Obtain a valid access token with the `TeamsTab.ReadWrite.All` scope.
2. Identify the `team-id`, `channel-id`, and `tab-id` for the tab to remove.
3. Send a DELETE request to the endpoint with the required path parameters.
4. A successful response returns HTTP 204 with no content.
