# Create Time Off Entry

Creates a new time off entry in a team's schedule. Associates the time off with a user, reason, and date range.

## API Details

- **API**: Microsoft Teams API
- **Method**: POST
- **Path**: `/teams/{team-id}/schedule/timesOff`
- **Operation ID**: `createTimeOff`
- **Tag**: TimeOff
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/timesOff`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Schedule.ReadWrite.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `userId` | string | Yes | The ID of the user taking time off |
| `sharedTimeOff` | object | Yes | The shared time off details |

```json
{
  "userId": "user-001",
  "sharedTimeOff": {
    "timeOffReasonId": "reason-001",
    "startDateTime": "2025-02-01T00:00:00Z",
    "endDateTime": "2025-02-03T00:00:00Z",
    "theme": "pink"
  }
}
```

## Example Request

```bash
curl -s -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timesOff" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "userId": "user-001",
    "sharedTimeOff": {
      "timeOffReasonId": "reason-001",
      "startDateTime": "2025-02-01T00:00:00Z",
      "endDateTime": "2025-02-03T00:00:00Z",
      "theme": "pink"
    }
  }'
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

When the user wants to create a new time off entry in a team's schedule, use this operation. Provide the team ID as a path parameter and include the user ID, time off reason, and date range in the request body. The response returns the created time off entry with a 201 status code.
