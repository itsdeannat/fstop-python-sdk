# fstop

Developer-friendly & type-safe Python SDK specifically catered to leverage *fstop* API.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=fstop&utm_campaign=python)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/fstop/fstop-api). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

Fstop: The Fstop API enables developers to build integrations and automations for the Fstop photography business platform. Manage clients, projects, bookings, and galleries programmatically.
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [fstop](#fstop)
  * [SDK Installation](#sdk-installation)
  * [IDE Support](#ide-support)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
  * [Resource Management](#resource-management)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

> [!TIP]
> To finish publishing your SDK to PyPI you must [run your first generation action](https://www.speakeasy.com/docs/github-setup#step-by-step-guide).


> [!NOTE]
> **Python version upgrade policy**
>
> Once a Python version reaches its [official end of life date](https://devguide.python.org/versions/), a 3-month grace period is provided for users to upgrade. Following this grace period, the minimum python version supported in the SDK will be updated.

The SDK can be installed with *uv*, *pip*, or *poetry* package managers.

### uv

*uv* is a fast Python package installer and resolver, designed as a drop-in replacement for pip and pip-tools. It's recommended for its speed and modern Python tooling capabilities.

```bash
uv add git+<UNSET>.git
```

### PIP

*PIP* is the default package installer for Python, enabling easy installation and management of packages from PyPI via the command line.

```bash
pip install git+<UNSET>.git
```

### Poetry

*Poetry* is a modern tool that simplifies dependency management and package publishing by using a single `pyproject.toml` file to handle project metadata and dependencies.

```bash
poetry add git+<UNSET>.git
```

### Shell and script usage with `uv`

You can use this SDK in a Python shell with [uv](https://docs.astral.sh/uv/) and the `uvx` command that comes with it like so:

```shell
uvx --from fstop python
```

It's also possible to write a standalone Python script without needing to set up a whole project like so:

```python
#!/usr/bin/env -S uv run --script
# /// script
# requires-python = ">=3.10"
# dependencies = [
#     "fstop",
# ]
# ///

from fstop import Fstop

sdk = Fstop(
  # SDK arguments
)

# Rest of script here...
```

Once that is saved to a file, you can run it with `uv run script.py` where
`script.py` can be replaced with the actual file name.
<!-- End SDK Installation [installation] -->

<!-- Start IDE Support [idesupport] -->
## IDE Support

### PyCharm

Generally, the SDK will work well with most IDEs out of the box. However, when using PyCharm, you can enjoy much better integration with Pydantic by installing an additional plugin.

- [PyCharm Pydantic Plugin](https://docs.pydantic.dev/latest/integrations/pycharm/)
<!-- End IDE Support [idesupport] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```python
# Synchronous Example
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.list_bookings()

    # Handle response
    print(res)
```

</br>

The same SDK client can also be used to make asynchronous requests by importing asyncio.

```python
# Asynchronous Example
import asyncio
from fstop import Fstop
import os

async def main():

    async with Fstop(
        jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
    ) as f_client:

        res = await f_client.bookings.list_bookings_async()

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name       | Type | Scheme      | Environment Variable |
| ---------- | ---- | ----------- | -------------------- |
| `jwt_auth` | http | HTTP Bearer | `FSTOP_JWT_AUTH`     |

To authenticate with the API the `jwt_auth` parameter must be set when initializing the SDK client instance. For example:
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
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [Bookings](docs/sdks/bookings/README.md)

* [list_bookings](docs/sdks/bookings/README.md#list_bookings) - List all bookings
* [create_booking](docs/sdks/bookings/README.md#create_booking) - Create a booking
* [retrieve_booking](docs/sdks/bookings/README.md#retrieve_booking) - Retrieve a booking
* [update_booking](docs/sdks/bookings/README.md#update_booking) - Update a booking
* [partially_update_booking](docs/sdks/bookings/README.md#partially_update_booking) - Partially update a booking
* [delete_booking](docs/sdks/bookings/README.md#delete_booking) - Delete a booking

### [Clients](docs/sdks/clients/README.md)

* [list_clients](docs/sdks/clients/README.md#list_clients) - List all clients
* [create_client](docs/sdks/clients/README.md#create_client) - Create a client
* [retrieve_client](docs/sdks/clients/README.md#retrieve_client) - Retrieve a client
* [update_client](docs/sdks/clients/README.md#update_client) - Update a client
* [partially_update_client](docs/sdks/clients/README.md#partially_update_client) - Partially update a client
* [delete_client](docs/sdks/clients/README.md#delete_client) - Delete a client

### [Galleries](docs/sdks/galleries/README.md)

* [list_galleries](docs/sdks/galleries/README.md#list_galleries) - List all galleries
* [create_gallery](docs/sdks/galleries/README.md#create_gallery) - Create a gallery
* [retrieve_gallery](docs/sdks/galleries/README.md#retrieve_gallery) - Retrieve a gallery
* [update_gallery](docs/sdks/galleries/README.md#update_gallery) - Update a gallery
* [partially_update_gallery](docs/sdks/galleries/README.md#partially_update_gallery) - Partially update a gallery
* [delete_gallery](docs/sdks/galleries/README.md#delete_gallery) - Delete a gallery

### [Projects](docs/sdks/projects/README.md)

* [list_projects](docs/sdks/projects/README.md#list_projects) - List all projects
* [create_project](docs/sdks/projects/README.md#create_project) - Create a project
* [retrieve_project](docs/sdks/projects/README.md#retrieve_project) - Retrieve a project
* [update_project](docs/sdks/projects/README.md#update_project) - Update a project
* [partially_update_project](docs/sdks/projects/README.md#partially_update_project) - Partially update a project
* [delete_project](docs/sdks/projects/README.md#delete_project) - Delete a project

### [Token](docs/sdks/token/README.md)

* [obtain_token](docs/sdks/token/README.md#obtain_token) - Obtain JWT token
* [refresh_token](docs/sdks/token/README.md#refresh_token) - Refresh JWT token

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries. If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API. However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a `RetryConfig` object to the call:
```python
from fstop import Fstop
from fstop.utils import BackoffStrategy, RetryConfig
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.list_bookings(,
        RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False))

    # Handle response
    print(res)

```

If you'd like to override the default retry strategy for all operations that support retries, you can use the `retry_config` optional parameter when initializing the SDK:
```python
from fstop import Fstop
from fstop.utils import BackoffStrategy, RetryConfig
import os


with Fstop(
    retry_config=RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False),
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.list_bookings()

    # Handle response
    print(res)

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`FstopError`](./src/fstop/errors/fstoperror.py) is the base class for all HTTP error responses. It has the following properties:

| Property           | Type             | Description                                                                             |
| ------------------ | ---------------- | --------------------------------------------------------------------------------------- |
| `err.message`      | `str`            | Error message                                                                           |
| `err.status_code`  | `int`            | HTTP response status code eg `404`                                                      |
| `err.headers`      | `httpx.Headers`  | HTTP response headers                                                                   |
| `err.body`         | `str`            | HTTP body. Can be empty string if no body is returned.                                  |
| `err.raw_response` | `httpx.Response` | Raw HTTP response                                                                       |
| `err.data`         |                  | Optional. Some errors may contain structured data. [See Error Classes](#error-classes). |

### Example
```python
from fstop import Fstop, errors
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:
    res = None
    try:

        res = f_client.bookings.list_bookings()

        # Handle response
        print(res)


    except errors.FstopError as e:
        # The base class for HTTP error responses
        print(e.message)
        print(e.status_code)
        print(e.body)
        print(e.headers)
        print(e.raw_response)

        # Depending on the method different errors may be thrown
        if isinstance(e, errors.UnauthorizedError):
            print(e.data.detail)  # Optional[str]
```

### Error Classes
**Primary errors:**
* [`FstopError`](./src/fstop/errors/fstoperror.py): The base class for HTTP error responses.
  * [`UnauthorizedError`](./src/fstop/errors/unauthorizederror.py): Serializer for 401 Unauthorized responses.

<details><summary>Less common errors (7)</summary>

<br />

**Network errors:**
* [`httpx.RequestError`](https://www.python-httpx.org/exceptions/#httpx.RequestError): Base class for request errors.
    * [`httpx.ConnectError`](https://www.python-httpx.org/exceptions/#httpx.ConnectError): HTTP client was unable to make a request to a server.
    * [`httpx.TimeoutException`](https://www.python-httpx.org/exceptions/#httpx.TimeoutException): HTTP request timed out.


**Inherit from [`FstopError`](./src/fstop/errors/fstoperror.py)**:
* [`NotFoundError`](./src/fstop/errors/notfounderror.py): Serializer for 404 Not Found responses. Status code `404`. Applicable to 16 of 26 methods.*
* [`BadRequestError`](./src/fstop/errors/badrequesterror.py): Serializer for 400 Bad Request responses. Status code `400`. Applicable to 12 of 26 methods.*
* [`ResponseValidationError`](./src/fstop/errors/responsevalidationerror.py): Type mismatch between the response data and the expected Pydantic model. Provides access to the Pydantic validation error via the `cause` attribute.

</details>

\* Check [the method documentation](#available-resources-and-operations) to see if the error is applicable.
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally by passing a URL to the `server_url: str` optional parameter when initializing the SDK client instance. For example:
```python
from fstop import Fstop
import os


with Fstop(
    server_url="https://fstop.photo",
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.bookings.list_bookings()

    # Handle response
    print(res)

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The Python SDK makes API calls using the [httpx](https://www.python-httpx.org/) HTTP library.  In order to provide a convenient way to configure timeouts, cookies, proxies, custom headers, and other low-level configuration, you can initialize the SDK client with your own HTTP client instance.
Depending on whether you are using the sync or async version of the SDK, you can pass an instance of `HttpClient` or `AsyncHttpClient` respectively, which are Protocol's ensuring that the client has the necessary methods to make API calls.
This allows you to wrap the client with your own custom logic, such as adding custom headers, logging, or error handling, or you can just pass an instance of `httpx.Client` or `httpx.AsyncClient` directly.

For example, you could specify a header for every request that this sdk makes as follows:
```python
from fstop import Fstop
import httpx

http_client = httpx.Client(headers={"x-custom-header": "someValue"})
s = Fstop(client=http_client)
```

or you could wrap the client with your own custom logic:
```python
from fstop import Fstop
from fstop.httpclient import AsyncHttpClient
import httpx

class CustomClient(AsyncHttpClient):
    client: AsyncHttpClient

    def __init__(self, client: AsyncHttpClient):
        self.client = client

    async def send(
        self,
        request: httpx.Request,
        *,
        stream: bool = False,
        auth: Union[
            httpx._types.AuthTypes, httpx._client.UseClientDefault, None
        ] = httpx.USE_CLIENT_DEFAULT,
        follow_redirects: Union[
            bool, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
    ) -> httpx.Response:
        request.headers["Client-Level-Header"] = "added by client"

        return await self.client.send(
            request, stream=stream, auth=auth, follow_redirects=follow_redirects
        )

    def build_request(
        self,
        method: str,
        url: httpx._types.URLTypes,
        *,
        content: Optional[httpx._types.RequestContent] = None,
        data: Optional[httpx._types.RequestData] = None,
        files: Optional[httpx._types.RequestFiles] = None,
        json: Optional[Any] = None,
        params: Optional[httpx._types.QueryParamTypes] = None,
        headers: Optional[httpx._types.HeaderTypes] = None,
        cookies: Optional[httpx._types.CookieTypes] = None,
        timeout: Union[
            httpx._types.TimeoutTypes, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
        extensions: Optional[httpx._types.RequestExtensions] = None,
    ) -> httpx.Request:
        return self.client.build_request(
            method,
            url,
            content=content,
            data=data,
            files=files,
            json=json,
            params=params,
            headers=headers,
            cookies=cookies,
            timeout=timeout,
            extensions=extensions,
        )

s = Fstop(async_client=CustomClient(httpx.AsyncClient()))
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Resource Management [resource-management] -->
## Resource Management

The `Fstop` class implements the context manager protocol and registers a finalizer function to close the underlying sync and async HTTPX clients it uses under the hood. This will close HTTP connections, release memory and free up other resources held by the SDK. In short-lived Python programs and notebooks that make a few SDK method calls, resource management may not be a concern. However, in longer-lived programs, it is beneficial to create a single SDK instance via a [context manager][context-manager] and reuse it across the application.

[context-manager]: https://docs.python.org/3/reference/datamodel.html#context-managers

```python
from fstop import Fstop
import os
def main():

    with Fstop(
        jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
    ) as f_client:
        # Rest of application here...


# Or when using async:
async def amain():

    async with Fstop(
        jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
    ) as f_client:
        # Rest of application here...
```
<!-- End Resource Management [resource-management] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass your own logger class directly into your SDK.
```python
from fstop import Fstop
import logging

logging.basicConfig(level=logging.DEBUG)
s = Fstop(debug_logger=logging.getLogger("fstop"))
```

You can also enable a default debug logger by setting an environment variable `FSTOP_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=fstop&utm_campaign=python)
