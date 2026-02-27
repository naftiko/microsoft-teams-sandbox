# Delete Team Tag

Delete a specific tag from a team in Microsoft Teams.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: DELETE /teams/{team-id}/tags/{tag-id}
- **Operation ID**: deleteTeamworkTag
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

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/tags/{tag-id}" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json"
```

## Example Response

No content body is returned.

**Status Code**: 204 No Content

## Instructions

1. Obtain a valid access token with the `TeamworkTag.ReadWrite` scope.
2. Identify the team ID and tag ID for the tag you want to delete.
3. Send a DELETE request to the `/teams/{team-id}/tags/{tag-id}` endpoint.
4. A successful request returns a 204 status code with no response body.
5. The tag and all its member associations will be permanently removed.
