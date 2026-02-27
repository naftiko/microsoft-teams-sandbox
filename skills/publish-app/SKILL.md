# Publish App to Catalog

Publish an app to the Teams app catalog using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: `POST /appCatalogs/teamsApps`
- **operationId**: `publishApp`
- **Tag**: Apps

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`

## Required Headers

- `Authorization: Bearer {access_token}`
- `Content-Type: application/zip`

## OAuth Scopes

- `AppCatalog.Submit`

## Parameters

### Request Body

The request body must contain the Teams app package as a binary ZIP file.

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/microsoft-teams-api/1.0.0/appCatalogs/teamsApps" \
  -H "Authorization: Bearer {access_token}" \
  -H "Content-Type: application/zip" \
  --data-binary @my-app-package.zip
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

1. Obtain a valid access token with the `AppCatalog.Submit` scope.
2. Prepare the Teams app package as a ZIP file containing the app manifest and resources.
3. Send a POST request to the endpoint with the ZIP file as the binary request body.
4. Set the `Content-Type` header to `application/zip`.
5. A successful response returns HTTP 201 with the published app details.
