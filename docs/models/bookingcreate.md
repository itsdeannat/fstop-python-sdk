# BookingCreate

Serializer for creating bookings - excludes read-only fields (id, project, created_at)


## Fields

| Field                                                                        | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `project_id`                                                                 | *str*                                                                        | :heavy_check_mark:                                                           | UUID of the project for this booking                                         |
| `date_`                                                                      | [datetime](https://docs.python.org/3/library/datetime.html#datetime-objects) | :heavy_check_mark:                                                           | Date of the booking                                                          |
| `time`                                                                       | *str*                                                                        | :heavy_check_mark:                                                           | Time of the booking                                                          |
| `duration`                                                                   | *int*                                                                        | :heavy_check_mark:                                                           | Booking duration in minutes                                                  |
| `location`                                                                   | *str*                                                                        | :heavy_check_mark:                                                           | Booking location                                                             |