# Bookings

## Overview

### Available Operations

* [list_bookings](#list_bookings) - List all bookings
* [create_booking](#create_booking) - Create a booking
* [retrieve_booking](#retrieve_booking) - Retrieve a booking
* [bookings_update](#bookings_update) - Update a booking
* [bookings_partial_update](#bookings_partial_update) - Partially update a booking
* [delete_booking](#delete_booking) - Delete a booking

## list_bookings

Retrieve a list of all bookings. Optionally, filter by project_id.

### Example Usage

<!-- UsageSnippet language="python" operationID="list_bookings" method="get" path="/api/bookings/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.list_bookings()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[List[models.BookingOutput]](../../models/.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## create_booking

Create a new booking for a project.

### Example Usage: BadRequest

<!-- UsageSnippet language="python" operationID="create_booking" method="post" path="/api/bookings/" example="BadRequest" -->
```python
from datetime import date
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.create_booking(project_id="60827b2d-0bbc-4e41-9c36-c85909e61c5c", date_=date.fromisoformat("2026-09-24"), time="<value>", duration=241323, location="<value>")

    # Handle response
    print(res)

```
### Example Usage: Request

<!-- UsageSnippet language="python" operationID="create_booking" method="post" path="/api/bookings/" example="Request" -->
```python
from datetime import date
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.create_booking(project_id="660e8400-e29b-41d4-a716-446655440000", date_=date.fromisoformat("2026-06-15"), time="14:00:00", duration=480, location="Downtown Venue")

    # Handle response
    print(res)

```
### Example Usage: SuccessfulResponse

<!-- UsageSnippet language="python" operationID="create_booking" method="post" path="/api/bookings/" example="SuccessfulResponse" -->
```python
from datetime import date
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.create_booking(project_id="60827b2d-0bbc-4e41-9c36-c85909e61c5c", date_=date.fromisoformat("2026-09-24"), time="<value>", duration=241323, location="<value>")

    # Handle response
    print(res)

```
### Example Usage: Unauthorized

<!-- UsageSnippet language="python" operationID="create_booking" method="post" path="/api/bookings/" example="Unauthorized" -->
```python
from datetime import date
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.create_booking(project_id="60827b2d-0bbc-4e41-9c36-c85909e61c5c", date_=date.fromisoformat("2026-09-24"), time="<value>", duration=241323, location="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `project_id`                                                                 | *str*                                                                        | :heavy_check_mark:                                                           | UUID of the project for this booking                                         |
| `date_`                                                                      | [datetime](https://docs.python.org/3/library/datetime.html#datetime-objects) | :heavy_check_mark:                                                           | Date of the booking                                                          |
| `time`                                                                       | *str*                                                                        | :heavy_check_mark:                                                           | Time of the booking                                                          |
| `duration`                                                                   | *int*                                                                        | :heavy_check_mark:                                                           | Booking duration in minutes                                                  |
| `location`                                                                   | *str*                                                                        | :heavy_check_mark:                                                           | Booking location                                                             |
| `retries`                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)             | :heavy_minus_sign:                                                           | Configuration to override the default retry behavior of the client.          |

### Response

**[models.BookingOutput](../../models/bookingoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## retrieve_booking

Get a specific booking by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="retrieve_booking" method="get" path="/api/bookings/{id}/" example="SuccessfulResponse" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.retrieve_booking(id="df9d5751-02dd-4ef8-994f-db398aac0109")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *str*                                                               | :heavy_check_mark:                                                  | Unique identifier of the resource.                                  |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.BookingOutput](../../models/bookingoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## bookings_update

Update a booking by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="bookings_update" method="put" path="/api/bookings/{id}/" -->
```python
from datetime import date
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.bookings_update(id="591beef0-999c-4003-8470-b997a21d62fc", project_id="c62ec803-1632-4541-a02e-21c63e43d349", date_=date.fromisoformat("2026-09-20"), time="<value>", duration=970852, location="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `id`                                                                         | *str*                                                                        | :heavy_check_mark:                                                           | Unique identifier of the resource.                                           |
| `project_id`                                                                 | *str*                                                                        | :heavy_check_mark:                                                           | UUID of the project for this booking                                         |
| `date_`                                                                      | [datetime](https://docs.python.org/3/library/datetime.html#datetime-objects) | :heavy_check_mark:                                                           | Date of the booking                                                          |
| `time`                                                                       | *str*                                                                        | :heavy_check_mark:                                                           | Time of the booking                                                          |
| `duration`                                                                   | *int*                                                                        | :heavy_check_mark:                                                           | Booking duration in minutes                                                  |
| `location`                                                                   | *str*                                                                        | :heavy_check_mark:                                                           | Booking location                                                             |
| `retries`                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)             | :heavy_minus_sign:                                                           | Configuration to override the default retry behavior of the client.          |

### Response

**[models.BookingOutput](../../models/bookingoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## bookings_partial_update

Partially update a booking by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="bookings_partial_update" method="patch" path="/api/bookings/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.bookings_partial_update(id="43da1f69-3b3e-439b-aa32-fda50fe0ca39")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `id`                                                                         | *str*                                                                        | :heavy_check_mark:                                                           | Unique identifier of the resource.                                           |
| `project_id`                                                                 | *Optional[str]*                                                              | :heavy_minus_sign:                                                           | UUID of the project for this booking                                         |
| `date_`                                                                      | [datetime](https://docs.python.org/3/library/datetime.html#datetime-objects) | :heavy_minus_sign:                                                           | Date of the booking                                                          |
| `time`                                                                       | *Optional[str]*                                                              | :heavy_minus_sign:                                                           | Time of the booking                                                          |
| `duration`                                                                   | *Optional[int]*                                                              | :heavy_minus_sign:                                                           | Booking duration in minutes                                                  |
| `location`                                                                   | *Optional[str]*                                                              | :heavy_minus_sign:                                                           | Booking location                                                             |
| `retries`                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)             | :heavy_minus_sign:                                                           | Configuration to override the default retry behavior of the client.          |

### Response

**[models.BookingOutput](../../models/bookingoutput.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.BadRequestError   | 400                      | application/json         |
| errors.UnauthorizedError | 401                      | application/json         |
| errors.NotFoundError     | 404                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## delete_booking

Delete a booking by ID.

### Example Usage

<!-- UsageSnippet language="python" operationID="delete_booking" method="delete" path="/api/bookings/{id}/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    f_client.bookings.delete_booking(id="78878836-4c9e-4e9b-8667-4316dc94f27e")

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