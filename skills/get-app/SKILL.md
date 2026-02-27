# Get App

Retrieve the properties of a specific app from the Teams app catalog using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `GET /appCatalogs/teamsApps/{app-id}`
- **operationId**: `getApp`
- **Tag**: Apps

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `AppCatalog.Read.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| app-id | string | Yes | The unique identifier of the app |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/microsoft-teams-api/1.0.0/appCatalogs/teamsApps/{app-id}" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```json
{
  "id": "app-id-001",
  "externalId": "com.example.myapp",
  "displayName": "My Custom App",
  "distributionMethod": "organization"
}
```

## Instructions

1. Obtain a valid access token with the `AppCatalog.Read.All` scope.
2. Identify the `app-id` for the target app.
3. Send a GET request to the endpoint with the required path parameter.
4. Parse the response to retrieve the app properties.
