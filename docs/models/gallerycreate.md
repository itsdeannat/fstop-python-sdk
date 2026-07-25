# GalleryCreate

Serializer for creating galleries - excludes read-only fields (id, project, created_at)


## Fields

| Field                                   | Type                                    | Required                                | Description                             |
| --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- |
| `project_id`                            | *str*                                   | :heavy_check_mark:                      | UUID of the project for this gallery    |
| `gallery_name`                          | *str*                                   | :heavy_check_mark:                      | Name of the gallery                     |
| `picture_count`                         | *int*                                   | :heavy_check_mark:                      | Number of pictures in the gallery       |
| `is_visible`                            | *bool*                                  | :heavy_check_mark:                      | Whether the gallery is publicly visible |
| `url`                                   | *str*                                   | :heavy_check_mark:                      | URL link to the gallery                 |