# List Learning Providers

Lists all registered learning providers in the employee experience. Returns a paginated collection of learning provider resources with their configuration details.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/employeeExperience/learningProviders`
- **Operation ID**: `listLearningProviders`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders`

## Required Headers

- `Authorization: Bearer {access-token}`

## OAuth Scopes

- `LearningProvider.Read`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `$top` | query | integer | No | Number of learning providers to return per page |
| `$filter` | query | string | No | OData filter expression |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders?%24top=10" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "provider-001",
      "displayName": "LinkedIn Learning",
      "loginWebUrl": "https://www.linkedin.com/learning",
      "isCourseActivitySyncEnabled": true
    },
    {
      "id": "provider-002",
      "displayName": "Coursera",
      "loginWebUrl": "https://www.coursera.org",
      "isCourseActivitySyncEnabled": false
    }
  ]
}
```

## Instructions

When the user wants to list or browse registered learning providers in the employee experience, use this operation. Use `$top` to control pagination and `$filter` to narrow results by specific criteria such as display name or sync status.
