# List Groups

Lists all Microsoft 365 groups in the organization. Returns a paginated collection of group resources including unified groups that can be associated with Microsoft Teams.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/groups`
- **Operation ID**: `listGroups`
- **Tag**: Groups
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Group.Read.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `$top` | query | integer | No | Number of groups to return per page |
| `$skip` | query | integer | No | Number of groups to skip |
| `$filter` | query | string | No | OData filter expression |
| `$select` | query | string | No | Comma-separated list of properties to include |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/groups?%24top=10" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
      "displayName": "Project Alpha Group",
      "mailEnabled": true,
      "mailNickname": "projectalpha",
      "securityEnabled": false,
      "groupTypes": [
        "Unified"
      ],
      "visibility": "Private"
    }
  ]
}
```

## Instructions

When the user wants to list, browse, or search for Microsoft 365 groups in their organization, use this operation. Supports pagination with `$top` and `$skip`, filtering with `$filter`, and selecting specific properties with `$select`.
