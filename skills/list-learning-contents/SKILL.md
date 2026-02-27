# List Learning Content

Lists all learning content for a specific learning provider. Returns a paginated collection of learning content resources with their details.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/employeeExperience/learningProviders/{learningProvider-id}/learningContents`
- **Operation ID**: `listLearningContents`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/{learningProvider-id}/learningContents`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `learningProvider-id` | path | string | Yes | The unique identifier of the learning provider |
| `$top` | query | integer | No | Number of learning content items to return per page |
| `$filter` | query | string | No | OData filter expression |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/provider-001/learningContents?%24top=10" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "value": [
    {
      "id": "content-001",
      "externalId": "course-python-101",
      "title": "Introduction to Python",
      "description": "Learn the basics of Python programming",
      "level": "Beginner",
      "isActive": true
    },
    {
      "id": "content-002",
      "externalId": "course-cloud-201",
      "title": "Cloud Architecture Fundamentals",
      "description": "Design scalable cloud solutions",
      "level": "Intermediate",
      "isActive": true
    }
  ]
}
```

## Instructions

When the user wants to list or browse learning content for a specific learning provider, use this operation. Provide the learning provider ID as a path parameter. Use `$top` to control pagination and `$filter` to narrow results by criteria such as title, level, or active status.
