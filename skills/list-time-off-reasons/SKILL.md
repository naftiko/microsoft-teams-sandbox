# List Time Off Reasons

Lists all time off reasons configured for a team's schedule. Returns a collection of time off reason resources with their display names and icon types.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams/{team-id}/schedule/timeOffReasons`
- **Operation ID**: `listTimeOffReasons`
- **Tag**: TimeOff
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/timeOffReasons`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timeOffReasons" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "reason-001",
      "displayName": "Vacation",
      "iconType": "plane",
      "isActive": true
    },
    {
      "id": "reason-002",
      "displayName": "Sick Leave",
      "iconType": "firstAid",
      "isActive": true
    }
  ]
}
```

## Instructions

When the user wants to list or browse the available time off reasons for a team's schedule, use this operation. Provide the team ID as a path parameter. The response includes each reason's display name, icon type, and active status, which can be used when creating time off entries.
