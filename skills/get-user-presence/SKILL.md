# Get User Presence

Retrieve the presence information for a specific user by their identifier from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /users/{user-id}/presence
- **Operation ID**: getUserPresence
- **Tag**: Presence

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/users/{user-id}/presence`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Presence.Read.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| user-id | string | Yes | The unique identifier of the user whose presence to retrieve. |

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/users/user-001/presence" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "id": "user-001",
  "availability": "Available",
  "activity": "Available"
}
```

## Instructions

1. Obtain a valid access token with the `Presence.Read.All` scope.
2. Identify the target user by their `user-id`.
3. Send the GET request to the user presence endpoint.
4. The response contains the specified user's presence information including availability and activity status.
5. Common availability values include: Available, Busy, DoNotDisturb, BeRightBack, Away, Offline.
6. Common activity values include: Available, InACall, InAMeeting, Presenting, OutOfOffice, OffWork.
