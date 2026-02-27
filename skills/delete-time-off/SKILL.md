# Delete Time Off Entry

Deletes a specific time off entry from a team's schedule. This action is permanent and cannot be undone.

## API Details

- **API**: Microsoft Teams API
- **Method**: DELETE
- **Path**: `/teams/{team-id}/schedule/timesOff/{timeOff-id}`
- **Operation ID**: `deleteTimeOff`
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
| `timeOff-id` | path | string | Yes | The unique identifier of the time off entry to delete |

## Example Request

```bash
curl -s -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timesOff/timeoff-001" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to delete or remove a time off entry from a team's schedule, use this operation. Provide both the team ID and time off ID as path parameters. This action permanently removes the time off entry from the schedule.
