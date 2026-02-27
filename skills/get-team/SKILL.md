# Get Team

Retrieves the details of a specific team by its unique identifier. Returns the team resource with its properties.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams/{team-id}`
- **Operation ID**: `getTeam`
- **Tag**: Teams
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Team.ReadBasic.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `$select` | query | string | No | Comma-separated list of properties to include |
| `$expand` | query | string | No | Comma-separated list of relationships to expand |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "id": "e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c",
  "displayName": "Engineering Team",
  "description": "Main engineering team for product development",
  "internalId": "19:engineering@thread.tacv2",
  "isArchived": false,
  "visibility": "private"
}
```

## Instructions

When the user wants to retrieve details about a specific team, use this operation. Provide the team ID as a path parameter. Use `$select` to return only specific properties and `$expand` to include related resources in the response.
