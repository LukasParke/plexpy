# WatchedIndicator

Whether or not media watched indicators are enabled (little orange dot on media)

## Example Usage

```python
from plex_api_client.models.components import WatchedIndicator

value = WatchedIndicator.NONE
```


## Values

| Name                  | Value                 |
| --------------------- | --------------------- |
| `NONE`                | 0                     |
| `MOVIES_AND_TV_SHOWS` | 1                     |
| `MOVIES`              | 2                     |
| `TV_SHOWS`            | 3                     |