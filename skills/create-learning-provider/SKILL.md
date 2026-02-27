# Register Learning Provider

Registers a new learning provider in the employee experience. Creates a provider resource that can host and deliver learning content to users.

## API Details

- **API**: Microsoft Teams API
- **Method**: POST
- **Path**: `/employeeExperience/learningProviders`
- **Operation ID**: `createLearningProvider`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders`

## Required Headers

- `Authorization: Bearer {access-token}`
- `Content-Type: application/json`

## OAuth Scopes

- `LearningProvider.ReadWrite`

## Request Body

| Field | Type | Required | Description |
|---|---|---|---|
| `displayName` | string | Yes | The display name of the learning provider |
| `loginWebUrl` | string | No | The login URL for the learning provider |
| `isCourseActivitySyncEnabled` | boolean | No | Whether course activity sync is enabled |

```json
{
  "displayName": "LinkedIn Learning",
  "loginWebUrl": "https://www.linkedin.com/learning",
  "isCourseActivitySyncEnabled": true
}
```

## Example Request

```bash
curl -s -X POST \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "LinkedIn Learning",
    "loginWebUrl": "https://www.linkedin.com/learning",
    "isCourseActivitySyncEnabled": true
  }'
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

When the user wants to register or create a new learning provider in the employee experience, use this operation. Provide the display name, login URL, and sync configuration in the request body. The response returns the created learning provider with a 201 status code.
