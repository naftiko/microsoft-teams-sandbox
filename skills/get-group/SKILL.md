# Get Group

Retrieves the details of a specific Microsoft 365 group by its unique identifier. Returns the group resource with its properties.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/groups/{group-id}`
- **Operation ID**: `getGroup`
- **Tag**: Groups
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups/{group-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Group.Read.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `group-id` | path | string | Yes | The unique identifier of the group |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups/a1b2c3d4-e5f6-7890-abcd-ef1234567890" \
  -H "Authorization: Bearer {access-token}"
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

When the user wants to retrieve details about a specific Microsoft 365 group, use this operation. Provide the group ID as a path parameter to get the full group resource with all its properties.
