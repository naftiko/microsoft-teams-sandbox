# List Chat Messages

List all messages in a specific chat conversation in Microsoft Teams.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /chats/{chat-id}/messages
- **Operation ID**: listChatMessages
- **Tag**: ChatMessages

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Chat.Read`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| chat-id | string | Yes | The unique identifier of the chat |

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $top | integer | No | The number of results to return |
| $orderby | string | No | Order results by a specific field |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/chats/{chat-id}/messages?$top=10" \
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

1. Obtain a valid access token with the `Chat.Read` scope.
2. Identify the chat ID for the conversation you want to retrieve messages from.
3. Send a GET request to the `/chats/{chat-id}/messages` endpoint.
4. Use the `$top` query parameter to limit the number of messages returned.
5. Use the `$orderby` query parameter to sort results by a specific field such as `createdDateTime`.
6. Parse the `value` array in the response to access individual message objects.
