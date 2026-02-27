# Get Learning Provider

Retrieves the details of a specific learning provider by its unique identifier. Returns the learning provider resource with its configuration properties.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/employeeExperience/learningProviders/{learningProvider-id}`
- **Operation ID**: `getLearningProvider`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/{learningProvider-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `learningProvider-id` | path | string | Yes | The unique identifier of the learning provider |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/provider-001" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "id": "provider-001",
  "displayName": "LinkedIn Learning",
  "loginWebUrl": "https://www.linkedin.com/learning",
  "isCourseActivitySyncEnabled": true
}
```

## Instructions

When the user wants to retrieve details about a specific learning provider, use this operation. Provide the learning provider ID as a path parameter. The response includes the provider's display name, login URL, and course activity sync configuration.
