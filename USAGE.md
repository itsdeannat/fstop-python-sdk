<!-- Start SDK Example Usage [usage] -->
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