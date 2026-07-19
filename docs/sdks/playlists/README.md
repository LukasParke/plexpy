# Playlists

## Overview

Plex Playlists operations

### Available Operations

* [delete_playlist_by_rating_key](#delete_playlist_by_rating_key) - Delete Playlist

## delete_playlist_by_rating_key

Delete a playlist.

### Example Usage

<!-- UsageSnippet language="python" operationID="deletePlaylistByRatingKey" method="delete" path="/playlists" -->
```python
from plex_api_client import PlexAPI
from plex_api_client.models import components


with PlexAPI(
    accepts=components.Accepts.APPLICATION_XML,
    client_identifier="abc123",
    product="Plex for Roku",
    version="2.4.1",
    platform="Roku",
    platform_version="4.3 build 1057",
    device="Roku 3",
    model="4200X",
    device_vendor="Roku",
    device_name="Living Room TV",
    marketplace="googlePlay",
    token="<YOUR_API_KEY_HERE>",
) as plex_api:

    res = plex_api.playlists.delete_playlist_by_rating_key(request={
        "rating_key": 499749,
    })

    assert res.success_response is not None

    # Handle response
    print(res.success_response)

```

### Parameters

| Parameter                                                                                                  | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                  | [operations.DeletePlaylistByRatingKeyRequest](../../models/operations/deleteplaylistbyratingkeyrequest.md) | :heavy_check_mark:                                                                                         | The request object to use for the request.                                                                 |
| `retries`                                                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                           | :heavy_minus_sign:                                                                                         | Configuration to override the default retry behavior of the client.                                        |

### Response

**[operations.DeletePlaylistByRatingKeyResponse](../../models/operations/deleteplaylistbyratingkeyresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |