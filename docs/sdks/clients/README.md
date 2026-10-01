# Clients

## Overview

### Available Operations

* [list_clients](#list_clients) - List all clients
* [create_client](#create_client) - Create a client
* [retrieve_client](#retrieve_client) - Retrieve a client
* [clients_update](#clients_update) - Update a client
* [clients_partial_update](#clients_partial_update) - Partially update a client
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
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.Client](../../models/client.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## clients_update

Update a client by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="clients_update" method="put" path="/api/clients/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.clients_update(id="3b1655ff-b54c-49dd-bcdd-dfdaaa356154", first_name="Nestor", last_name="Kilback", city="Charleston", state="Pennsylvania", zip_code="35804", email="Thora85@hotmail.com", phone_number="350.580.4982 x524")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
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

## clients_partial_update

Partially update a client by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="clients_partial_update" method="patch" path="/api/clients/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.clients.clients_partial_update(id="1cb03e38-893d-48af-892e-6be5bf6fd6f9")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
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
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |