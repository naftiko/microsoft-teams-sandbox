# Replace Time Off Entry

Replaces an existing time off entry in a team's schedule with the provided data. The entire time off resource is replaced with the request body content.

## API Details

- **API**: Microsoft Teams API
- **Method**: PUT
- **Path**: `/teams/{team-id}/schedule/timesOff/{timeOff-id}`
- **Operation ID**: `replaceTimeOff`
- **Tag**: TimeOff
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/timesOff/{timeOff-id}`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `timeOff-id` | path | string | Yes | The unique identifier of the time off entry |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `userId` | string | No | The ID of the user taking time off |
| `sharedTimeOff` | object | No | The shared time off details |

```json
{
  "userId": "user-001",
  "sharedTimeOff": {
    "timeOffReasonId": "reason-001",
    "startDateTime": "2025-02-01T00:00:00Z",
    "endDateTime": "2025-02-05T00:00:00Z",
    "theme": "pink"
  }
}
```

## Example Request

```bash
curl -s -X PUT \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timesOff/timeoff-001" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "userId": "user-001",
    "sharedTimeOff": {
      "timeOffReasonId": "reason-001",
      "startDateTime": "2025-02-01T00:00:00Z",
      "endDateTime": "2025-02-05T00:00:00Z",
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
  "lastModifiedDateTime": "2025-01-15T10:00:00Z",
  "sharedTimeOff": {
    "timeOffReasonId": "reason-001",
    "startDateTime": "2025-02-01T00:00:00Z",
    "endDateTime": "2025-02-05T00:00:00Z",
    "theme": "pink"
  }
}
```

## Instructions

When the user wants to replace or fully update an existing time off entry in a team's schedule, use this operation. Provide both the team ID and time off ID as path parameters, along with the complete time off data in the request body. This replaces the entire time off resource.
