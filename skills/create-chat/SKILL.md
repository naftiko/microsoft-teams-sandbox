# Create Chat

Create a new chat using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `POST /chats`
- **operationId**: `createChat`
- **Tag**: Chats

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Chat.Create`

## Parameters

### Request Body

The request body should contain the chat properties including chat type, topic, and members.

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/chats" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "chatType": "group",
    "topic": "Project Discussion",
    "members": [
      {
        "@odata.type": "#microsoft.graph.aadUserConversationMember",
        "roles": ["owner"],
        "user@odata.bind": "https://graph.microsoft.com/v1.0/users/user-id-001"
      },
      {
        "@odata.type": "#microsoft.graph.aadUserConversationMember",
        "roles": ["owner"],
        "user@odata.bind": "https://graph.microsoft.com/v1.0/users/user-id-002"
      }
    ]
  }'
```

## Example Response

```json
{
  "id": "19:chat-abc123@thread.v2",
  "topic": "Project Discussion",
  "chatType": "group",
  "createdDateTime": "2025-01-15T09:00:00Z",
  "lastUpdatedDateTime": "2025-01-20T14:30:00Z"
}
```

## Instructions

1. Obtain a valid access token with the `Chat.Create` scope.
2. Construct the request body with the chat type, optional topic, and member list.
3. Send a POST request to the endpoint with the request body.
4. A successful response returns HTTP 201 with the created chat details.
