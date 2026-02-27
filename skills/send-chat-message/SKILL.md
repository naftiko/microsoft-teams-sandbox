# Send Chat Message

Send a new message in a specific chat conversation in Microsoft Teams.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /chats/{chat-id}/messages
- **Operation ID**: sendChatMessage
- **Tag**: ChatMessages

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Chat.ReadWrite`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| chat-id | string | Yes | The unique identifier of the chat |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| body | object | Yes | The message body containing contentType and content |
| importance | string | No | The importance of the message (normal, high, urgent) |
| mentions | array | No | List of mentions in the message |
| attachments | array | No | List of attachments |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/chats/{chat-id}/messages" \
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

1. Obtain a valid access token with the `Chat.ReadWrite` scope.
2. Identify the chat ID for the conversation you want to send a message to.
3. Construct the request body with the message content and content type.
4. Send a POST request to the `/chats/{chat-id}/messages` endpoint.
5. Optionally include mentions, attachments, or set the importance level.
6. A successful request returns a 201 status code with the created message object.
