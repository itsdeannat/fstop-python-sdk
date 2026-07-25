# Gallery


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `id`                                                                 | *str*                                                                | :heavy_check_mark:                                                   | Unique identifier for the gallery                                    |
| `booking`                                                            | [models.GalleryBooking](../models/gallerybooking.md)                 | :heavy_check_mark:                                                   | Booking associated with this gallery                                 |
| `gallery_name`                                                       | *str*                                                                | :heavy_check_mark:                                                   | Name of the gallery                                                  |
| `picture_count`                                                      | *int*                                                                | :heavy_check_mark:                                                   | Number of pictures in the gallery                                    |
| `is_visible`                                                         | *bool*                                                               | :heavy_check_mark:                                                   | Whether the gallery is publicly visible                              |
| `url`                                                                | *str*                                                                | :heavy_check_mark:                                                   | URL link to the gallery                                              |
| `created_at`                                                         | [date](https://docs.python.org/3/library/datetime.html#date-objects) | :heavy_check_mark:                                                   | Timestamp when gallery was created                                   |