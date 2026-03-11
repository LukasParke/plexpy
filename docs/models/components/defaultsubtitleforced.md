# DefaultSubtitleForced

The forced subtitles searches mode (0 = Prefer non-forced subtitles, 1 = Prefer forced subtitles, 2 = Only show forced subtitles, 3 = Only show non-forced subtitles)

## Example Usage

```python
from plex_api_client.models.components import DefaultSubtitleForced

value = DefaultSubtitleForced.PREFER_NON_FORCED
```


## Values

| Name                | Value               |
| ------------------- | ------------------- |
| `PREFER_NON_FORCED` | 0                   |
| `PREFER_FORCED`     | 1                   |
| `ONLY_FORCED`       | 2                   |
| `ONLY_NON_FORCED`   | 3                   |