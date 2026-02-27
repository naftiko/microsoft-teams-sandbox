# Update Channel

Updates the properties of a specific channel within a team. Only the properties included in the request body are updated.

## API Details

- **API**: Microsoft Teams API
- **Method**: PATCH
- **Path**: `/teams/{team-id}/channels/{channel-id}`
- **Operation ID**: `updateChannel`
- **Tag**: Channels
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `channel-id` | path | string | Yes | The unique identifier of the channel |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `displayName` | string | No | The updated display name of the channel |
| `description` | string | No | The updated description of the channel |

```json
{
  "displayName": "General - Updated",
  "description": "Updated general discussion channel"
}
```

## Example Request

```bash
curl -s -X PATCH \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/channels/19:channel123@thread.tacv2" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "General - Updated",
    "description": "Updated general discussion channel"
  }'
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to update or modify an existing channel's properties such as its name or description, use this operation. Provide both the team ID and channel ID as path parameters. Only include the fields that need to be changed in the request body.
