# Projects

## Overview

### Available Operations

* [list_projects](#list_projects) - List all projects
* [create_project](#create_project) - Create a project
* [retrieve_project](#retrieve_project) - Retrieve a project
* [update_project](#update_project) - Update a project
* [partially_update_project](#partially_update_project) - Partially update a project
* [delete_project](#delete_project) - Delete a project

## list_projects

Retrieve a list of all projects. Optionally filter by client_id.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_projects" method="get" path="/api/projects/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.list_projects()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[List[models.Project]](../../models/.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## create_project

Create a new project for a client.

### Example Usage: BadRequest

<!-- UsageSnippet language="python" operationID="create_project" method="post" path="/api/projects/" example="BadRequest" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.create_project(project_name="<value>", project_type="portrait", client_id="97687fb3-35ce-4eb8-b192-c0abff07c71c")

    # Handle response
    print(res)

```
### Example Usage: Request

<!-- UsageSnippet language="python" operationID="create_project" method="post" path="/api/projects/" example="Request" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.create_project(project_name="Birthday Party", project_type="party", client_id="550e8400-e29b-41d4-a716-446655440002")

    # Handle response
    print(res)

```
### Example Usage: SuccessfulResponse

<!-- UsageSnippet language="python" operationID="create_project" method="post" path="/api/projects/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.create_project(project_name="<value>", project_type="portrait", client_id="97687fb3-35ce-4eb8-b192-c0abff07c71c")

    # Handle response
    print(res)

```
### Example Usage: Unauthorized

<!-- UsageSnippet language="python" operationID="create_project" method="post" path="/api/projects/" example="Unauthorized" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.create_project(project_name="<value>", project_type="portrait", client_id="97687fb3-35ce-4eb8-b192-c0abff07c71c")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `project_name`                                                                                           | *str*                                                                                                    | :heavy_check_mark:                                                                                       | Name of the project                                                                                      |
| `project_type`                                                                                           | [models.ProjectTypeEnum](../../models/projecttypeenum.md)                                                | :heavy_check_mark:                                                                                       | Type of project (event, portrait, or party)<br/><br/>* `event` - event<br/>* `portrait` - portrait<br/>* `party` - party |
| `client_id`                                                                                              | *str*                                                                                                    | :heavy_check_mark:                                                                                       | UUID of the client for this project                                                                      |
| `retries`                                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                         | :heavy_minus_sign:                                                                                       | Configuration to override the default retry behavior of the client.                                      |

### Response

**[models.Project](../../models/project.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## retrieve_project

Get a specific project by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="retrieve_project" method="get" path="/api/projects/{id}/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.retrieve_project(id="fbde4cc2-173b-4a75-a73a-4e7e70b72f3f")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | A UUID string identifying this project.                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Project](../../models/project.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## update_project

Update an existing project.

### Example Usage: BadRequest

<!-- UsageSnippet language="python" operationID="update_project" method="put" path="/api/projects/{id}/" example="BadRequest" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.update_project(id="6172f420-cc0c-45f3-a081-08ad7c9b021f", project_name="<value>", project_type="event", client_id="e6cdc396-9282-4d2d-ae93-8e844765ecc5")

    # Handle response
    print(res)

```
### Example Usage: NotFound

<!-- UsageSnippet language="python" operationID="update_project" method="put" path="/api/projects/{id}/" example="NotFound" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.update_project(id="a1d677b4-44ba-425a-95f9-73c1ecfee2e9", project_name="<value>", project_type="event", client_id="e6cdc396-9282-4d2d-ae93-8e844765ecc5")

    # Handle response
    print(res)

```
### Example Usage: SuccessfulResponse

<!-- UsageSnippet language="python" operationID="update_project" method="put" path="/api/projects/{id}/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.update_project(id="03bc43a0-a09d-4f68-8072-1fe6aed2ed5e", project_name="<value>", project_type="event", client_id="e6cdc396-9282-4d2d-ae93-8e844765ecc5")

    # Handle response
    print(res)

```
### Example Usage: Unauthorized

<!-- UsageSnippet language="python" operationID="update_project" method="put" path="/api/projects/{id}/" example="Unauthorized" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.update_project(id="2ffca99c-68c9-4c16-9d48-365d7ac052f2", project_name="<value>", project_type="event", client_id="e6cdc396-9282-4d2d-ae93-8e844765ecc5")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                     | *str*                                                                                                    | :heavy_check_mark:                                                                                       | A UUID string identifying this project.                                                                  |
| `project_name`                                                                                           | *str*                                                                                                    | :heavy_check_mark:                                                                                       | Name of the project                                                                                      |
| `project_type`                                                                                           | [models.ProjectTypeEnum](../../models/projecttypeenum.md)                                                | :heavy_check_mark:                                                                                       | Type of project (event, portrait, or party)<br/><br/>* `event` - event<br/>* `portrait` - portrait<br/>* `party` - party |
| `client_id`                                                                                              | *str*                                                                                                    | :heavy_check_mark:                                                                                       | UUID of the client for this project                                                                      |
| `retries`                                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                         | :heavy_minus_sign:                                                                                       | Configuration to override the default retry behavior of the client.                                      |

### Response

**[models.Project](../../models/project.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## partially_update_project

Partially update an existing project.

### Example Usage

<!-- UsageSnippet language="python" operationID="partially_update_project" method="patch" path="/api/projects/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.partially_update_project(id="699e6a41-ae9b-4bbd-b956-4f914c7a54a3")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                     | *str*                                                                                                    | :heavy_check_mark:                                                                                       | A UUID string identifying this project.                                                                  |
| `project_name`                                                                                           | *Optional[str]*                                                                                          | :heavy_minus_sign:                                                                                       | Name of the project                                                                                      |
| `project_type`                                                                                           | [Optional[models.ProjectTypeEnum]](../../models/projecttypeenum.md)                                      | :heavy_minus_sign:                                                                                       | Type of project (event, portrait, or party)<br/><br/>* `event` - event<br/>* `portrait` - portrait<br/>* `party` - party |
| `client_id`                                                                                              | *Optional[str]*                                                                                          | :heavy_minus_sign:                                                                                       | UUID of the client for this project                                                                      |
| `retries`                                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                         | :heavy_minus_sign:                                                                                       | Configuration to override the default retry behavior of the client.                                      |

### Response

**[models.Project](../../models/project.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## delete_project

Delete a project by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_project" method="delete" path="/api/projects/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    f_client.projects.delete_project(id="757c3501-8a89-4423-b07a-d32caa14b696")

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | A UUID string identifying this project.                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |