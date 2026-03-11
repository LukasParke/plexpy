# MediaReviewsVisibility

Whether or not the account has media reviews visibility enabled

## Example Usage

```python
from plex_api_client.models.components import MediaReviewsVisibility

value = MediaReviewsVisibility.NO_ONE
```


## Values

| Name                     | Value                    |
| ------------------------ | ------------------------ |
| `NO_ONE`                 | 0                        |
| `CRITICS_ONLY`           | 1                        |
| `PLEX_USERS_ONLY`        | 2                        |
| `PLEX_USERS_AND_CRITICS` | 3                        |