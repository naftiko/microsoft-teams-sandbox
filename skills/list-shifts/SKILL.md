# List Shifts

Retrieve a list of shifts for a specific team's schedule from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /teams/{team-id}/schedule/shifts
- **Operation ID**: listShifts
- **Tag**: Shifts

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/shifts`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `Schedule.Read.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| team-id | string | Yes | The unique identifier of the team. |

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $top | integer | No | The number of results to return per page. |
| $filter | string | No | OData filter expression to filter shifts. |

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/team-001/schedule/shifts?$top=10" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "shift-001",
      "userId": "user-001",
      "sharedShift": {
        "displayName": "Morning Shift",
        "startDateTime": "2025-01-22T08:00:00Z",
        "endDateTime": "2025-01-22T16:00:00Z",
        "theme": "blue"
      }
    },
    {
      "id": "shift-002",
      "userId": "user-002",
      "sharedShift": {
        "displayName": "Evening Shift",
        "startDateTime": "2025-01-22T16:00:00Z",
        "endDateTime": "2025-01-23T00:00:00Z",
        "theme": "purple"
      }
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `Schedule.Read.All` scope.
2. Identify the team by its `team-id`.
3. Optionally specify query parameters to filter or paginate the results.
4. Send the GET request to the shifts endpoint.
5. The response contains a `value` array of shift objects.
6. Each shift includes its id, assigned user id, and shared shift details such as display name, start and end times, and theme color.
