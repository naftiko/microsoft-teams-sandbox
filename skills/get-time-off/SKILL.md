# Get Time Off Entry

Retrieves the details of a specific time off entry by its unique identifier within a team's schedule. Returns the time off resource with its shared time off details.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams/{team-id}/schedule/timesOff/{timeOff-id}`
- **Operation ID**: `getTimeOff`
- **Tag**: TimeOff
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/timesOff/{timeOff-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `timeOff-id` | path | string | Yes | The unique identifier of the time off entry |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timesOff/timeoff-001" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "id": "timeoff-001",
  "userId": "user-001",
  "createdDateTime": "2025-01-10T10:00:00Z",
  "lastModifiedDateTime": "2025-01-10T10:00:00Z",
  "sharedTimeOff": {
    "timeOffReasonId": "reason-001",
    "startDateTime": "2025-02-01T00:00:00Z",
    "endDateTime": "2025-02-03T00:00:00Z",
    "theme": "pink"
  }
}
```

## Instructions

When the user wants to retrieve details about a specific time off entry in a team's schedule, use this operation. Provide both the team ID and time off ID as path parameters. The response includes the assigned user, time off reason, date range, and timestamps.
