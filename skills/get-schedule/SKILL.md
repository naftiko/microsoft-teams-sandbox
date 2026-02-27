# Get Team Schedule

Retrieve the schedule for a specific team from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teams/{team-id}/schedule
- **Operation ID**: getSchedule
- **Tag**: Schedules

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Schedule.Read.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team. |

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/team-001/schedule" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "id": "schedule-001",
  "enabled": true,
  "timeZone": "America/New_York",
  "provisionStatus": "completed",
  "timeClockEnabled": true,
  "openShiftsEnabled": true,
  "swapShiftsRequestsEnabled": true,
  "offerShiftRequestsEnabled": true,
  "timeOffRequestsEnabled": true
}
```

## Instructions

1. Obtain a valid access token with the `Schedule.Read.All` scope.
2. Identify the team by its `team-id`.
3. Send the GET request to the schedule endpoint.
4. The response contains the schedule configuration for the team including timezone, provision status, and feature flags.
5. Feature flags indicate whether time clock, open shifts, swap requests, offer requests, and time off requests are enabled.
