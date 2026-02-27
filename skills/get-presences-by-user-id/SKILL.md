# Get Presences for Multiple Users

Retrieve the presence information for multiple users in a single request from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: POST /communications/getPresencesByUserId
- **Operation ID**: getPresencesByUserId
- **Tag**: Presence

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/getPresencesByUserId`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Presence.Read.All`

## Parameters

### Request Body

| Name | Type | Required | Description |
|------|------|----------|-------------|
| ids | array of strings | Yes | An array of user IDs for which to retrieve presence information. |

## Example Request

```bash
curl -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/getPresencesByUserId" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}" \
  -d '{
    "ids": ["user-001", "user-002"]
  }'
```

## Example Response

```json
{
  "value": [
    {
      "id": "user-001",
      "availability": "Available",
      "activity": "Available"
    },
    {
      "id": "user-002",
      "availability": "Busy",
      "activity": "InACall"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `Presence.Read.All` scope.
2. Construct the request body with an `ids` array containing the user IDs to query.
3. Send the POST request to the getPresencesByUserId endpoint.
4. The response contains a `value` array of presence objects, one for each requested user.
5. Each presence object includes the user's id, availability, and activity status.
6. This is more efficient than making individual presence requests when you need presence for multiple users.
