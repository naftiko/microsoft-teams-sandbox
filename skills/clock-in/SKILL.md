# Clock In

Records a clock-in event for a specific time card in a team's schedule. Updates the time card with the clock-in timestamp and location approval status.

## API Details

- **API**: Microsoft Teams API
- **Method**: POST
- **Path**: `/teams/{team-id}/schedule/timeCards/{timeCard-id}/clockIn`
- **Operation ID**: `clockIn`
- **Tag**: Shifts
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/timeCards/{timeCard-id}/clockIn`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `timeCard-id` | path | string | Yes | The unique identifier of the time card |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `atApprovedLocation` | boolean | No | Whether the clock-in is at an approved location |
| `notes` | object | No | Notes for the clock-in event (ItemBody object with content and contentType) |

```json
{
  "atApprovedLocation": true,
  "notes": {
    "content": "Starting morning shift",
    "contentType": "text"
  }
}
```

## Example Request

```bash
curl -s -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timeCards/timecard-001/clockIn" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "atApprovedLocation": true,
    "notes": {
      "content": "Starting morning shift",
      "contentType": "text"
    }
  }'
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

When the user wants to clock in or record a clock-in event for a time card, use this operation. Provide the team ID and time card ID as path parameters, along with the optional location approval status and notes in the request body. The response returns the updated time card with the clock-in event details.
