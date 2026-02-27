# Invite Participants to Call

Invite additional participants to an existing call in Microsoft Teams communications.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /communications/calls/{call-id}/participants/invite
- **Operation ID**: inviteParticipants
- **Tag**: Calls

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/json`

## OAuth Scopes

- `Calls.Initiate.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| call-id | string | Yes | The unique identifier of the call |

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| participants | array | Yes | The list of participants to invite |
| clientContext | string | No | A unique client context string for correlating the request |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls/{call-id}/participants/invite" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "participants": [
      {
        "@odata.type": "#microsoft.graph.invitationParticipantInfo",
        "identity": {
          "user": {
            "id": "user-002",
            "displayName": "Jane Smith"
          }
        }
      }
    ],
    "clientContext": "ctx-001"
  }'
```

## Example Response

```json
{
  "id": "op-invite-001",
  "status": "completed",
  "clientContext": "ctx-001"
}
```

**Status Code**: 202 Accepted

## Instructions

1. Obtain a valid access token with the `Calls.Initiate.All` scope.
2. Identify the call ID for the call you want to invite participants to.
3. Construct the `participants` array with the identity information of each participant to invite.
4. Optionally include a `clientContext` string for correlating the request with callback notifications.
5. Send a POST request to the `/communications/calls/{call-id}/participants/invite` endpoint.
6. A successful request returns a 202 status code with an operation object indicating the invite status.
