# Answer Call

Answer an incoming call in Microsoft Teams communications.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /communications/calls/{call-id}/answer
- **Operation ID**: answerCall
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
| callbackUri | string | Yes | The callback URL for call state notifications |
| acceptedModalities | array | Yes | The accepted modalities (audio, video, videoBasedScreenSharing) |
| mediaConfig | object | No | The media configuration for the call |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls/{call-id}/answer" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "callbackUri": "https://bot.example.com/api/calls",
    "acceptedModalities": ["audio"],
    "mediaConfig": {
      "@odata.type": "#microsoft.graph.appHostedMediaConfig",
      "blob": "<Media Session Configuration>"
    }
  }'
```

## Example Response

No content body is returned.

**Status Code**: 202 Accepted

## Instructions

1. Obtain a valid access token with the `Calls.Initiate.All` scope.
2. Identify the call ID for the incoming call you want to answer.
3. Construct the request body with the `callbackUri` and `acceptedModalities`.
4. Optionally include `mediaConfig` to configure the media session.
5. The `acceptedModalities` array can include `audio`, `video`, or `videoBasedScreenSharing`.
6. Send a POST request to the `/communications/calls/{call-id}/answer` endpoint.
7. A successful request returns a 202 status code indicating the answer operation has been accepted.
