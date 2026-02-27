# Create Channel

Creates a new channel in a specific team. Channels can be standard (visible to all team members) or private (visible only to specific members).

## API Details

- **API**: Microsoft Teams API
- **Method**: POST
- **Path**: `/teams/{team-id}/channels`
- **Operation ID**: `createChannel`
- **Tag**: Channels
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/channels`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Channel.Create`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `displayName` | string | Yes | The display name of the channel |
| `description` | string | No | A description of the channel |
| `membershipType` | string | No | The membership type (`standard`, `private`, or `shared`) |

```json
{
  "displayName": "General",
  "description": "General discussion channel",
  "membershipType": "standard"
}
```

## Example Request

```bash
curl -s -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/channels" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "General",
    "description": "General discussion channel",
    "membershipType": "standard"
  }'
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

When the user wants to create a new channel in a team, use this operation. Provide the team ID as a path parameter and the channel details in the request body. Specify the membershipType as `standard` for channels visible to all team members or `private` for restricted-access channels.
