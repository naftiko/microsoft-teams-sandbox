# Delete App from Catalog

Delete an app from the Teams app catalog using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `DELETE /appCatalogs/teamsApps/{app-id}`
- **operationId**: `deleteApp`
- **Tag**: Apps

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `AppCatalog.ReadWrite.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| app-id | string | Yes | The unique identifier of the app |

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/microsoft-teams-api/1.0.0/appCatalogs/teamsApps/{app-id}" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```
HTTP/1.1 204 No Content
```

## Instructions

1. Obtain a valid access token with the `AppCatalog.ReadWrite.All` scope.
2. Identify the `app-id` for the app to delete.
3. Send a DELETE request to the endpoint with the required path parameter.
4. A successful response returns HTTP 204 with no content.
