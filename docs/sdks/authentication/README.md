# Authentication

## Overview

Plex Authentication operations

### Available Operations

* [register_device_jwk](#register_device_jwk) - Register Device JWK
* [get_auth_keys](#get_auth_keys) - Get Auth Keys
* [get_auth_nonce](#get_auth_nonce) - Get Auth Nonce
* [exchange_jwt_token](#exchange_jwt_token) - Exchange JWT Token
* [get_claim_token](#get_claim_token) - Get Claim Token
* [get_features](#get_features) - Get Features
* [ping](#ping) - Ping the server
* [create_o_auth_pin](#create_o_auth_pin) - Create OAuth PIN
* [create_legacy_pin](#create_legacy_pin) - Create Legacy PIN
* [link_o_auth_pin](#link_o_auth_pin) - Link OAuth PIN
* [get_server_access_tokens](#get_server_access_tokens) - Get Server Access Tokens
* [get_token_details](#get_token_details) - Get Token Details
* [change_password](#change_password) - Change Password
* [post_users_sign_in_data](#post_users_sign_in_data) - Get User Sign In Data
* [sign_out](#sign_out) - Sign Out
* [switch_home_user](#switch_home_user) - Switch Home User
* [get_o_auth_pin](#get_o_auth_pin) - Get OAuth PIN Status

## register_device_jwk

Register a device public key (JWK) for JWT-based authentication.

### Example Usage

<!-- UsageSnippet language="python" operationID="registerDeviceJWK" method="post" path="/auth/jwk" -->
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

    res = plex_api.authentication.register_device_jwk(request={
        "jwk_registration_request": {
            "jwk": {
                "crv": "string value",
                "kid": "string value",
                "kty": "string value",
                "x": "string value",
            },
        },
    })

    assert res.auth_token_response is not None

    # Handle response
    print(res.auth_token_response)

```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `request`                                                                                  | [operations.RegisterDeviceJWKRequest](../../models/operations/registerdevicejwkrequest.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |
| `retries`                                                                                  | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                           | :heavy_minus_sign:                                                                         | Configuration to override the default retry behavior of the client.                        |
| `server_url`                                                                               | *Optional[str]*                                                                            | :heavy_minus_sign:                                                                         | An optional server URL to use.                                                             |

### Response

**[operations.RegisterDeviceJWKResponse](../../models/operations/registerdevicejwkresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_auth_keys

Get Plex public JWKs for signature verification.

### Example Usage

<!-- UsageSnippet language="python" operationID="getAuthKeys" method="get" path="/auth/keys" -->
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

    res = plex_api.authentication.get_auth_keys(request={})

    assert res.auth_keys_response is not None

    # Handle response
    print(res.auth_keys_response)

```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `request`                                                                      | [operations.GetAuthKeysRequest](../../models/operations/getauthkeysrequest.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |
| `retries`                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)               | :heavy_minus_sign:                                                             | Configuration to override the default retry behavior of the client.            |
| `server_url`                                                                   | *Optional[str]*                                                                | :heavy_minus_sign:                                                             | An optional server URL to use.                                                 |

### Response

**[operations.GetAuthKeysResponse](../../models/operations/getauthkeysresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_auth_nonce

Get a nonce to sign in client JWT authentication flow.

### Example Usage

<!-- UsageSnippet language="python" operationID="getAuthNonce" method="get" path="/auth/nonce" -->
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

    res = plex_api.authentication.get_auth_nonce(request={})

    assert res.auth_nonce_response is not None

    # Handle response
    print(res.auth_nonce_response)

```

### Parameters

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `request`                                                                        | [operations.GetAuthNonceRequest](../../models/operations/getauthnoncerequest.md) | :heavy_check_mark:                                                               | The request object to use for the request.                                       |
| `retries`                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                 | :heavy_minus_sign:                                                               | Configuration to override the default retry behavior of the client.              |
| `server_url`                                                                     | *Optional[str]*                                                                  | :heavy_minus_sign:                                                               | An optional server URL to use.                                                   |

### Response

**[operations.GetAuthNonceResponse](../../models/operations/getauthnonceresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## exchange_jwt_token

Exchange a signed client JWT for a Plex JWT token.

### Example Usage

<!-- UsageSnippet language="python" operationID="exchangeJWTToken" method="post" path="/auth/token" -->
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

    res = plex_api.authentication.exchange_jwt_token(request={
        "token_exchange_request": {
            "client_identifier": "string value",
            "jwt": "string value",
            "scope": "string value",
        },
    })

    assert res.auth_token_response is not None

    # Handle response
    print(res.auth_token_response)

```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `request`                                                                                | [operations.ExchangeJWTTokenRequest](../../models/operations/exchangejwttokenrequest.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |
| `retries`                                                                                | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                         | :heavy_minus_sign:                                                                       | Configuration to override the default retry behavior of the client.                      |
| `server_url`                                                                             | *Optional[str]*                                                                          | :heavy_minus_sign:                                                                       | An optional server URL to use.                                                           |

### Response

**[operations.ExchangeJWTTokenResponse](../../models/operations/exchangejwttokenresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_claim_token

Get a claim token for new server setup.

### Example Usage

<!-- UsageSnippet language="python" operationID="getClaimToken" method="get" path="/claim/token.json" -->
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

    res = plex_api.authentication.get_claim_token(request={})

    assert res.claim_token_response is not None

    # Handle response
    print(res.claim_token_response)

```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `request`                                                                          | [operations.GetClaimTokenRequest](../../models/operations/getclaimtokenrequest.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |
| `retries`                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                   | :heavy_minus_sign:                                                                 | Configuration to override the default retry behavior of the client.                |
| `server_url`                                                                       | *Optional[str]*                                                                    | :heavy_minus_sign:                                                                 | An optional server URL to use.                                                     |

### Response

**[operations.GetClaimTokenResponse](../../models/operations/getclaimtokenresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_features

Get Plex Pass feature flags for the logged-in user.

### Example Usage

<!-- UsageSnippet language="python" operationID="getFeatures" method="get" path="/features" -->
```python
from plex_api_client import PlexAPI


with PlexAPI(
    token="<YOUR_API_KEY_HERE>",
) as plex_api:

    res = plex_api.authentication.get_features()

    assert res.object is not None

    # Handle response
    print(res.object)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |
| `server_url`                                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | An optional server URL to use.                                      |

### Response

**[operations.GetFeaturesResponse](../../models/operations/getfeaturesresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## ping

Health / latency check. No authentication required.

### Example Usage

<!-- UsageSnippet language="python" operationID="ping" method="get" path="/ping" -->
```python
from plex_api_client import PlexAPI


with PlexAPI() as plex_api:

    res = plex_api.authentication.ping()

    assert res.success_response is not None

    # Handle response
    print(res.success_response)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |
| `server_url`                                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | An optional server URL to use.                                      |

### Response

**[operations.PingResponse](../../models/operations/pingresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## create_o_auth_pin

Create a 4-character PIN for device linking via OAuth. The user must visit https://plex.tv/link and enter the PIN to authorize the device.

### Example Usage

<!-- UsageSnippet language="python" operationID="createOAuthPin" method="post" path="/pins" -->
```python
from plex_api_client import PlexAPI
from plex_api_client.models import components, operations


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
) as plex_api:

    res = plex_api.authentication.create_o_auth_pin(security=operations.CreateOAuthPinSecurity(
        client_identifier="<YOUR_API_KEY_HERE>",
    ), request={})

    assert res.object is not None

    # Handle response
    print(res.object)

```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `request`                                                                              | [operations.CreateOAuthPinRequest](../../models/operations/createoauthpinrequest.md)   | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |
| `security`                                                                             | [operations.CreateOAuthPinSecurity](../../models/operations/createoauthpinsecurity.md) | :heavy_check_mark:                                                                     | The security requirements to use for the request.                                      |
| `retries`                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                       | :heavy_minus_sign:                                                                     | Configuration to override the default retry behavior of the client.                    |
| `server_url`                                                                           | *Optional[str]*                                                                        | :heavy_minus_sign:                                                                     | An optional server URL to use.                                                         |

### Response

**[operations.CreateOAuthPinResponse](../../models/operations/createoauthpinresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## create_legacy_pin

Legacy PIN creation (XML).

### Example Usage

<!-- UsageSnippet language="python" operationID="createLegacyPin" method="post" path="/pins.xml" -->
```python
from plex_api_client import PlexAPI


with PlexAPI(
    token="<YOUR_API_KEY_HERE>",
) as plex_api:

    res = plex_api.authentication.create_legacy_pin()

    assert res.body is not None

    # Handle response
    print(res.body)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |
| `server_url`                                                        | *Optional[str]*                                                     | :heavy_minus_sign:                                                  | An optional server URL to use.                                      |

### Response

**[operations.CreateLegacyPinResponse](../../models/operations/createlegacypinresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## link_o_auth_pin

Link a PIN to an account (OAuth completion).

### Example Usage

<!-- UsageSnippet language="python" operationID="linkOAuthPin" method="put" path="/pins/link" -->
```python
from plex_api_client import PlexAPI


with PlexAPI(
    token="<YOUR_API_KEY_HERE>",
) as plex_api:

    res = plex_api.authentication.link_o_auth_pin(request={
        "auth_token": "example",
        "pin": "example",
    })

    assert res.success_response is not None

    # Handle response
    print(res.success_response)

```

### Parameters

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                            | [operations.LinkOAuthPinAuthenticationRequestBody](../../models/operations/linkoauthpinauthenticationrequestbody.md) | :heavy_check_mark:                                                                                                   | The request object to use for the request.                                                                           |
| `retries`                                                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                                     | :heavy_minus_sign:                                                                                                   | Configuration to override the default retry behavior of the client.                                                  |
| `server_url`                                                                                                         | *Optional[str]*                                                                                                      | :heavy_minus_sign:                                                                                                   | An optional server URL to use.                                                                                       |

### Response

**[operations.LinkOAuthPinResponse](../../models/operations/linkoauthpinresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_server_access_tokens

List access tokens for the server.

### Example Usage

<!-- UsageSnippet language="python" operationID="getServerAccessTokens" method="get" path="/server/access_tokens" -->
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

    res = plex_api.authentication.get_server_access_tokens(request={})

    assert res.server_access_tokens_response is not None

    # Handle response
    print(res.server_access_tokens_response)

```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `request`                                                                                          | [operations.GetServerAccessTokensRequest](../../models/operations/getserveraccesstokensrequest.md) | :heavy_check_mark:                                                                                 | The request object to use for the request.                                                         |
| `retries`                                                                                          | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                                   | :heavy_minus_sign:                                                                                 | Configuration to override the default retry behavior of the client.                                |
| `server_url`                                                                                       | *Optional[str]*                                                                                    | :heavy_minus_sign:                                                                                 | An optional server URL to use.                                                                     |

### Response

**[operations.GetServerAccessTokensResponse](../../models/operations/getserveraccesstokensresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_token_details

Get the User data from the provided X-Plex-Token

### Example Usage

<!-- UsageSnippet language="python" operationID="getTokenDetails" method="get" path="/user" -->
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

    res = plex_api.authentication.get_token_details(request={})

    assert res.user_plex_account is not None

    # Handle response
    print(res.user_plex_account)

```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `request`                                                                              | [operations.GetTokenDetailsRequest](../../models/operations/gettokendetailsrequest.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |
| `retries`                                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                       | :heavy_minus_sign:                                                                     | Configuration to override the default retry behavior of the client.                    |
| `server_url`                                                                           | *Optional[str]*                                                                        | :heavy_minus_sign:                                                                     | An optional server URL to use.                                                         |

### Response

**[operations.GetTokenDetailsResponse](../../models/operations/gettokendetailsresponse.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| errors.BadRequest   | 400                 | application/json    |
| errors.Unauthorized | 401                 | application/json    |
| errors.SDKError     | 4XX, 5XX            | \*/\*               |

## change_password

Change or reset the logged-in user's password.

### Example Usage

<!-- UsageSnippet language="python" operationID="changePassword" method="post" path="/users/password" -->
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

    res = plex_api.authentication.change_password(request={})

    assert res.success_response is not None

    # Handle response
    print(res.success_response)

```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `request`                                                                            | [operations.ChangePasswordRequest](../../models/operations/changepasswordrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `retries`                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                     | :heavy_minus_sign:                                                                   | Configuration to override the default retry behavior of the client.                  |
| `server_url`                                                                         | *Optional[str]*                                                                      | :heavy_minus_sign:                                                                   | An optional server URL to use.                                                       |

### Response

**[operations.ChangePasswordResponse](../../models/operations/changepasswordresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## post_users_sign_in_data

Sign in user with username and password and return user data with Plex authentication token

### Example Usage

<!-- UsageSnippet language="python" operationID="postUsersSignInData" method="post" path="/users/signin" -->
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
) as plex_api:

    res = plex_api.authentication.post_users_sign_in_data(request={
        "request_body": {
            "login": "username@email.com",
            "password": "password123",
            "remember_me": True,
            "verification_code": "123456",
        },
    })

    assert res.user_plex_account is not None

    # Handle response
    print(res.user_plex_account)

```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `request`                                                                                      | [operations.PostUsersSignInDataRequest](../../models/operations/postuserssignindatarequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `retries`                                                                                      | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                               | :heavy_minus_sign:                                                                             | Configuration to override the default retry behavior of the client.                            |
| `server_url`                                                                                   | *Optional[str]*                                                                                | :heavy_minus_sign:                                                                             | An optional server URL to use.                                                                 |

### Response

**[operations.PostUsersSignInDataResponse](../../models/operations/postuserssignindataresponse.md)**

### Errors

| Error Type          | Status Code         | Content Type        |
| ------------------- | ------------------- | ------------------- |
| errors.BadRequest   | 400                 | application/json    |
| errors.Unauthorized | 401                 | application/json    |
| errors.SDKError     | 4XX, 5XX            | \*/\*               |

## sign_out

Invalidate the current authentication token.

### Example Usage

<!-- UsageSnippet language="python" operationID="signOut" method="delete" path="/users/signout" -->
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

    res = plex_api.authentication.sign_out(request={})

    assert res.success_response is not None

    # Handle response
    print(res.success_response)

```

### Parameters

| Parameter                                                              | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `request`                                                              | [operations.SignOutRequest](../../models/operations/signoutrequest.md) | :heavy_check_mark:                                                     | The request object to use for the request.                             |
| `retries`                                                              | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)       | :heavy_minus_sign:                                                     | Configuration to override the default retry behavior of the client.    |
| `server_url`                                                           | *Optional[str]*                                                        | :heavy_minus_sign:                                                     | An optional server URL to use.                                         |

### Response

**[operations.SignOutResponse](../../models/operations/signoutresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 4XX, 5XX        | \*/\*           |

## switch_home_user

Switch to a Plex Home user and return a new auth token.

### Example Usage

<!-- UsageSnippet language="python" operationID="switchHomeUser" method="post" path="/home/users/{id}/switch" -->
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

    res = plex_api.authentication.switch_home_user(request={
        "id": 135337,
    })

    assert res.success_response is not None

    # Handle response
    print(res.success_response)

```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `request`                                                                            | [operations.SwitchHomeUserRequest](../../models/operations/switchhomeuserrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `retries`                                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                     | :heavy_minus_sign:                                                                   | Configuration to override the default retry behavior of the client.                  |
| `server_url`                                                                         | *Optional[str]*                                                                      | :heavy_minus_sign:                                                                   | An optional server URL to use.                                                       |

### Response

**[operations.SwitchHomeUserResponse](../../models/operations/switchhomeuserresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |

## get_o_auth_pin

Poll the PIN status. Returns authToken when the user has linked the device.

### Example Usage

<!-- UsageSnippet language="python" operationID="getOAuthPin" method="get" path="/pins/{pinId}" -->
```python
from plex_api_client import PlexAPI
from plex_api_client.models import components, operations


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
) as plex_api:

    res = plex_api.authentication.get_o_auth_pin(security=operations.GetOAuthPinSecurity(
        client_identifier="<YOUR_API_KEY_HERE>",
    ), request={
        "pin_id": 876892,
    })

    assert res.object is not None

    # Handle response
    print(res.object)

```

### Parameters

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `request`                                                                        | [operations.GetOAuthPinRequest](../../models/operations/getoauthpinrequest.md)   | :heavy_check_mark:                                                               | The request object to use for the request.                                       |
| `security`                                                                       | [operations.GetOAuthPinSecurity](../../models/operations/getoauthpinsecurity.md) | :heavy_check_mark:                                                               | The security requirements to use for the request.                                |
| `retries`                                                                        | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)                 | :heavy_minus_sign:                                                               | Configuration to override the default retry behavior of the client.              |
| `server_url`                                                                     | *Optional[str]*                                                                  | :heavy_minus_sign:                                                               | An optional server URL to use.                                                   |

### Response

**[operations.GetOAuthPinResponse](../../models/operations/getoauthpinresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.Error     | 401              | application/json |
| errors.SDKError  | 4XX, 5XX         | \*/\*            |