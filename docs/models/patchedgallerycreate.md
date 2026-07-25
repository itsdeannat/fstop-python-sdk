# PatchedGalleryCreate

Serializer for creating galleries - excludes read-only fields (id, project, created_at)


## Fields

| Field                                   | Type                                    | Required                                | Description                             |
| --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- |
| `project_id`                            | *Optional[str]*                         | :heavy_minus_sign:                      | UUID of the project for this gallery    |
| `gallery_name`                          | *Optional[str]*                         | :heavy_minus_sign:                      | Name of the gallery                     |
| `picture_count`                         | *Optional[int]*                         | :heavy_minus_sign:                      | Number of pictures in the gallery       |
| `is_visible`                            | *Optional[bool]*                        | :heavy_minus_sign:                      | Whether the gallery is publicly visible |
| `url`                                   | *Optional[str]*                         | :heavy_minus_sign:                      | URL link to the gallery                 |