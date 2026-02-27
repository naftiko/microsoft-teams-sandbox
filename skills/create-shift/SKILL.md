# Create Shift

Create a new shift in a specific team's schedule using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /teams/{team-id}/schedule/shifts
- **Operation ID**: createShift
- **Tag**: Shifts

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/shifts`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Schedule.ReadWrite.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team. |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| userId | string | No | The ID of the user assigned to the shift. |
| schedulingGroupId | string | No | The ID of the scheduling group the shift belongs to. |
| sharedShift | object | Yes | The shared shift details including display name, start and end times, theme, and notes. |

## Example Request

```bash
curl -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/team-001/schedule/shifts" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}" \
  -d '{
    "userId": "user-001",
    "schedulingGroupId": "group-001",
    "sharedShift": {
      "displayName": "Morning Shift",
      "startDateTime": "2025-01-22T08:00:00Z",
      "endDateTime": "2025-01-22T16:00:00Z",
      "theme": "blue",
      "notes": "Regular morning shift"
    }
  }'
```

## Example Response

```json
{
  "id": "shift-001",
  "userId": "user-001",
  "schedulingGroupId": "group-001",
  "createdDateTime": "2025-01-15T08:00:00Z",
  "lastModifiedDateTime": "2025-01-15T08:00:00Z",
  "sharedShift": {
    "displayName": "Morning Shift",
    "startDateTime": "2025-01-22T08:00:00Z",
    "endDateTime": "2025-01-22T16:00:00Z",
    "theme": "blue",
    "notes": "Regular morning shift"
  }
}
```

## Instructions

1. Obtain a valid access token with the `Schedule.ReadWrite.All` scope.
2. Identify the team by its `team-id`.
3. Construct the request body with the shift details including the assigned user, scheduling group, and shared shift information.
4. The `sharedShift` object should include at minimum the display name, start and end date times.
5. Optionally include a theme color and notes for the shift.
6. Send the POST request to the shifts endpoint.
7. A 201 Created response indicates the shift was successfully created.
8. The response body contains the created shift object with its assigned id and timestamps.
