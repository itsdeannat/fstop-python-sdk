# Projects

## Overview

### Available Operations

* [list_projects](#list_projects) - List all projects
* [create_project](#create_project) - Create a project
* [retrieve_project](#retrieve_project) - Retrieve a project
* [projects_update](#projects_update) - Update a project
* [projects_partial_update](#projects_partial_update) - Partially update a project
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

**[List[models.ProjectOutput]](../../models/.md)**

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

**[models.ProjectOutput](../../models/projectoutput.md)**

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
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ProjectOutput](../../models/projectoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## projects_update

Update a project by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="projects_update" method="put" path="/api/projects/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.projects_update(id="5c1e2a68-61ed-4eb8-a1c3-5cc03b9763f1", project_name="<value>", project_type="party", client_id="7e984de6-a6c3-43b4-9dff-7eb9b88b7616")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                     | *str*                                                                                                    | :heavy_check_mark:                                                                                       | Unique identifier of the resource.                                                                       |
| `project_name`                                                                                           | *str*                                                                                                    | :heavy_check_mark:                                                                                       | Name of the project                                                                                      |
| `project_type`                                                                                           | [models.ProjectTypeEnum](../../models/projecttypeenum.md)                                                | :heavy_check_mark:                                                                                       | Type of project (event, portrait, or party)<br/><br/>* `event` - event<br/>* `portrait` - portrait<br/>* `party` - party |
| `client_id`                                                                                              | *str*                                                                                                    | :heavy_check_mark:                                                                                       | UUID of the client for this project                                                                      |
| `retries`                                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                         | :heavy_minus_sign:                                                                                       | Configuration to override the default retry behavior of the client.                                      |

### Response

**[models.ProjectOutput](../../models/projectoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## projects_partial_update

Partially update a project by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="projects_partial_update" method="patch" path="/api/projects/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.projects.projects_partial_update(id="dbc062af-47b2-40c4-9ea4-1787d6a9e9cb")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                     | *str*                                                                                                    | :heavy_check_mark:                                                                                       | Unique identifier of the resource.                                                                       |
| `project_name`                                                                                           | *Optional[str]*                                                                                          | :heavy_minus_sign:                                                                                       | Name of the project                                                                                      |
| `project_type`                                                                                           | [Optional[models.ProjectTypeEnum]](../../models/projecttypeenum.md)                                      | :heavy_minus_sign:                                                                                       | Type of project (event, portrait, or party)<br/><br/>* `event` - event<br/>* `portrait` - portrait<br/>* `party` - party |
| `client_id`                                                                                              | *Optional[str]*                                                                                          | :heavy_minus_sign:                                                                                       | UUID of the client for this project                                                                      |
| `retries`                                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                         | :heavy_minus_sign:                                                                                       | Configuration to override the default retry behavior of the client.                                      |

### Response

**[models.ProjectOutput](../../models/projectoutput.md)**

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
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |