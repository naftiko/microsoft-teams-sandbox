# Delete Online Meeting

Delete an existing online meeting for the authenticated user using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: DELETE /me/onlineMeetings/{meeting-id}
- **Operation ID**: deleteOnlineMeeting
- **Tag**: OnlineMeetings

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings/{meeting-id}`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `OnlineMeetings.ReadWrite`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| meeting-id | string | Yes | The unique identifier of the online meeting to delete. |

## Example Request

```bash
curl -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings/meeting-001" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```
HTTP/1.1 204 No Content
```

## Instructions

1. Obtain a valid access token with the `OnlineMeetings.ReadWrite` scope.
2. Identify the online meeting to delete by its `meeting-id`.
3. Send the DELETE request to the onlineMeetings endpoint with the meeting identifier.
4. A 204 No Content response indicates the meeting was successfully deleted.
5. No response body is returned for a successful deletion.
