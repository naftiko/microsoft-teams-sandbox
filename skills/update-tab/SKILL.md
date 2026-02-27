# Update Tab

Update the properties of a specific tab in a channel within a team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `PATCH /teams/{team-id}/channels/{channel-id}/tabs/{tab-id}`
- **operationId**: `updateTab`
- **Tag**: Tabs

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

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
curl -X PATCH "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}/tabs/{tab-id}" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "Updated Wiki Tab"
  }'
```

## Example Response

```
HTTP/1.1 204 No Content
```

## Instructions

1. Obtain a valid access token with the `TeamsTab.ReadWrite.All` scope.
2. Identify the `team-id`, `channel-id`, and `tab-id` for the target tab.
3. Construct the request body with the properties to update.
4. Send a PATCH request to the endpoint with the required path parameters and request body.
5. A successful response returns HTTP 204 with no content.
