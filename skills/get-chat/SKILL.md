# Get Chat

Retrieve the properties and relationships of a specific chat using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `GET /chats/{chat-id}`
- **operationId**: `getChat`
- **Tag**: Chats

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Chat.Read`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| chat-id | string | Yes | The unique identifier of the chat |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/chats/{chat-id}" \
  -H "Authorization: Bearer {access_token}"
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

1. Obtain a valid access token with the `Chat.Read` scope.
2. Identify the `chat-id` for the target chat.
3. Send a GET request to the endpoint with the required path parameter.
4. Parse the response to retrieve the chat properties.
