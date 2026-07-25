# Clients

## Overview

### Available Operations

* [list_clients](#list_clients) - List all clients
* [create_client](#create_client) - Create a client
* [retrieve_client](#retrieve_client) - Retrieve a client
* [update_client](#update_client) - Update a client
* [partially_update_client](#partially_update_client) - Partially update a client
* [delete_client](#delete_client) - Delete a client

## list_clients

Retrieve a list of all clients in the system.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_clients" method="get" path="/api/clients/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.list_clients()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[List[models.Client]](../../models/.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## create_client

Create a new client.

### Example Usage: BadRequest

<!-- UsageSnippet language="python" operationID="create_client" method="post" path="/api/clients/" example="BadRequest" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.create_client(first_name="Adonis", last_name="Bahringer", city="Fort Nova", state="Georgia", zip_code="50179", email="Clotilde.Hintz8@yahoo.com", phone_number="312.391.3315 x8251")

    # Handle response
    print(res)

```
### Example Usage: Request

<!-- UsageSnippet language="python" operationID="create_client" method="post" path="/api/clients/" example="Request" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.create_client(first_name="Alice", last_name="Johnson", city="Cincinnati", state="OH", zip_code="45202", email="alice.johnson@example.com", phone_number="+12161239999")

    # Handle response
    print(res)

```
### Example Usage: SuccessfulResponse

<!-- UsageSnippet language="python" operationID="create_client" method="post" path="/api/clients/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.create_client(first_name="Adonis", last_name="Bahringer", city="Fort Nova", state="Georgia", zip_code="50179", email="Clotilde.Hintz8@yahoo.com", phone_number="312.391.3315 x8251")

    # Handle response
    print(res)

```
### Example Usage: Unauthorized

<!-- UsageSnippet language="python" operationID="create_client" method="post" path="/api/clients/" example="Unauthorized" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.create_client(first_name="Adonis", last_name="Bahringer", city="Fort Nova", state="Georgia", zip_code="50179", email="Clotilde.Hintz8@yahoo.com", phone_number="312.391.3315 x8251")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `first_name`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Client's first name                                                 |
| `last_name`                                                         | *str*                                                               | :heavy_check_mark:                                                  | Client's last name                                                  |
| `city`                                                              | *str*                                                               | :heavy_check_mark:                                                  | City where client is located                                        |
| `state`                                                             | *str*                                                               | :heavy_check_mark:                                                  | State abbreviation (e.g., CA, NY)                                   |
| `zip_code`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Postal code for client's address                                    |
| `email`                                                             | *str*                                                               | :heavy_check_mark:                                                  | Client's email address for contact                                  |
| `phone_number`                                                      | *str*                                                               | :heavy_check_mark:                                                  | Client's phone number                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Client](../../models/client.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## retrieve_client

Get a specific client by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="retrieve_client" method="get" path="/api/clients/{id}/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.retrieve_client(id="f41dee16-4754-4fa4-9c82-d6079305f54c")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | A UUID string identifying this client.                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Client](../../models/client.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## update_client

Update an existing client.

### Example Usage: BadRequest

<!-- UsageSnippet language="python" operationID="update_client" method="put" path="/api/clients/{id}/" example="BadRequest" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.update_client(id="8b32958e-9502-42e2-90c2-4d406cd0fdfe", first_name="Maxwell", last_name="Hoeger", city="Schmittshire", state="Michigan", zip_code="14512-8813", email="Madelynn77@hotmail.com", phone_number="917-654-0044 x6213")

    # Handle response
    print(res)

```
### Example Usage: NotFound

<!-- UsageSnippet language="python" operationID="update_client" method="put" path="/api/clients/{id}/" example="NotFound" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.update_client(id="b496550f-2ed3-4503-9e52-dbd9e6c8f688", first_name="Maxwell", last_name="Hoeger", city="Schmittshire", state="Michigan", zip_code="14512-8813", email="Madelynn77@hotmail.com", phone_number="917-654-0044 x6213")

    # Handle response
    print(res)

```
### Example Usage: SuccessfulResponse

<!-- UsageSnippet language="python" operationID="update_client" method="put" path="/api/clients/{id}/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.update_client(id="2b946d1c-c429-41ce-8472-c4615bf253ad", first_name="Maxwell", last_name="Hoeger", city="Schmittshire", state="Michigan", zip_code="14512-8813", email="Madelynn77@hotmail.com", phone_number="917-654-0044 x6213")

    # Handle response
    print(res)

```
### Example Usage: Unauthorized

<!-- UsageSnippet language="python" operationID="update_client" method="put" path="/api/clients/{id}/" example="Unauthorized" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.update_client(id="96d2995a-51d6-4485-b92b-eb1525c03a13", first_name="Maxwell", last_name="Hoeger", city="Schmittshire", state="Michigan", zip_code="14512-8813", email="Madelynn77@hotmail.com", phone_number="917-654-0044 x6213")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | A UUID string identifying this client.                              |
| `first_name`                                                        | *str*                                                               | :heavy_check_mark:                                                  | Client's first name                                                 |
| `last_name`                                                         | *str*                                                               | :heavy_check_mark:                                                  | Client's last name                                                  |
| `city`                                                              | *str*                                                               | :heavy_check_mark:                                                  | City where client is located                                        |
| `state`                                                             | *str*                                                               | :heavy_check_mark:                                                  | State abbreviation (e.g., CA, NY)                                   |
| `zip_code`                                                          | *str*                                                               | :heavy_check_mark:                                                  | Postal code for client's address                                    |
| `email`                                                             | *str*                                                               | :heavy_check_mark:                                                  | Client's email address for contact                                  |
| `phone_number`                                                      | *str*                                                               | :heavy_check_mark:                                                  | Client's phone number                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Client](../../models/client.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## partially_update_client

Partially update an existing client.

### Example Usage

<!-- UsageSnippet language="python" operationID="partially_update_client" method="patch" path="/api/clients/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.partially_update_client(id="5da8c191-5f1a-43a9-b0f9-227f0080cc26")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | A UUID string identifying this client.                              |
| `first_name`                                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Client's first name                                                 |
| `last_name`                                                         | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Client's last name                                                  |
| `city`                                                              | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | City where client is located                                        |
| `state`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | State abbreviation (e.g., CA, NY)                                   |
| `zip_code`                                                          | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Postal code for client's address                                    |
| `email`                                                             | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Client's email address for contact                                  |
| `phone_number`                                                      | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | Client's phone number                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Client](../../models/client.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## delete_client

Delete a client by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_client" method="delete" path="/api/clients/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    f_client.clients.delete_client(id="313d4aeb-2558-4a20-acec-571613331767")

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | A UUID string identifying this client.                              |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |