# List Channel Messages

List all messages in a specific channel within a Microsoft Teams team.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teams/{team-id}/channels/{channel-id}/messages
- **Operation ID**: listChannelMessages
- **Tag**: ChatMessages

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `ChannelMessage.Read.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |
| channel-id | string | Yes | The unique identifier of the channel |

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $top | integer | No | The number of results to return |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}/messages?$top=10" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json"
```

## Example Response

```json
{
  "value": [
    {
      "id": "msg-001",
      "messageType": "message",
      "createdDateTime": "2025-01-20T14:30:00Z",
      "body": {
        "contentType": "text",
        "content": "Hello team, let's sync up on the project status."
      },
      "from": {
        "user": {
          "id": "user-001",
          "displayName": "Jane Smith"
        }
      },
      "importance": "normal"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `ChannelMessage.Read.All` scope.
2. Identify the team ID and channel ID for the channel you want to retrieve messages from.
3. Send a GET request to the `/teams/{team-id}/channels/{channel-id}/messages` endpoint.
4. Use the `$top` query parameter to limit the number of messages returned.
5. Parse the `value` array in the response to access individual message objects.
