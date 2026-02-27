# Create Learning Content

Creates new learning content for a specific learning provider. Adds a course, module, or other learning resource to the provider's catalog.

## API Details

- **API**: Microsoft Teams API
- **Method**: POST
- **Path**: `/employeeExperience/learningProviders/{learningProvider-id}/learningContents`
- **Operation ID**: `createLearningContent`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/{learningProvider-id}/learningContents`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `learningProvider-id` | path | string | Yes | The unique identifier of the learning provider |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `externalId` | string | Yes | The external identifier for the content |
| `title` | string | Yes | The title of the learning content |
| `description` | string | No | A description of the learning content |
| `contentWebUrl` | string | No | The URL to access the content |
| `languageTag` | string | No | The language tag (e.g., en-US) |
| `duration` | string | No | The duration in ISO 8601 format |
| `format` | string | No | The content format (e.g., video, document) |
| `level` | string | No | The difficulty level (e.g., Beginner, Intermediate, Advanced) |
| `isActive` | boolean | No | Whether the content is active |
| `isSearchable` | boolean | No | Whether the content is searchable |

```json
{
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

## Example Request

```bash
curl -s -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/provider-001/learningContents" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
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
  }'
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

When the user wants to create or add new learning content to a learning provider, use this operation. Provide the learning provider ID as a path parameter and include the content details such as title, description, URL, format, and level in the request body. The response returns the created learning content with a 201 status code.
