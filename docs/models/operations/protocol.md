# Protocol

Indicates the network streaming protocol to be used for the transcode session: * 'http' - include the file in the http response such as MKV streaming * 'hls' - hls stream (RFC 8216) * 'dash' - dash stream (ISO/IEC 23009-1:2022)


## Example Usage

```python
from plex_api_client.models.operations import Protocol

value = Protocol.HTTP
```


## Values

| Name   | Value  |
| ------ | ------ |
| `HTTP` | http   |
| `HLS`  | hls    |
| `DASH` | dash   |