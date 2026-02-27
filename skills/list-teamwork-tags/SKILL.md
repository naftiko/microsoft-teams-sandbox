# List Team Tags

List all tags associated with a specific team in Microsoft Teams.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teams/{team-id}/tags
- **Operation ID**: listTeamworkTags
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

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/tags" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json"
```

## Example Response

```json
{
  "value": [
    {
      "id": "tag-001",
      "displayName": "Frontend Developers",
      "description": "All frontend team members",
      "memberCount": 5,
      "tagType": "standard"
    },
    {
      "id": "tag-002",
      "displayName": "Backend Developers",
      "description": "All backend team members",
      "memberCount": 8,
      "tagType": "standard"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `TeamworkTag.Read` scope.
2. Identify the team ID for the team whose tags you want to list.
3. Send a GET request to the `/teams/{team-id}/tags` endpoint.
4. Parse the `value` array in the response to access individual tag objects.
5. Each tag includes its display name, description, member count, and tag type.
