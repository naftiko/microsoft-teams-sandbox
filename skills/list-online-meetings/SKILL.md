# List Online Meetings

Retrieve a list of online meetings for the authenticated user from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /me/onlineMeetings
- **Operation ID**: listOnlineMeetings
- **Tag**: OnlineMeetings

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `OnlineMeetings.Read`

## Parameters

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $top | integer | No | The number of results to return per page. |
| $filter | string | No | OData filter expression to filter online meetings. |

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/me/onlineMeetings?$top=10" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "meeting-001",
      "subject": "Sprint Planning",
      "startDateTime": "2025-01-22T09:00:00Z",
      "endDateTime": "2025-01-22T10:00:00Z",
      "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%3Ameeting_abc123"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `OnlineMeetings.Read` scope.
2. Optionally specify query parameters to filter or paginate the results.
3. Send the GET request to the onlineMeetings endpoint.
4. The response contains a `value` array of online meeting objects with details such as subject, times, and join URL.
