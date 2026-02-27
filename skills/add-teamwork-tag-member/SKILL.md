# Add Tag Member

Add a new member to a specific tag in a Microsoft Teams team.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /teams/{team-id}/tags/{tag-id}/members
- **Operation ID**: addTeamworkTagMember
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
| userId | string | Yes | The unique identifier of the user to add |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/tags/{tag-id}/members" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "userId": "user-001"
  }'
```

## Example Response

```json
{
  "id": "tagmember-001",
  "displayName": "John Doe",
  "userId": "user-001"
}
```

**Status Code**: 201 Created

## Instructions

1. Obtain a valid access token with the `TeamworkTag.ReadWrite` scope.
2. Identify the team ID and tag ID for the tag you want to add a member to.
3. Construct the request body with the `userId` of the user to add.
4. Send a POST request to the `/teams/{team-id}/tags/{tag-id}/members` endpoint.
5. A successful request returns a 201 status code with the created tag member object.
