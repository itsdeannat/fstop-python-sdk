# ClientCreate

Serializer for creating clients - excludes read-only fields (id, created_at)


## Fields

| Field                              | Type                               | Required                           | Description                        |
| ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- |
| `first_name`                       | *str*                              | :heavy_check_mark:                 | Client's first name                |
| `last_name`                        | *str*                              | :heavy_check_mark:                 | Client's last name                 |
| `city`                             | *str*                              | :heavy_check_mark:                 | City where client is located       |
| `state`                            | *str*                              | :heavy_check_mark:                 | State abbreviation (e.g., CA, NY)  |
| `zip_code`                         | *str*                              | :heavy_check_mark:                 | Postal code for client's address   |
| `email`                            | *str*                              | :heavy_check_mark:                 | Client's email address for contact |
| `phone_number`                     | *str*                              | :heavy_check_mark:                 | Client's phone number              |