# Create Group

Creates a new Microsoft 365 group. The group can be a unified group (Microsoft 365 group) that can later be team-enabled, or a security group.

## API Details

- **API**: Microsoft Teams API
- **Method**: POST
- **Path**: `/groups`
- **Operation ID**: `createGroup`
- **Tag**: Groups
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Group.ReadWrite.All`

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `displayName` | string | Yes | The display name of the group |
| `description` | string | No | A description of the group |
| `mailEnabled` | boolean | Yes | Whether the group is mail-enabled |
| `mailNickname` | string | Yes | The mail alias for the group |
| `securityEnabled` | boolean | Yes | Whether the group is security-enabled |
| `groupTypes` | array | No | Group types (e.g., `["Unified"]` for Microsoft 365 groups) |
| `visibility` | string | No | The visibility of the group (`Private` or `Public`) |

```json
{
  "displayName": "Project Alpha Group",
  "description": "Microsoft 365 group for Project Alpha",
  "mailEnabled": true,
  "mailNickname": "projectalpha",
  "securityEnabled": false,
  "groupTypes": ["Unified"],
  "visibility": "Private"
}
```

## Example Request

```bash
curl -s -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "Project Alpha Group",
    "description": "Microsoft 365 group for Project Alpha",
    "mailEnabled": true,
    "mailNickname": "projectalpha",
    "securityEnabled": false,
    "groupTypes": ["Unified"],
    "visibility": "Private"
  }'
```

## Example Response

```json
{
  "id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  "displayName": "Project Alpha Group",
  "description": "Microsoft 365 group for Project Alpha",
  "mailEnabled": true,
  "mailNickname": "projectalpha",
  "securityEnabled": false,
  "groupTypes": [
    "Unified"
  ],
  "visibility": "Private"
}
```

## Instructions

When the user wants to create a new Microsoft 365 group or security group, use this operation. Provide the required fields including displayName, mailEnabled, mailNickname, and securityEnabled. For Microsoft 365 groups (unified groups), include `"Unified"` in the groupTypes array.
