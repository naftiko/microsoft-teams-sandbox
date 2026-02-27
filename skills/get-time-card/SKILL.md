# Get Time Card

Retrieves the details of a specific time card by its unique identifier within a team's schedule. Returns the time card resource with clock-in and clock-out event details.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams/{team-id}/schedule/timeCards/{timeCard-id}`
- **Operation ID**: `getTimeCard`
- **Tag**: Shifts
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/timeCards/{timeCard-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `timeCard-id` | path | string | Yes | The unique identifier of the time card |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timeCards/timecard-001" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "id": "timecard-001",
  "userId": "user-001",
  "state": "clockedIn",
  "clockInEvent": {
    "dateTime": "2025-01-22T08:00:00Z",
    "atApprovedLocation": true
  },
  "createdDateTime": "2025-01-22T08:00:00Z",
  "lastModifiedDateTime": "2025-01-22T08:00:00Z"
}
```

## Instructions

When the user wants to retrieve details about a specific time card in a team's schedule, use this operation. Provide both the team ID and time card ID as path parameters. The response includes the time card's state, clock-in event details, and timestamps.
