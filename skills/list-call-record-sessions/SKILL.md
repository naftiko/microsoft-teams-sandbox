# List Call Record Sessions

Retrieve the sessions associated with a specific call record from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /communications/callRecords/{callRecord-id}/sessions
- **Operation ID**: listCallRecordSessions
- **Tag**: CallRecords

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/callRecords/{callRecord-id}/sessions`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `CallRecords.Read.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| callRecord-id | string | Yes | The unique identifier of the call record. |

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $expand | string | No | OData expand expression to include related entities such as segments. |

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/callRecords/callrecord-001/sessions?$expand=segments" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "session-001",
      "startDateTime": "2025-01-20T14:00:00Z",
      "endDateTime": "2025-01-20T14:30:00Z",
      "modalities": [
        "audio"
      ]
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `CallRecords.Read.All` scope.
2. Identify the call record by its `callRecord-id`.
3. Optionally use the `$expand` query parameter to include related entities such as segments.
4. Send the GET request to the sessions endpoint.
5. The response contains a `value` array of session objects with details such as start and end times and modalities.
