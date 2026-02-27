# Get Learning Content

Retrieves the details of a specific learning content item by its unique identifier within a learning provider. Returns the learning content resource with its properties.

## API Details

- **API**: Microsoft Teams API
- **Method**: GET
- **Path**: `/employeeExperience/learningProviders/{learningProvider-id}/learningContents/{learningContent-id}`
- **Operation ID**: `getLearningContent`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/{learningProvider-id}/learningContents/{learningContent-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `learningProvider-id` | path | string | Yes | The unique identifier of the learning provider |
| `learningContent-id` | path | string | Yes | The unique identifier of the learning content |

## Example Request

```bash
curl -s -X GET \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/provider-001/learningContents/content-001" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

```json
{
  "id": "content-001",
  "externalId": "course-python-101",
  "title": "Introduction to Python",
  "description": "Learn the basics of Python programming",
  "contentWebUrl": "https://learning.example.com/courses/python-101",
  "languageTag": "en-US",
  "duration": "PT2H30M",
  "format": "video",
  "level": "Beginner",
  "isActive": true,
  "isSearchable": true
}
```

## Instructions

When the user wants to retrieve details about a specific learning content item from a learning provider, use this operation. Provide both the learning provider ID and learning content ID as path parameters. The response includes the content's title, description, format, level, and other configuration properties.
