# Create or Replace Schedule

Create or replace the schedule for a specific team using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: PUT /teams/{team-id}/schedule
- **Operation ID**: createOrReplaceSchedule
- **Tag**: Schedules

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule`

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
| enabled | boolean | No | Whether the schedule is enabled. |
| timeZone | string | No | The time zone for the schedule (e.g., America/New_York). |
| timeClockEnabled | boolean | No | Whether the time clock feature is enabled. |
| openShiftsEnabled | boolean | No | Whether open shifts are enabled. |
| swapShiftsRequestsEnabled | boolean | No | Whether swap shift requests are enabled. |
| offerShiftRequestsEnabled | boolean | No | Whether offer shift requests are enabled. |
| timeOffRequestsEnabled | boolean | No | Whether time off requests are enabled. |

## Example Request

```bash
curl -X PUT \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/team-001/schedule" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}" \
  -d '{
    "enabled": true,
    "timeZone": "America/New_York",
    "timeClockEnabled": true,
    "openShiftsEnabled": true,
    "swapShiftsRequestsEnabled": true,
    "offerShiftRequestsEnabled": true,
    "timeOffRequestsEnabled": true
  }'
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

1. Obtain a valid access token with the `Schedule.ReadWrite.All` scope.
2. Identify the team by its `team-id`.
3. Construct the request body with the schedule configuration including timezone and feature flags.
4. Send the PUT request to the schedule endpoint.
5. A 200 OK response indicates the schedule was successfully created or replaced.
6. The response body contains the full schedule object including the provision status.
7. Note that this operation replaces the entire schedule configuration, so include all desired settings in the request body.
