# Plex

## Overview

Plex Plex operations

### Available Operations

* [get_server_resources](#get_server_resources) - Get Server Resources

## get_server_resources

Get Plex server access tokens and server connections

### Example Usage

<!-- UsageSnippet language="python" operationID="getServerResources" method="get" path="/resources" -->
```python
from plex_api_client import PlexAPI
from plex_api_client.models import components, operations


with PlexAPI(
    accepts=components.Accepts.APPLICATION_XML,
    client_identifier="abc123",
    token="<YOUR_API_KEY_HERE>",
) as plex_api:

    res = plex_api.plex.get_server_resources(request={
        "include_https": operations.IncludeHTTPS.TRUE,
        "include_relay": operations.IncludeRelay.TRUE,
        "include_i_pv6": operations.IncludeIPv6.TRUE,
    })

    assert res.plex_devices is not None

    # Handle response
    print(res.plex_devices)

```

### Parameters

| Parameter                                                                                    | Type                                                                                         | Required                                                                                     | Description                                                                                  |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `request`                                                                                    | [operations.GetServerResourcesRequest](../../models/operations/getserverresourcesrequest.md) | :heavy_check_mark:                                                                           | The request object to use for the request.                                                   |
| `retries`                                                                                    | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                             | :heavy_minus_sign:                                                                           | Configuration to override the default retry behavior of the client.                          |
| `server_url`                                                                                 | *Optional[str]*                                                                              | :heavy_minus_sign:                                                                           | An optional server URL to use.                                                               |

### Response

**[operations.GetServerResourcesResponse](../../models/operations/getserverresourcesresponse.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| errors.Unauthorized | 401                 | application/json    |
| errors.SDKError     | 4XX, 5XX            | \*/\*               |