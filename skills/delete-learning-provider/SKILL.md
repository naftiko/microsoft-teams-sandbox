# Delete Learning Provider

Deletes a specific learning provider from the employee experience. This action is permanent and cannot be undone.

## API Details

- **API**: Microsoft Teams API
- **Method**: DELETE
- **Path**: `/employeeExperience/learningProviders/{learningProvider-id}`
- **Operation ID**: `deleteLearningProvider`
- **Tag**: EmployeeLearning
- **OpenAPI**: [microsoft-teams-openapi.yaml](../../openapi/microsoft-teams-openapi.yaml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/{learningProvider-id}`

## Required Headers

- `Authorization: Bearer {access-token}`

## Parameters

| Name | In | Type | Required | Description |
|---|---|---|---|---|
| `learningProvider-id` | path | string | Yes | The unique identifier of the learning provider to delete |

## Example Request

```bash
curl -s -X DELETE \
  "http://localhost:8080/rest/microsoft-teams-api/1.0.0/employeeExperience/learningProviders/provider-001" \
  -H "Authorization: Bearer {access-token}"
```

## Example Response

**Status Code**: 204 No Content

No response body is returned.

## Instructions

When the user wants to delete or remove a learning provider from the employee experience, use this operation. Provide the learning provider ID as a path parameter. This action permanently deletes the learning provider and may affect associated learning content.
