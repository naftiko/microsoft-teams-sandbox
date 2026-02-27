# Play Prompt in Call

Play an audio prompt to participants in an existing call in Microsoft Teams communications.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /communications/calls/{call-id}/playPrompt
- **Operation ID**: playPrompt
- **Tag**: CallIvr

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
| prompts | array | Yes | The list of MediaPrompt objects to play |
| clientContext | string | No | A unique client context string for correlating the request |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls/{call-id}/playPrompt" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "prompts": [
      {
        "@odata.type": "#microsoft.graph.mediaPrompt",
        "mediaInfo": {
          "uri": "https://storage.example.com/audio/welcome.wav",
          "resourceId": "audio-001"
        }
      }
    ],
    "clientContext": "ctx-002"
  }'
```

## Example Response

```json
{
  "id": "op-prompt-001",
  "status": "completed",
  "clientContext": "ctx-002"
}
```

**Status Code**: 202 Accepted

## Instructions

1. Obtain a valid access token with the `Calls.Initiate.All` scope.
2. Identify the call ID for the call where you want to play a prompt.
3. Construct the `prompts` array with MediaPrompt objects containing the media URI and resource ID.
4. Optionally include a `clientContext` string for correlating the request with callback notifications.
5. Send a POST request to the `/communications/calls/{call-id}/playPrompt` endpoint.
6. A successful request returns a 202 status code with an operation object indicating the prompt playback status.
