# Update Learning Content

Updates the properties of a specific learning content item. Only the properties included in the request body are updated.

## API Details

- **API**: Microsoft Teams API
- **Method**: PATCH
- **Path**: `/employeeExperience/learningProviders/{learningProvider-id}/learningContents/{learningContent-id}`
- **Operation ID**: `updateLearningContent`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/{learningProvider-id}/learningContents/{learningContent-id}`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `learningProvider-id` | path | string | Yes | The unique identifier of the learning provider |
| `learningContent-id` | path | string | Yes | The unique identifier of the learning content |

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `title` | string | No | The updated title of the learning content |
| `description` | string | No | The updated description |
| `contentWebUrl` | string | No | The updated URL to access the content |
| `duration` | string | No | The updated duration in ISO 8601 format |
| `level` | string | No | The updated difficulty level |
| `isActive` | boolean | No | Whether the content is active |
| `isSearchable` | boolean | No | Whether the content is searchable |

```json
{
  "title": "Introduction to Python - Updated",
  "description": "Learn the basics of Python programming with hands-on exercises",
  "level": "Beginner"
}
```

## Example Request

```bash
curl -s -X PATCH \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/provider-001/learningContents/content-001" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Introduction to Python - Updated",
    "description": "Learn the basics of Python programming with hands-on exercises",
    "level": "Beginner"
  }'
```

## Example Response

```json
{
  "id": "content-001",
  "externalId": "course-python-101",
  "title": "Introduction to Python - Updated",
  "description": "Learn the basics of Python programming with hands-on exercises",
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

When the user wants to update or modify an existing learning content item's properties such as its title, description, level, or active status, use this operation. Provide both the learning provider ID and learning content ID as path parameters and only include the fields that need to be changed in the request body.
