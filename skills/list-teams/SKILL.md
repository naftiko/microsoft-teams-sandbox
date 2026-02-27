# List All Teams

Lists all teams in the organization that the authenticated user has access to. Returns a paginated collection of team resources with basic properties.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams`
- **Operation ID**: `listTeams`
- **Tag**: Teams
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Team.ReadBasic.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `$top` | query | integer | No | Number of teams to return per page |
| `$skip` | query | integer | No | Number of teams to skip |
| `$filter` | query | string | No | OData filter expression |
| `$select` | query | string | No | Comma-separated list of properties to include |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams?%24top=10" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "@odata.count": 2,
  "value": [
    {
      "id": "e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c",
      "displayName": "Engineering Team",
      "description": "Main engineering team",
      "isArchived": false,
      "visibility": "private"
    },
    {
      "id": "f2c4d6b8-0e3a-5c7f-9d2b-4a6e8c1f3d5a",
      "displayName": "Marketing Team",
      "description": "Marketing and communications",
      "isArchived": false,
      "visibility": "public"
    }
  ]
}
```

## Instructions

When the user wants to list, browse, or search for teams in their organization, use this operation. Supports pagination with `$top` and `$skip`, filtering with `$filter`, and selecting specific properties with `$select`.
