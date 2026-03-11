# RecommendationsVisibility

The visibility of this hub in recommendations:
  - all: Visible to all users
  - none: Visible to no users
  - admin: Visible to only admin users
  - shared: Visible to shared users


## Example Usage

```python
from plex_api_client.models.operations import RecommendationsVisibility

value = RecommendationsVisibility.ALL
```


## Values

| Name     | Value    |
| -------- | -------- |
| `ALL`    | all      |
| `NONE`   | none     |
| `ADMIN`  | admin    |
| `SHARED` | shared   |