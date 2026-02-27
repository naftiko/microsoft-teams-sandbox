# Create Team Tag

Create a new tag for a specific team in Microsoft Teams.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /teams/{team-id}/tags
- **Operation ID**: createTeamworkTag
- **Tag**: Tags

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `TeamworkTag.ReadWrite`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| displayName | string | Yes | The display name of the tag |
| description | string | No | A description of the tag |
| members | array | No | List of members to add to the tag |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/tags" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "Frontend Developers",
    "description": "All frontend team members"
  }'
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

**Status Code**: 201 Created

## Instructions

1. Obtain a valid access token with the `TeamworkTag.ReadWrite` scope.
2. Identify the team ID for the team where you want to create a tag.
3. Construct the request body with at minimum the `displayName` field.
4. Optionally include a `description` and initial `members` array.
5. Send a POST request to the `/teams/{team-id}/tags` endpoint.
6. A successful request returns a 201 status code with the created tag object.
