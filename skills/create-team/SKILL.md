# Create Team

Creates a new team in Microsoft Teams. The operation is asynchronous and returns a 202 Accepted response with a Location header that can be used to check the status of the team creation.

## API Details

- **API**: Microsoft Teams API
- **Method**: POST
- **Path**: `/teams`
- **Operation ID**: `createTeam`
- **Tag**: Teams
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Team.Create`

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `displayName` | string | Yes | The display name of the team |
| `description` | string | No | A description of the team |
| `visibility` | string | No | The visibility of the team (`private` or `public`) |
| `members` | array | No | List of members to add to the team |
| `channels` | array | No | List of channels to create in the team |

```json
{
  "displayName": "New Project Team",
  "description": "Team for the new project initiative",
  "visibility": "private"
}
```

## Example Request

```bash
curl -s -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "New Project Team",
    "description": "Team for the new project initiative",
    "visibility": "private"
  }'
```

## Example Response

The response is `202 Accepted` with a `Location` header pointing to the team creation status.

**Status Code**: 202

**Headers**:
```
Location: /teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/operations/abc123
```

## Instructions

When the user wants to create a new team in Microsoft Teams, use this operation. Provide the team display name, optional description, and visibility setting. The operation is asynchronous, so the response includes a Location header to track the creation progress.
