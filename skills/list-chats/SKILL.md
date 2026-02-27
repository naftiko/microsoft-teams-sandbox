# List Chats

Retrieve the list of chats that the user is part of using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `GET /chats`
- **operationId**: `listChats`
- **Tag**: Chats

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Chat.Read`

## Parameters

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $top | integer | No | The number of results to return |
| $filter | string | No | OData filter expression |
| $expand | string | No | OData expand expression |
| $orderby | string | No | OData order by expression |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/chats" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "19:chat-abc123@thread.v2",
      "topic": "Project Discussion",
      "chatType": "group",
      "createdDateTime": "2025-01-15T09:00:00Z"
    },
    {
      "id": "19:chat-def456@thread.v2",
      "topic": null,
      "chatType": "oneOnOne",
      "createdDateTime": "2025-01-10T08:00:00Z"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `Chat.Read` scope.
2. Send a GET request to the endpoint.
3. Optionally include `$top`, `$filter`, `$expand`, or `$orderby` query parameters to refine results.
4. Parse the response to retrieve the list of chats.
