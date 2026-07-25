# PatchedBookingCreate

Serializer for creating bookings - excludes read-only fields (id, project, created_at)


## Fields

| Field                                                                        | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `project_id`                                                                 | *Optional[str]*                                                              | :heavy_minus_sign:                                                           | UUID of the project for this booking                                         |
| `date_`                                                                      | [datetime](https://docs.python.org/3/library/datetime.html#datetime-objects) | :heavy_minus_sign:                                                           | Date of the booking                                                          |
| `time`                                                                       | *Optional[str]*                                                              | :heavy_minus_sign:                                                           | Time of the booking                                                          |
| `duration`                                                                   | *Optional[int]*                                                              | :heavy_minus_sign:                                                           | Booking duration in minutes                                                  |
| `location`                                                                   | *Optional[str]*                                                              | :heavy_minus_sign:                                                           | Booking location                                                             |