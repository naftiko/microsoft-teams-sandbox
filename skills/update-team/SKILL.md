# Update Team

Updates the properties of a specific team. Only the properties included in the request body are updated.

## API Details

- **API**: Microsoft Teams API
- **Method**: PATCH
- **Path**: `/teams/{team-id}`
- **Operation ID**: `updateTeam`
- **Tag**: Teams
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Team.ReadBasic.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `displayName` | string | No | The updated display name of the team |
| `description` | string | No | The updated description of the team |
| `visibility` | string | No | The updated visibility (`private` or `public`) |
| `isArchived` | boolean | No | Whether the team is archived |

```json
{
  "displayName": "Engineering Team - Updated",
  "description": "Updated description for the engineering team"
}
```

## Example Request

```bash
curl -s -X PATCH \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "Engineering Team - Updated",
    "description": "Updated description for the engineering team"
  }'
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to update or modify an existing team's properties such as its name, description, visibility, or archive status, use this operation. Only include the fields that need to be changed in the request body.
