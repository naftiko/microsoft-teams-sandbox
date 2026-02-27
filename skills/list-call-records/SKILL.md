# List Call Records

Retrieve a list of call records from the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: GET /communications/callRecords
- **Operation ID**: listCallRecords
- **Tag**: CallRecords

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/callRecords`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `CallRecords.Read.All`

## Parameters

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $top | integer | No | The number of results to return per page. |
| $filter | string | No | OData filter expression to filter call records. |
| $orderby | string | No | OData orderby expression to sort results. |

## Example Request

```bash
curl -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/communications/callRecords?$top=10" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "callrecord-001",
      "version": 1,
      "type": "peerToPeer",
      "modalities": [
        "audio"
      ],
      "startDateTime": "2025-01-20T14:00:00Z",
      "endDateTime": "2025-01-20T14:30:00Z"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `CallRecords.Read.All` scope.
2. Optionally specify query parameters to filter, sort, or paginate the results.
3. Send the GET request to the callRecords endpoint.
4. The response contains a `value` array of call record objects with details such as type, modalities, and timestamps.
