# Token

## Overview

### Available Operations

* [obtain_token](#obtain_token) - Obtain JWT token
* [refresh_token](#refresh_token) - Refresh JWT token

## obtain_token

Authenticate and obtain access and refresh tokens.

### Example Usage

<!-- UsageSnippet language="python" operationID="obtain_token" method="post" path="/api/token/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.token.obtain_token(username="Watson_Flatley", password="Od4r0DaNO_D8IXK")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `username`                                                          | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `password`                                                          | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.ObtainTokenResponse](../../models/obtaintokenresponse.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 400                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |

## refresh_token

Refresh an expired access token using a refresh token.

### Example Usage

<!-- UsageSnippet language="python" operationID="refresh_token" method="post" path="/api/token/refresh/" -->
```python
from fstop import Fstop
import os


with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    res = f_client.token.refresh_token(refresh="<value>")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `refresh`                                                           | *str*                                                               | :heavy_check_mark:                                                  | N/A                                                                 |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.RefreshTokenResponse](../../models/refreshtokenresponse.md)**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.UnauthorizedError | 400                      | application/json         |
| errors.FstopDefaultError | 4XX, 5XX                 | \*/\*                    |