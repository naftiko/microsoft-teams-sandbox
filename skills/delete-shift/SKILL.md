# Delete Shift

Deletes a specific shift from a team's schedule. This action is permanent and cannot be undone.

## API Details

- **API**: Microsoft Teams API
- **Method**: DELETE
- **Path**: `/teams/{team-id}/schedule/shifts/{shift-id}`
- **Operation ID**: `deleteShift`
- **Tag**: Shifts
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/shifts/{shift-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `shift-id` | path | string | Yes | The unique identifier of the shift to delete |

## Example Request

```bash
curl -s -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/shifts/shift-001" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to delete or remove a shift from a team's schedule, use this operation. Provide both the team ID and shift ID as path parameters. This action permanently removes the shift from the schedule.
