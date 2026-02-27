# Get Online Meeting

Retrieve a specific online meeting by its identifier for the authenticated user from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /me/onlineMeetings/{meeting-id}
- **Operation ID**: getOnlineMeeting
- **Tag**: OnlineMeetings

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings/{meeting-id}`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `OnlineMeetings.Read`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| meeting-id | string | Yes | The unique identifier of the online meeting. |

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings/meeting-001" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "id": "meeting-001",
  "subject": "Sprint Planning",
  "startDateTime": "2025-01-22T09:00:00Z",
  "endDateTime": "2025-01-22T10:00:00Z",
  "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%3Ameeting_abc123",
  "allowedPresenters": "organization",
  "isEntryExitAnnounced": true
}
```

## Instructions

1. Obtain a valid access token with the `OnlineMeetings.Read` scope.
2. Identify the online meeting by its `meeting-id`.
3. Send the GET request to the onlineMeetings endpoint with the meeting identifier.
4. The response contains the meeting details including subject, times, join URL, and configuration settings.
