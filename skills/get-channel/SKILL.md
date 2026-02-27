# Get Channel

Retrieves the details of a specific channel within a team by its unique identifier. Returns the channel resource with its properties.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams/{team-id}/channels/{channel-id}`
- **Operation ID**: `getChannel`
- **Tag**: Channels
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels/{channel-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Channel.ReadBasic.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `channel-id` | path | string | Yes | The unique identifier of the channel |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/channels/19:channel123@thread.tacv2" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "id": "19:channel123@thread.tacv2",
  "displayName": "General",
  "description": "General discussion channel",
  "membershipType": "standard",
  "createdDateTime": "2025-01-15T10:30:00Z",
  "webUrl": "https://teams.microsoft.com/l/channel/19%3Achannel123%40thread.tacv2/General"
}
```

## Instructions

When the user wants to retrieve details about a specific channel within a team, use this operation. Provide both the team ID and channel ID as path parameters to get the full channel resource with all its properties.
