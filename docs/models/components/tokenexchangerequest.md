# TokenExchangeRequest


## Fields

| Field                                       | Type                                        | Required                                    | Description                                 |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| `client_identifier`                         | *Optional[str]*                             | :heavy_minus_sign:                          | Unique client identifier                    |
| `jwt`                                       | *Optional[str]*                             | :heavy_minus_sign:                          | JWT token to exchange for a Plex auth token |
| `scope`                                     | *Optional[str]*                             | :heavy_minus_sign:                          | Requested scope for the token               |