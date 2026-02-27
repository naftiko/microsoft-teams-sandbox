# Get Team Tag

Retrieve a specific tag from a team in Microsoft Teams.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teams/{team-id}/tags/{tag-id}
- **Operation ID**: getTeamworkTag
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
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/tags/{tag-id}" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json"
```

## Example Response

```json
{
  "id": "tag-001",
  "displayName": "Frontend Developers",
  "description": "All frontend team members",
  "memberCount": 5,
  "tagType": "standard"
}
```

## Instructions

1. Obtain a valid access token with the `TeamworkTag.Read` scope.
2. Identify the team ID and tag ID for the tag you want to retrieve.
3. Send a GET request to the `/teams/{team-id}/tags/{tag-id}` endpoint.
4. The response contains the tag details including display name, description, member count, and tag type.
