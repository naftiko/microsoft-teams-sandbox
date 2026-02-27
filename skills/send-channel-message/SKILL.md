# Send Channel Message

Send a new message to a specific channel within a Microsoft Teams team.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /teams/{team-id}/channels/{channel-id}/messages
- **Operation ID**: sendChannelMessage
- **Tag**: ChatMessages

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `ChannelMessage.Send`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |
| channel-id | string | Yes | The unique identifier of the channel |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| body | object | Yes | The message body containing contentType and content |
| importance | string | No | The importance of the message (normal, high, urgent) |
| mentions | array | No | List of mentions in the message |
| attachments | array | No | List of attachments |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}/messages" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "body": {
      "contentType": "text",
      "content": "Hello team, let'\''s sync up on the project status."
    }
  }'
```

## Example Response

```json
{
  "id": "msg-001",
  "messageType": "message",
  "createdDateTime": "2025-01-20T14:30:00Z",
  "subject": null,
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
  "importance": "normal",
  "attachments": [],
  "mentions": []
}
```

**Status Code**: 201 Created

## Instructions

1. Obtain a valid access token with the `ChannelMessage.Send` scope.
2. Identify the team ID and channel ID for the channel you want to post a message to.
3. Construct the request body with the message content and content type.
4. Send a POST request to the `/teams/{team-id}/channels/{channel-id}/messages` endpoint.
5. Optionally include mentions, attachments, or set the importance level.
6. A successful request returns a 201 status code with the created message object.
