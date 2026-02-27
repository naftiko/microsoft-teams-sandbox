# List Channels

Lists all channels in a specific team. Returns a paginated collection of channel resources including standard and private channels.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams/{team-id}/channels`
- **Operation ID**: `listChannels`
- **Tag**: Channels
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Channel.ReadBasic.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `$top` | query | integer | No | Number of channels to return per page |
| `$filter` | query | string | No | OData filter expression |
| `$select` | query | string | No | Comma-separated list of properties to include |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/channels" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "@odata.count": 2,
  "value": [
    {
      "id": "19:channel123@thread.tacv2",
      "displayName": "General",
      "description": "General discussion channel",
      "membershipType": "standard"
    },
    {
      "id": "19:channel456@thread.tacv2",
      "displayName": "Development",
      "description": "Dev team channel",
      "membershipType": "private"
    }
  ]
}
```

## Instructions

When the user wants to list, browse, or search for channels within a specific team, use this operation. Provide the team ID as a path parameter. Supports pagination with `$top`, filtering with `$filter`, and selecting specific properties with `$select`.
