# Fstop Python SDK

The Fstop Python SDK is a Python client for the fictional Fstop API, built as part of [Beyond the Docs](https://beyond-the-docs.netlify.app/).

The SDK was automatically generated from the Fstop API's OpenAPI specification using [Speakeasy](https://www.speakeasy.com/).

> **⚠️ Project status:** This SDK is a learning project and is not production-ready. The Fstop API is not publicly deployed, and the SDK examples in this documentation have not been comprehensively tested against a running API. **Don't use this SDK in a production application.**

## What can you do with the SDK?

The SDK provides Python methods for interacting with Fstop resources, including:

* **Clients**
* **Projects**
* **Galleries**
* **Bookings**
* **Authentication**

## Installation

The SDK is currently intended for experimentation with the Fstop API and is not published as a production package.

Installation and packaging are future tasks for the project.

## Example 

```python
from fstop import Fstop
import os

with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:

    response = f_client.projects.list_projects()

    print(response)
```

> **Important:** SDK examples are provided for demonstration purposes. They have not been comprehensively tested against a running Fstop API and may not work as written.

## Authentication

The SDK currently supports JWT authentication.

Authentication credentials are provided when initializing the SDK client:

```python
from fstop import Fstop
import os

with Fstop(
    jwt_auth=os.getenv("FSTOP_JWT_AUTH", ""),
) as f_client:
    # Make API requests here
    ...
```

Credentials should be stored securely and should not be committed to source control.

## About Beyond the Docs

Beyond the Docs is a hands-on project where I built an ecosystem of developer tools to understand how they work and how the technical decisions behind them shape the developer and documentation experience.

[Read the full project story](https://beyond-the-docs.netlify.app/)

