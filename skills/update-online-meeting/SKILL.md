# Update Online Meeting

Update the properties of an existing online meeting for the authenticated user using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: PATCH /me/onlineMeetings/{meeting-id}
- **Operation ID**: updateOnlineMeeting
- **Tag**: OnlineMeetings

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings/{meeting-id}`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `OnlineMeetings.ReadWrite`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| meeting-id | string | Yes | The unique identifier of the online meeting to update. |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| subject | string | No | The updated subject or topic of the meeting. |
| startDateTime | string (datetime) | No | The updated start date and time in UTC. |
| endDateTime | string (datetime) | No | The updated end date and time in UTC. |
| allowedPresenters | string | No | Who can present in the meeting. |
| isEntryExitAnnounced | boolean | No | Whether to announce when participants enter or exit. |

## Example Request

```bash
curl -X PATCH \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings/meeting-001" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}" \
  -d '{
    "subject": "Sprint Planning - Updated",
    "endDateTime": "2025-01-22T10:30:00Z"
  }'
```

## Example Response

```json
{
  "id": "meeting-001",
  "subject": "Sprint Planning - Updated",
  "startDateTime": "2025-01-22T09:00:00Z",
  "endDateTime": "2025-01-22T10:30:00Z",
  "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%3Ameeting_abc123",
  "allowedPresenters": "organization",
  "isEntryExitAnnounced": true
}
```

## Instructions

1. Obtain a valid access token with the `OnlineMeetings.ReadWrite` scope.
2. Identify the online meeting to update by its `meeting-id`.
3. Construct the request body with only the properties you want to update.
4. Send the PATCH request to the onlineMeetings endpoint.
5. A 200 OK response indicates the meeting was successfully updated.
6. The response body contains the full updated meeting object.
