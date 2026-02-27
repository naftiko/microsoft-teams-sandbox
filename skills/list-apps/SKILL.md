# List Teams Apps

Retrieve the list of apps published in the Teams app catalog using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `GET /appCatalogs/teamsApps`
- **operationId**: `listApps`
- **Tag**: Apps

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `AppCatalog.Read.All`

## Parameters

### Query Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| $top | integer | No | The number of results to return |
| $filter | string | No | OData filter expression |
| $select | string | No | OData select expression to choose specific properties |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/appCatalogs/teamsApps" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "app-id-001",
      "externalId": "com.example.myapp",
      "displayName": "My Custom App",
      "distributionMethod": "organization"
    },
    {
      "id": "app-id-002",
      "externalId": "com.example.otherapp",
      "displayName": "Another App",
      "distributionMethod": "store"
    }
  ]
}
```

## Instructions

1. Obtain a valid access token with the `AppCatalog.Read.All` scope.
2. Send a GET request to the endpoint.
3. Optionally include `$top`, `$filter`, or `$select` query parameters to refine results.
4. Parse the response to retrieve the list of apps in the catalog.
