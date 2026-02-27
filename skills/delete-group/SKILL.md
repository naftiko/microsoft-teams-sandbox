# Delete Group

Deletes a specific Microsoft 365 group and its associated resources. This action is permanent and cannot be undone.

## API Details

- **API**: Microsoft Teams API
- **Method**: DELETE
- **Path**: `/groups/{group-id}`
- **Operation ID**: `deleteGroup`
- **Tag**: Groups
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups/{group-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Group.ReadWrite.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `group-id` | path | string | Yes | The unique identifier of the group to delete |

## Example Request

```bash
curl -s -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups/a1b2c3d4-e5f6-7890-abcd-ef1234567890" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to delete or remove a Microsoft 365 group, use this operation. Provide the group ID as a path parameter. This action permanently deletes the group and all its associated data including conversations, files, and the associated team if one exists.
