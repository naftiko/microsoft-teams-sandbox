# Create Online Meeting

Create a new online meeting for the authenticated user using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /me/onlineMeetings
- **Operation ID**: createOnlineMeeting
- **Tag**: OnlineMeetings

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `OnlineMeetings.ReadWrite`

## Parameters

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| subject | string | No | The subject or topic of the online meeting. |
| startDateTime | string (datetime) | No | The start date and time of the meeting in UTC. |
| endDateTime | string (datetime) | No | The end date and time of the meeting in UTC. |
| allowedPresenters | string | No | Who can present in the meeting (e.g., organization, everyone, roleIsPresenter). |
| isEntryExitAnnounced | boolean | No | Whether to announce when participants enter or exit. |
| participants | object | No | The participants of the meeting including organizer and attendees. |

## Example Request

```bash
curl -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}" \
  -d '{
    "subject": "Sprint Planning",
    "startDateTime": "2025-01-22T09:00:00Z",
    "endDateTime": "2025-01-22T10:00:00Z",
    "allowedPresenters": "organization",
    "isEntryExitAnnounced": true
  }'
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

1. Obtain a valid access token with the `OnlineMeetings.ReadWrite` scope.
2. Construct the request body with the meeting details such as subject, start and end times, and presenter settings.
3. Send the POST request to the onlineMeetings endpoint.
4. A 201 Created response indicates the meeting was successfully created.
5. The response body contains the created meeting object including the `joinWebUrl` for participants to join.
