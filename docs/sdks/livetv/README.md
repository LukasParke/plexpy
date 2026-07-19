# LiveTV

## Overview

LiveTV contains the playback sessions of a channel from a DVR device

### Available Operations

* [get_dvr_recordings](#get_dvr_recordings) - Get DVR Recordings
* [get_sessions](#get_sessions) - Get all sessions
* [get_dvr_recordings_by_dvr](#get_dvr_recordings_by_dvr) - Get DVR Recordings by DVR
* [delete_live_tv_session](#delete_live_tv_session) - Delete Live TV Session
* [get_live_tv_session](#get_live_tv_session) - Get a single session
* [get_session_playlist_index](#get_session_playlist_index) - Get a session playlist index
* [get_session_segment](#get_session_segment) - Get a single session segment

## get_dvr_recordings

List completed DVR recordings.

### Example Usage

<!-- UsageSnippet language="python" operationID="getDVRRecordings" method="get" path="/livetv/recordings" -->
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

    res = plex_api.live_tv.get_dvr_recordings(request={})

    assert res.media_container_with_metadata is not None

    # Handle response
    print(res.media_container_with_metadata)

```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `request`                                                                                | [operations.GetDVRRecordingsRequest](../../models/operations/getdvrrecordingsrequest.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |
| `retries`                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                         | :heavy_minus_sign:                                                                       | Configuration to override the default retry behavior of the client.                      |

### Response

**[operations.GetDVRRecordingsResponse](../../models/operations/getdvrrecordingsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_sessions

Get all livetv sessions and metadata

### Example Usage

<!-- UsageSnippet language="python" operationID="getSessions" method="get" path="/livetv/sessions" -->
```python
from plex_api_client import PlexAPI


with PlexAPI(
    token="<YOUR_API_KEY_HERE>",
) as plex_api:

    res = plex_api.live_tv.get_sessions()

    assert res.media_container_with_metadata is not None

    # Handle response
    print(res.media_container_with_metadata)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `dvr_id`                                                            | *Optional[int]*                                                     | :heavy_minus_sign:                                                  | Filter by DVR ID.                                                   |
| `channel`                                                           | *Optional[int]*                                                     | :heavy_minus_sign:                                                  | Filter by channel ID.                                               |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[operations.GetSessionsResponse](../../models/operations/getsessionsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_dvr_recordings_by_dvr

List completed DVR recordings for a specific DVR.

### Example Usage

<!-- UsageSnippet language="python" operationID="getDVRRecordingsByDVR" method="get" path="/livetv/dvrs/{dvrId}/recordings" -->
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

    res = plex_api.live_tv.get_dvr_recordings_by_dvr(request={
        "dvr_id": 83756,
    })

    assert res.media_container_with_metadata is not None

    # Handle response
    print(res.media_container_with_metadata)

```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `request`                                                                                          | [operations.GetDVRRecordingsByDVRRequest](../../models/operations/getdvrrecordingsbydvrrequest.md) | :heavy_check_mark:                                                                                 | The request object to use for the request.                                                         |
| `retries`                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                   | :heavy_minus_sign:                                                                                 | Configuration to override the default retry behavior of the client.                                |

### Response

**[operations.GetDVRRecordingsByDVRResponse](../../models/operations/getdvrrecordingsbydvrresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## delete_live_tv_session

Terminate a Live TV session.

### Example Usage

<!-- UsageSnippet language="python" operationID="deleteLiveTVSession" method="delete" path="/livetv/sessions/{sessionId}" -->
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

    res = plex_api.live_tv.delete_live_tv_session(request={
        "session_id": "<id>",
    })

    assert res.success_response is not None

    # Handle response
    print(res.success_response)

```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `request`                                                                                      | [operations.DeleteLiveTVSessionRequest](../../models/operations/deletelivetvsessionrequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `retries`                                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                               | :heavy_minus_sign:                                                                             | Configuration to override the default retry behavior of the client.                            |

### Response

**[operations.DeleteLiveTVSessionResponse](../../models/operations/deletelivetvsessionresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_live_tv_session

Get a single livetv session and metadata

### Example Usage

<!-- UsageSnippet language="python" operationID="getLiveTVSession" method="get" path="/livetv/sessions/{sessionId}" -->
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

    res = plex_api.live_tv.get_live_tv_session(request={
        "session_id": "<id>",
    })

    assert res.media_container_with_metadata is not None

    # Handle response
    print(res.media_container_with_metadata)

```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `request`                                                                                | [operations.GetLiveTVSessionRequest](../../models/operations/getlivetvsessionrequest.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |
| `retries`                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                         | :heavy_minus_sign:                                                                       | Configuration to override the default retry behavior of the client.                      |

### Response

**[operations.GetLiveTVSessionResponse](../../models/operations/getlivetvsessionresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_session_playlist_index

Get a playlist index for playing this session

### Example Usage

<!-- UsageSnippet language="python" operationID="getSessionPlaylistIndex" method="get" path="/livetv/sessions/{sessionId}/{consumerId}/index.m3u8" -->
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

    res = plex_api.live_tv.get_session_playlist_index(request={
        "session_id": "<id>",
        "consumer_id": "<id>",
    })

    assert res.binary_response is not None

    # Handle response
    print(res.binary_response)

```

### Parameters

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `request`                                                                                              | [operations.GetSessionPlaylistIndexRequest](../../models/operations/getsessionplaylistindexrequest.md) | :heavy_check_mark:                                                                                     | The request object to use for the request.                                                             |
| `retries`                                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                       | :heavy_minus_sign:                                                                                     | Configuration to override the default retry behavior of the client.                                    |

### Response

**[operations.GetSessionPlaylistIndexResponse](../../models/operations/getsessionplaylistindexresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 4XX, 5XX        | \*/\*           |

## get_session_segment

Get a single LiveTV session segment

### Example Usage

<!-- UsageSnippet language="python" operationID="getSessionSegment" method="get" path="/livetv/sessions/{sessionId}/{consumerId}/{segmentId}" -->
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

    res = plex_api.live_tv.get_session_segment(request={
        "session_id": "<id>",
        "consumer_id": "<id>",
        "segment_id": "<id>",
    })

    assert res.binary_response is not None

    # Handle response
    print(res.binary_response)

```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `request`                                                                                  | [operations.GetSessionSegmentRequest](../../models/operations/getsessionsegmentrequest.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |
| `retries`                                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                           | :heavy_minus_sign:                                                                         | Configuration to override the default retry behavior of the client.                        |

### Response

**[operations.GetSessionSegmentResponse](../../models/operations/getsessionsegmentresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 4XX, 5XX        | \*/\*           |