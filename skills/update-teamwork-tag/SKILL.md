# Update Team Tag

Update the properties of an existing tag in a Microsoft Teams team.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: PATCH /teams/{team-id}/tags/{tag-id}
- **Operation ID**: updateTeamworkTag
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
| tag-id | string | Yes | The unique identifier of the tag |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| displayName | string | No | The updated display name of the tag |
| description | string | No | The updated description of the tag |

## Example Request

```bash
curl -X PATCH "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/tags/{tag-id}" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "Senior Frontend Developers",
    "description": "All senior frontend team members"
  }'
```

## Example Response

```json
{
  "id": "tag-001",
  "displayName": "Senior Frontend Developers",
  "description": "All senior frontend team members",
  "memberCount": 5,
  "tagType": "standard"
}
```

**Status Code**: 200 OK

## Instructions

1. Obtain a valid access token with the `TeamworkTag.ReadWrite` scope.
2. Identify the team ID and tag ID for the tag you want to update.
3. Construct the request body with the fields you want to update.
4. Send a PATCH request to the `/teams/{team-id}/tags/{tag-id}` endpoint.
5. A successful request returns a 200 status code with the updated tag object.
