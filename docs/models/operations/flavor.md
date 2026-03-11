# Flavor

- `0`: The country is divided into regions, and following the key will lead to a list of regions.
- `1`: The county is divided by postal codes, and an example code is returned in `example`.
- `2`: The country has a single postal code, returned in `example`.


## Example Usage

```python
from plex_api_client.models.operations import Flavor

value = Flavor.ZERO
```


## Values

| Name   | Value  |
| ------ | ------ |
| `ZERO` | 0      |
| `ONE`  | 1      |
| `TWO`  | 2      |