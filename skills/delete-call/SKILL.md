# End Call

End an existing call in Microsoft Teams communications.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: DELETE /communications/calls/{call-id}
- **Operation ID**: deleteCall
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

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/calls/{call-id}" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/json"
```

## Example Response

No content body is returned.

**Status Code**: 204 No Content

## Instructions

1. Obtain a valid access token with the `Calls.Initiate.All` scope.
2. Identify the call ID for the call you want to end.
3. Send a DELETE request to the `/communications/calls/{call-id}` endpoint.
4. A successful request returns a 204 status code with no response body.
5. The call will be terminated for all participants.
