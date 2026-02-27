# Get My Presence

Retrieve the presence information for the authenticated user from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /me/presence
- **Operation ID**: getMyPresence
- **Tag**: Presence

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/presence`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Presence.Read`

## Parameters

No parameters required.

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/presence" \
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

1. Obtain a valid access token with the `Presence.Read` scope.
2. Send the GET request to the presence endpoint.
3. The response contains the authenticated user's presence information including availability and activity status.
4. Common availability values include: Available, Busy, DoNotDisturb, BeRightBack, Away, Offline.
5. Common activity values include: Available, InACall, InAMeeting, Presenting, OutOfOffice, OffWork.
