# BookingClient

Details of the client associated with this project


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `id`                                                                 | *str*                                                                | :heavy_check_mark:                                                   | Unique identifier for the client                                     |
| `first_name`                                                         | *str*                                                                | :heavy_check_mark:                                                   | Client's first name                                                  |
| `last_name`                                                          | *str*                                                                | :heavy_check_mark:                                                   | Client's last name                                                   |
| `city`                                                               | *str*                                                                | :heavy_check_mark:                                                   | City where client is located                                         |
| `state`                                                              | *str*                                                                | :heavy_check_mark:                                                   | State abbreviation (e.g., CA, NY)                                    |
| `zip_code`                                                           | *str*                                                                | :heavy_check_mark:                                                   | Postal code for client's address                                     |
| `email`                                                              | *str*                                                                | :heavy_check_mark:                                                   | Client's email address for contact                                   |
| `phone_number`                                                       | *str*                                                                | :heavy_check_mark:                                                   | Client's phone number                                                |
| `created_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | Timestamp when client was created                                    |