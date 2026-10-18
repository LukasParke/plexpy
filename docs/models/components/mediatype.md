# MediaType

The type of media to retrieve or filter by.

1 = movie
2 = show
3 = season
4 = episode
5 = trailer
7 = person
8 = artist
9 = album
10 = track
12 = clip
13 = photo
14 = photoalbum
15 = playlist
16 = playlistfolder
18 = collection

E.g. A movie library will not return anything with type 3 as there are no seasons for movie libraries

## Example Usage

```python
from plex_api_client.models.components import MediaType

value = MediaType.MOVIE
```


## Values

| Name              | Value             |
| ----------------- | ----------------- |
| `MOVIE`           | 1                 |
| `TV_SHOW`         | 2                 |
| `SEASON`          | 3                 |
| `EPISODE`         | 4                 |
| `TRAILER`         | 5                 |
| `PERSON`          | 7                 |
| `ARTIST`          | 8                 |
| `ALBUM`           | 9                 |
| `TRACK`           | 10                |
| `CLIP`            | 12                |
| `PHOTO`           | 13                |
| `PHOTO_ALBUM`     | 14                |
| `PLAYLIST`        | 15                |
| `PLAYLIST_FOLDER` | 16                |
| `COLLECTION`      | 18                |