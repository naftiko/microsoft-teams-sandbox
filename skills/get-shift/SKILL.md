# Get Shift

Retrieves the details of a specific shift by its unique identifier within a team's schedule. Returns the shift resource with its properties including shared shift details.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams/{team-id}/schedule/shifts/{shift-id}`
- **Operation ID**: `getShift`
- **Tag**: Shifts
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/shifts/{shift-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Schedule.Read.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `shift-id` | path | string | Yes | The unique identifier of the shift |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/shifts/shift-001" \
  -H "Authorization: Bearer {access-token}"
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

When the user wants to retrieve details about a specific shift in a team's schedule, use this operation. Provide both the team ID and shift ID as path parameters. The response includes the shift's assigned user, scheduling group, and shared shift details such as start and end times.
