# List Message Replies

List all replies to a specific message in a channel within a Microsoft Teams team.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teams/{team-id}/channels/{channel-id}/messages/{message-id}/replies
- **Operation ID**: listMessageReplies
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
| message-id | string | Yes | The unique identifier of the message |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}/messages/{message-id}/replies" \
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
2. Identify the team ID, channel ID, and message ID for the message whose replies you want to retrieve.
3. Send a GET request to the `/teams/{team-id}/channels/{channel-id}/messages/{message-id}/replies` endpoint.
4. Parse the `value` array in the response to access individual reply message objects.
