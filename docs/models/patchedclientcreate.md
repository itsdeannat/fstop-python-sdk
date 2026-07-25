# PatchedClientCreate

Serializer for creating clients - excludes read-only fields (id, created_at)


## Fields

| Field                              | Type                               | Required                           | Description                        |
| ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- |
| `first_name`                       | *Optional[str]*                    | :heavy_minus_sign:                 | Client's first name                |
| `last_name`                        | *Optional[str]*                    | :heavy_minus_sign:                 | Client's last name                 |
| `city`                             | *Optional[str]*                    | :heavy_minus_sign:                 | City where client is located       |
| `state`                            | *Optional[str]*                    | :heavy_minus_sign:                 | State abbreviation (e.g., CA, NY)  |
| `zip_code`                         | *Optional[str]*                    | :heavy_minus_sign:                 | Postal code for client's address   |
| `email`                            | *Optional[str]*                    | :heavy_minus_sign:                 | Client's email address for contact |
| `phone_number`                     | *Optional[str]*                    | :heavy_minus_sign:                 | Client's phone number              |