# Update Group

Updates the properties of a specific Microsoft 365 group. Only the properties included in the request body are updated.

## API Details

- **API**: Microsoft Teams API
- **Method**: PATCH
- **Path**: `/groups/{group-id}`
- **Operation ID**: `updateGroup`
- **Tag**: Groups
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups/{group-id}`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Group.ReadWrite.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `group-id` | path | string | Yes | The unique identifier of the group |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `displayName` | string | No | The updated display name of the group |
| `description` | string | No | The updated description of the group |
| `visibility` | string | No | The updated visibility (`Private` or `Public`) |
| `mailNickname` | string | No | The updated mail alias for the group |

```json
{
  "displayName": "Project Alpha Group - Updated",
  "description": "Updated description for Project Alpha"
}
```

## Example Request

```bash
curl -s -X PATCH \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups/a1b2c3d4-e5f6-7890-abcd-ef1234567890" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "Project Alpha Group - Updated",
    "description": "Updated description for Project Alpha"
  }'
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to update or modify an existing Microsoft 365 group's properties such as its name, description, or visibility, use this operation. Only include the fields that need to be changed in the request body.
