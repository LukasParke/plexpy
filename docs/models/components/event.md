# Event

Event type that triggered the webhook.

## Example Usage

```python
from plex_api_client.models.components import Event

value = Event.MEDIA_PLAY
```


## Values

| Name              | Value             |
| ----------------- | ----------------- |
| `MEDIA_PLAY`      | media.play        |
| `MEDIA_PAUSE`     | media.pause       |
| `MEDIA_RESUME`    | media.resume      |
| `MEDIA_STOP`      | media.stop        |
| `MEDIA_SCROBBLE`  | media.scrobble    |
| `MEDIA_RATE`      | media.rate        |
| `LIBRARY_NEW`     | library.new       |
| `LIBRARY_ON_DECK` | library.on.deck   |