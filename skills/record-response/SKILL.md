# Record Call Response

Record a response from a participant during a call in Microsoft Teams communications.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /communications/calls/{call-id}/recordResponse
- **Operation ID**: recordResponse
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
| prompts | array | No | The list of prompts to play before recording |
| bargeInAllowed | boolean | No | Whether the user can interrupt the prompt to begin recording |
| initialSilenceTimeoutInSeconds | integer | No | Maximum initial silence before the recording times out |
| maxSilenceTimeoutInSeconds | integer | No | Maximum silence allowed after speech before the recording stops |
| maxRecordDurationInSeconds | integer | No | Maximum duration of the recording in seconds |
| stopTones | array | No | DTMF tones that will stop the recording (e.g., "#", "1") |
| clientContext | string | No | A unique client context string for correlating the request |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls/{call-id}/recordResponse" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "prompts": [
      {
        "@odata.type": "#microsoft.graph.mediaPrompt",
        "mediaInfo": {
          "uri": "https://storage.example.com/audio/please-record.wav",
          "resourceId": "audio-002"
        }
      }
    ],
    "bargeInAllowed": true,
    "initialSilenceTimeoutInSeconds": 5,
    "maxSilenceTimeoutInSeconds": 3,
    "maxRecordDurationInSeconds": 60,
    "stopTones": ["#"],
    "clientContext": "ctx-003"
  }'
```

## Example Response

```json
{
  "id": "op-record-001",
  "status": "completed",
  "recordingLocation": "https://storage.example.com/recordings/rec-001.wav",
  "clientContext": "ctx-003"
}
```

**Status Code**: 202 Accepted

## Instructions

1. Obtain a valid access token with the `Calls.Initiate.All` scope.
2. Identify the call ID for the call where you want to record a response.
3. Optionally include `prompts` to play an audio prompt before recording begins.
4. Set `bargeInAllowed` to `true` if the caller should be able to interrupt the prompt to start recording.
5. Configure timeout parameters: `initialSilenceTimeoutInSeconds` for how long to wait for speech, `maxSilenceTimeoutInSeconds` for silence after speech, and `maxRecordDurationInSeconds` for the overall recording limit.
6. Specify `stopTones` to define DTMF tones that will end the recording.
7. Optionally include a `clientContext` string for correlating the request with callback notifications.
8. Send a POST request to the `/communications/calls/{call-id}/recordResponse` endpoint.
9. A successful request returns a 202 status code with an operation object including the recording location.
