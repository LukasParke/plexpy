# ProcessingState

The state of processing if this generator is part of an optimizer playlist

## Example Usage

```python
from plex_api_client.models.operations import ProcessingState

value = ProcessingState.PROCESSED
```


## Values

| Name         | Value        |
| ------------ | ------------ |
| `PROCESSED`  | processed    |
| `COMPLETED`  | completed    |
| `TOMBSTONED` | tombstoned   |
| `DISABLED`   | disabled     |
| `ERROR`      | error        |
| `PENDING`    | pending      |