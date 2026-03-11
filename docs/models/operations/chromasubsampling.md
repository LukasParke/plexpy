# ChromaSubsampling

Use the specified chroma subsambling.
  - 0: 411
  - 1: 420
  - 2: 422
  - 3: 444
Defaults to 3 (444)

## Example Usage

```python
from plex_api_client.models.operations import ChromaSubsampling

value = ChromaSubsampling.ZERO
```


## Values

| Name    | Value   |
| ------- | ------- |
| `ZERO`  | 0       |
| `ONE`   | 1       |
| `TWO`   | 2       |
| `THREE` | 3       |