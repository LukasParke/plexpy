# Provider

A media provider registered with the PMS.


## Fields

| Field                                  | Type                                   | Required                               | Description                            | Example                                |
| -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- |
| `title`                                | *Optional[str]*                        | :heavy_minus_sign:                     | Human-readable provider title.         | Plex VOD                               |
| `identifier`                           | *Optional[str]*                        | :heavy_minus_sign:                     | Unique provider identifier.            | tv.plex.provider.vod                   |
| `protocol`                             | *Optional[str]*                        | :heavy_minus_sign:                     | Protocol version used by the provider. | 1.0                                    |
| `types`                                | *Optional[str]*                        | :heavy_minus_sign:                     | Content types provided.                | movie,show                             |