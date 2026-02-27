# Delete Workforce Integration

Delete an existing workforce integration using the Microsoft Teams API.

## API Details

- **API Name**: Microsoft Teams API
- **OpenAPI Ref**: `../../openapi/microsoft-teams-openapi.yaml`
- **Endpoint**: DELETE /teamwork/workforceIntegrations/{workforceIntegration-id}
- **Operation ID**: deleteWorkforceIntegration
- **Tag**: WorkforceIntegrations

## Sandbox

- **Base URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0`
- **Full URL**: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations/{workforceIntegration-id}`

## Required Headers

- `Content-Type: application/json`
- `Authorization: Bearer {access_token}`

## OAuth Scopes

- `WorkforceIntegration.ReadWrite.All`

## Parameters

### Path Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| workforceIntegration-id | string | Yes | The unique identifier of the workforce integration to delete. |

## Example Request

```bash
curl -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/teamwork/workforceIntegrations/wfi-001" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer {access_token}"
```

## Example Response

```
HTTP/1.1 204 No Content
```

## Instructions

1. Obtain a valid access token with the `WorkforceIntegration.ReadWrite.All` scope.
2. Identify the workforce integration to delete by its `workforceIntegration-id`.
3. Send the DELETE request to the workforceIntegrations endpoint with the integration identifier.
4. A 204 No Content response indicates the workforce integration was successfully deleted.
5. No response body is returned for a successful deletion.
