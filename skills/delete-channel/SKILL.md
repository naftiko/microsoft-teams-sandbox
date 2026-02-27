# Delete Channel

Deletes a specific channel from a team. This action is permanent and cannot be undone. The General channel of a team cannot be deleted.

## API Details

- **API**: Microsoft Teams API
- **Method**: DELETE
- **Path**: `/teams/{team-id}/channels/{channel-id}`
- **Operation ID**: `deleteChannel`
- **Tag**: Channels
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `channel-id` | path | string | Yes | The unique identifier of the channel to delete |

## Example Request

```bash
curl -s -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/channels/19:channel456@thread.tacv2" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to delete or remove a channel from a team, use this operation. Provide both the team ID and channel ID as path parameters. This action permanently deletes the channel and all its associated messages and files. Note that the General channel cannot be deleted.
