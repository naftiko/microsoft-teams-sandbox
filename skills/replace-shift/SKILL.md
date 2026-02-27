# Replace Shift

Replaces an existing shift in a team's schedule with the provided shift data. The entire shift resource is replaced with the request body content.

## API Details

- **API**: Microsoft Teams API
- **Method**: PUT
- **Path**: `/teams/{team-id}/schedule/shifts/{shift-id}`
- **Operation ID**: `replaceShift`
- **Tag**: Shifts
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/shifts/{shift-id}`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Schedule.ReadWrite.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `shift-id` | path | string | Yes | The unique identifier of the shift |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `userId` | string | No | The ID of the user assigned to the shift |
| `schedulingGroupId` | string | No | The ID of the scheduling group |
| `sharedShift` | object | No | The shared shift details |

```json
{
  "userId": "user-001",
  "schedulingGroupId": "group-001",
  "sharedShift": {
    "displayName": "Morning Shift",
    "startDateTime": "2025-01-22T08:00:00Z",
    "endDateTime": "2025-01-22T16:00:00Z",
    "theme": "blue",
    "notes": "Regular morning shift"
  }
}
```

## Example Request

```bash
curl -s -X PUT \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/shifts/shift-001" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "userId": "user-001",
    "schedulingGroupId": "group-001",
    "sharedShift": {
      "displayName": "Morning Shift",
      "startDateTime": "2025-01-22T08:00:00Z",
      "endDateTime": "2025-01-22T16:00:00Z",
      "theme": "blue",
      "notes": "Regular morning shift"
    }
  }'
```

## Example Response

```json
{
  "id": "shift-001",
  "userId": "user-001",
  "schedulingGroupId": "group-001",
  "createdDateTime": "2025-01-15T08:00:00Z",
  "lastModifiedDateTime": "2025-01-15T08:00:00Z",
  "sharedShift": {
    "displayName": "Morning Shift",
    "startDateTime": "2025-01-22T08:00:00Z",
    "endDateTime": "2025-01-22T16:00:00Z",
    "theme": "blue",
    "notes": "Regular morning shift"
  }
}
```

## Instructions

When the user wants to replace or fully update an existing shift in a team's schedule, use this operation. Provide both the team ID and shift ID as path parameters, along with the complete shift data in the request body. This replaces the entire shift resource.
