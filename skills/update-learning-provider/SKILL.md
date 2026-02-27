# Update Learning Provider

Updates the properties of a specific learning provider. Only the properties included in the request body are updated.

## API Details

- **API**: Microsoft Teams API
- **Method**: PATCH
- **Path**: `/employeeExperience/learningProviders/{learningProvider-id}`
- **Operation ID**: `updateLearningProvider`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/{learningProvider-id}`

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
| `displayName` | string | No | The updated display name of the learning provider |
| `loginWebUrl` | string | No | The updated login URL |
| `isCourseActivitySyncEnabled` | boolean | No | Whether course activity sync is enabled |

```json
{
  "displayName": "LinkedIn Learning - Updated",
  "isCourseActivitySyncEnabled": false
}
```

## Example Request

```bash
curl -s -X PATCH \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/provider-001" \
  -H "Authorization: Bearer {access-token}" \
  -H "Content-Type: application/json" \
  -d '{
    "displayName": "LinkedIn Learning - Updated",
    "isCourseActivitySyncEnabled": false
  }'
```

## Example Response

```json
{
  "id": "provider-001",
  "displayName": "LinkedIn Learning - Updated",
  "loginWebUrl": "https://www.linkedin.com/learning",
  "isCourseActivitySyncEnabled": false
}
```

## Instructions

When the user wants to update or modify an existing learning provider's properties such as its name, login URL, or sync configuration, use this operation. Provide the learning provider ID as a path parameter and only include the fields that need to be changed in the request body.
