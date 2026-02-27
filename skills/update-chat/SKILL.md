# Update Chat

Update the properties of a specific chat using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `PATCH /chats/{chat-id}`
- **operationId**: `updateChat`
- **Tag**: Chats

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

## Example Request

```bash
curl -X PATCH "http://localhost:8080/rest/microsoft-teams-api/1.0.0/chats/{chat-id}" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "topic": "Updated Project Discussion"
  }'
```

## Example Response

```json
{
  "id": "19:chat-abc123@thread.v2",
  "topic": "Updated Project Discussion",
  "chatType": "group",
  "createdDateTime": "2025-01-15T09:00:00Z",
  "lastUpdatedDateTime": "2025-01-20T14:30:00Z"
}
```

## Instructions

1. Obtain a valid access token with the `Chat.ReadWrite` scope.
2. Identify the `chat-id` for the target chat.
3. Construct the request body with the properties to update.
4. Send a PATCH request to the endpoint with the required path parameter and request body.
5. A successful response returns HTTP 200 with the updated chat details.
