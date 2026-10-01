# Galleries

## Overview

### Available Operations

* [list_galleries](#list_galleries) - List all galleries
* [create_gallery](#create_gallery) - Create a gallery
* [retrieve_gallery](#retrieve_gallery) - Retrieve a gallery
* [galleries_update](#galleries_update) - Update a gallery
* [galleries_partial_update](#galleries_partial_update) - Partially update a gallery
* [delete_gallery](#delete_gallery) - Delete a gallery

## list_galleries

Retrieve a list of all galleries. Optionally filter by project_id.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_galleries" method="get" path="/api/galleries/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.galleries.list_galleries()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[List[models.GalleryOutput]](../../models/.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## create_gallery

Create a new gallery for a project.

### Example Usage: BadRequest

<!-- UsageSnippet language="python" operationID="create_gallery" method="post" path="/api/galleries/" example="BadRequest" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.galleries.create_gallery(project_id="c2542d62-2158-40d7-958e-d3f200cf14bc", gallery_name="<value>", picture_count=470532, is_visible=False, url="https://close-soybean.org")

    # Handle response
    print(res)

```
### Example Usage: Request

<!-- UsageSnippet language="python" operationID="create_gallery" method="post" path="/api/galleries/" example="Request" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.galleries.create_gallery(project_id="660e8400-e29b-41d4-a716-446655440000", gallery_name="Reception Photos", picture_count=89, is_visible=True, url="https://example.com/galleries/reception")

    # Handle response
    print(res)

```
### Example Usage: SuccessfulResponse

<!-- UsageSnippet language="python" operationID="create_gallery" method="post" path="/api/galleries/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.galleries.create_gallery(project_id="c2542d62-2158-40d7-958e-d3f200cf14bc", gallery_name="<value>", picture_count=470532, is_visible=False, url="https://close-soybean.org")

    # Handle response
    print(res)

```
### Example Usage: Unauthorized

<!-- UsageSnippet language="python" operationID="create_gallery" method="post" path="/api/galleries/" example="Unauthorized" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.galleries.create_gallery(project_id="c2542d62-2158-40d7-958e-d3f200cf14bc", gallery_name="<value>", picture_count=470532, is_visible=False, url="https://close-soybean.org")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | UUID of the project for this gallery                                |
| `gallery_name`                                                      | *str*                                                               | :heavy_check_mark:                                                  | Name of the gallery                                                 |
| `picture_count`                                                     | *int*                                                               | :heavy_check_mark:                                                  | Number of pictures in the gallery                                   |
| `is_visible`                                                        | *bool*                                                              | :heavy_check_mark:                                                  | Whether the gallery is publicly visible                             |
| `url`                                                               | *str*                                                               | :heavy_check_mark:                                                  | URL link to the gallery                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GalleryOutput](../../models/galleryoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## retrieve_gallery

Get a specific gallery by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="retrieve_gallery" method="get" path="/api/galleries/{id}/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.galleries.retrieve_gallery(id="82ef9e72-f2f7-41ff-ae6d-2d7622a989c6")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GalleryOutput](../../models/galleryoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## galleries_update

Update a gallery by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="galleries_update" method="put" path="/api/galleries/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.galleries.galleries_update(id="f50b1668-e4a6-40ef-bce0-48ad6d4c6854", project_id="1b3a2be3-3b01-4f10-9a2b-6b3447fc1c92", gallery_name="<value>", picture_count=475576, is_visible=False, url="https://personal-barracks.org/")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
| `project_id`                                                        | *str*                                                               | :heavy_check_mark:                                                  | UUID of the project for this gallery                                |
| `gallery_name`                                                      | *str*                                                               | :heavy_check_mark:                                                  | Name of the gallery                                                 |
| `picture_count`                                                     | *int*                                                               | :heavy_check_mark:                                                  | Number of pictures in the gallery                                   |
| `is_visible`                                                        | *bool*                                                              | :heavy_check_mark:                                                  | Whether the gallery is publicly visible                             |
| `url`                                                               | *str*                                                               | :heavy_check_mark:                                                  | URL link to the gallery                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GalleryOutput](../../models/galleryoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## galleries_partial_update

Partially update a gallery by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="galleries_partial_update" method="patch" path="/api/galleries/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.galleries.galleries_partial_update(id="dbbf72ca-a804-4e6f-ba9a-781da9e110f7")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
| `project_id`                                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | UUID of the project for this gallery                                |
| `gallery_name`                                                      | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Name of the gallery                                                 |
| `picture_count`                                                     | *Optional[int]*                                                     | :heavy_minus_sign:                                                  | Number of pictures in the gallery                                   |
| `is_visible`                                                        | *Optional[bool]*                                                    | :heavy_minus_sign:                                                  | Whether the gallery is publicly visible                             |
| `url`                                                               | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | URL link to the gallery                                             |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GalleryOutput](../../models/galleryoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## delete_gallery

Delete a gallery by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_gallery" method="delete" path="/api/galleries/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    f_client.galleries.delete_gallery(id="5ece5a2b-7d31-4cab-8796-66cc9fc5ad56")

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