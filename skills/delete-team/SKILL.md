# Delete Team

Deletes a specific team and its associated resources. This action is permanent and cannot be undone.

## API Details

- **API**: Microsoft Teams API
- **Method**: DELETE
- **Path**: `/teams/{team-id}`
- **Operation ID**: `deleteTeam`
- **Tag**: Teams
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team to delete |

## Example Request

```bash
curl -s -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to delete or remove a team from Microsoft Teams, use this operation. Provide the team ID as a path parameter. This action permanently deletes the team and all its associated data including channels, messages, and files.
