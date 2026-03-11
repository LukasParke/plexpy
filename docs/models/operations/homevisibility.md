# HomeVisibility

Whether this hub is visible on the home screen
  - all: Visible to all users
  - none: Visible to no users
  - admin: Visible to only admin users
  - shared: Visible to shared users


## Example Usage

```python
from plex_api_client.models.operations import HomeVisibility

value = HomeVisibility.ALL
```


## Values

| Name     | Value    |
| -------- | -------- |
| `ALL`    | all      |
| `NONE`   | none     |
| `ADMIN`  | admin    |
| `SHARED` | shared   |