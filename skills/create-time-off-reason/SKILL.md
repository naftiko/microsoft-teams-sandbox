# Create Time Off Reason

Creates a new time off reason for a team's schedule. Time off reasons define the categories of time off available to team members.

## API Details

- **API**: Microsoft Teams API
- **Method**: POST
- **Path**: `/teams/{team-id}/schedule/timeOffReasons`
- **Operation ID**: `createTimeOffReason`
- **Tag**: TimeOff
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/timeOffReasons`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `displayName` | string | Yes | The display name of the time off reason |
| `iconType` | string | No | The icon type for the reason (e.g., plane, firstAid, car) |
| `isActive` | boolean | No | Whether the time off reason is active |

```json
{
  "displayName": "Vacation",
  "iconType": "plane",
  "isActive": true
}
```

## Example Request

```bash
curl -s -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timeOffReasons" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "Vacation",
    "iconType": "plane",
    "isActive": true
  }'
```

## Example Response

```json
{
  "id": "reason-001",
  "displayName": "Vacation",
  "iconType": "plane",
  "isActive": true,
  "createdDateTime": "2025-01-01T00:00:00Z",
  "lastModifiedDateTime": "2025-01-01T00:00:00Z"
}
```

## Instructions

When the user wants to create a new time off reason for a team's schedule, use this operation. Provide the team ID as a path parameter and include the display name, icon type, and active status in the request body. The response returns the created time off reason with a 201 status code.
