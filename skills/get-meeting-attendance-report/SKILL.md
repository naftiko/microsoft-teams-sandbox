# Get Meeting Attendance Report

Retrieve the attendance report for a specific online meeting from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /me/onlineMeetings/{meeting-id}/meetingAttendanceReport
- **Operation ID**: getMeetingAttendanceReport
- **Tag**: OnlineMeetings

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings/{meeting-id}/meetingAttendanceReport`

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
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings/meeting-001/meetingAttendanceReport" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "id": "report-001",
  "totalParticipantCount": 12,
  "meetingStartDateTime": "2025-01-22T09:00:00Z",
  "meetingEndDateTime": "2025-01-22T10:00:00Z",
  "attendanceRecords": [
    {
      "emailAddress": "jane@example.com",
      "totalAttendanceInSeconds": 3540,
      "role": "Presenter",
      "identity": {
        "id": "user-001",
        "displayName": "Jane Smith"
      }
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `OnlineMeetings.Read` scope.
2. Identify the online meeting by its `meeting-id`.
3. Send the GET request to the meetingAttendanceReport endpoint.
4. The response contains the attendance report including total participant count, meeting times, and individual attendance records.
5. Each attendance record includes the participant's email, total attendance time in seconds, role, and identity information.
