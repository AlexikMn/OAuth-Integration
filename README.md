# OAuth-Integration

## Introduction

The OAuth Integration Package is a JavaScript library designed to simplify OAuth authentication with various OAuth providers. It provides a convenient interface for generating authorization URLs, exchanging authorization codes for access tokens, and fetching user information using those tokens.

## Installation

You can install the OAuth Integration Package via npm:

```bash
npm install oauth-integration
```

## Usage

```javascript
const OAuthIntegration = require('oauth-integration');

// Initialize OAuthIntegration with your OAuth client credentials
const oauth = new OAuthIntegration(clientId, clientSecret, redirectUri);

// Generate authorization URL for the OAuth provider
const authUrl = await oauth.getAuthorizationUrl(provider, scope);

// Redirect users to authUrl to authenticate

// Exchange authorization code for an access token
const accessToken = await oauth.getAccessToken(provider, code);

// Use the access token to fetch user information
const userInfo = await oauth.getUserInfo(provider, accessToken);
```

## API

### `OAuthIntegration(clientId, clientSecret, redirectUri)`

- `clientId`: OAuth client ID provided by the OAuth provider.
- `clientSecret`: OAuth client secret provided by the OAuth provider.
- `redirectUri`: Redirect URI registered with the OAuth provider for callback after authentication.

### `getAuthorizationUrl(provider, scope)`

Generates an authorization URL for the specified provider and scope.

- `provider`: OAuth provider (e.g., 'google', 'facebook', 'github').
- `scope`: OAuth scope requested for authorization.

### `getAccessToken(provider, code)`

Exchanges an authorization code for an access token.

- `provider`: OAuth provider (e.g., 'google', 'facebook', 'github').
- `code`: Authorization code received after successful authentication.

### `getUserInfo(provider, accessToken)`

Fetches user information using the provided access token.

- `provider`: OAuth provider (e.g., 'google', 'facebook', 'github').
- `accessToken`: Access token obtained after successful authorization.

## Contributing

Contributions are welcome! Please feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
