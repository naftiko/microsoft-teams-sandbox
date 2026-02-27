# Delete Learning Content

Deletes a specific learning content item from a learning provider. This action is permanent and cannot be undone.

## API Details

- **API**: Microsoft Teams API
- **Method**: DELETE
- **Path**: `/employeeExperience/learningProviders/{learningProvider-id}/learningContents/{learningContent-id}`
- **Operation ID**: `deleteLearningContent`
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
| `learningContent-id` | path | string | Yes | The unique identifier of the learning content to delete |

## Example Request

```bash
curl -s -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/provider-001/learningContents/content-001" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to delete or remove a learning content item from a learning provider, use this operation. Provide both the learning provider ID and learning content ID as path parameters. This action permanently removes the learning content from the provider's catalog.
