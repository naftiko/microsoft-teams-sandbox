# List Tag Members

List all members of a specific tag in a Microsoft Teams team.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teams/{team-id}/tags/{tag-id}/members
- **Operation ID**: listTeamworkTagMembers
- **Tag**: Tags

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `TeamworkTag.Read`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |
| tag-id | string | Yes | The unique identifier of the tag |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/tags/{tag-id}/members" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json"
```

## Example Response

```json
{
  "value": [
    {
      "id": "tagmember-001",
      "displayName": "John Doe",
      "userId": "user-001"
    },
    {
      "id": "tagmember-002",
      "displayName": "Jane Smith",
      "userId": "user-002"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `TeamworkTag.Read` scope.
2. Identify the team ID and tag ID for the tag whose members you want to list.
3. Send a GET request to the `/teams/{team-id}/tags/{tag-id}/members` endpoint.
4. Parse the `value` array in the response to access individual tag member objects.
5. Each member includes their display name and user ID.
