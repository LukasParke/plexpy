# DefaultSubtitleAccessibility

The subtitles for the deaf or hard-of-hearing (SDH) searches mode (0 = Prefer non-SDH subtitles, 1 = Prefer SDH subtitles, 2 = Only show SDH subtitles, 3 = Only show non-SDH subtitles)

## Example Usage

```python
from plex_api_client.models.components import DefaultSubtitleAccessibility

value = DefaultSubtitleAccessibility.PREFER_NON_SDH
```


## Values

| Name             | Value            |
| ---------------- | ---------------- |
| `PREFER_NON_SDH` | 0                |
| `PREFER_SDH`     | 1                |
| `ONLY_SDH`       | 2                |
| `ONLY_NON_SDH`   | 3                |