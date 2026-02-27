# List Time Off Entries

Lists all time off entries in a team's schedule. Returns a paginated collection of time off resources with their shared time off details.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/teams/{team-id}/schedule/timesOff`
- **Operation ID**: `listTimesOff`
- **Tag**: TimeOff
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/{team-id}/schedule/timesOff`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `Schedule.Read.All`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `team-id` | path | string | Yes | The unique identifier of the team |
| `$top` | query | integer | No | Number of time off entries to return per page |
| `$filter` | query | string | No | OData filter expression |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teams/e1b3c5a7-9d2f-4b6e-8c1a-3f5d7e9b2a4c/schedule/timesOff?%24top=10" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "timeoff-001",
      "userId": "user-001",
      "sharedTimeOff": {
        "timeOffReasonId": "reason-001",
        "startDateTime": "2025-02-01T00:00:00Z",
        "endDateTime": "2025-02-03T00:00:00Z"
      }
    }
  ]
}
```

## Instructions

When the user wants to list or browse time off entries for a team's schedule, use this operation. Provide the team ID as a path parameter. Use `$top` to control pagination and `$filter` to narrow results by specific criteria such as user or date range.
