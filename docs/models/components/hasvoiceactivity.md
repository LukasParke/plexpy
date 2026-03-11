# HasVoiceActivity

Voice activity detection availability flag returned by PMS.
PMS returns this as string values (`"0"` or `"1"`) instead of a JSON boolean.


## Example Usage

```python
from plex_api_client.models.components import HasVoiceActivity

value = HasVoiceActivity.FALSE
```


## Values

| Name    | Value   |
| ------- | ------- |
| `FALSE` | 0       |
| `TRUE`  | 1       |