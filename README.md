# GitHub integeration

## Overview

The provided sample includes:

- Generating GitHub API access tokens via OAuth 2.0.
- Authenticating and connecting to the GitHub API via Linx
- Template requests: Retrieving and sending data to the GitHub API via HTTP requests.

---

### Additional resources

- [GitHub-Linx integration guide](https://community.linx.software/community/t/oauth-2-0-authentication-github-example/487)
- [GitHub API authentication documentation](https://docs.github.com/en/rest)

---

## Dependencies

### Pre-requisites

- Linx Designer
- Salesforce account

### Linx Designer

This solution was developed in the Linx Designer `v5.20.2.0`

---

## Setting up the sample

Register a new app on GitHub:

1. Register a new 'OAuth application' on GitHub
1. Configure the 'Authorization callback URL' to be: `http://localhost:8080/oauth/token`
1. Save your app.
1. Generate your **client secret**.
1. Copy the **Client ID** and **Client Secret**.

Configure the Solution's $.Settings:

1. Open the [sample Solution](Solution.lsoz) in your Linx Designer.
1. Edit the $.Settings values:

   - `client_id`: Your GitHub app’s **Client ID**
   - `client_secret`: Your GitHub app’s **Client Secret**

1. Save the Solution.

Generate access tokens:

1. Start the debugger on the RESTHost service in the Linx Designer.
2. Make a request in your browser to `http://localhost:8080/oauth/authorize`
3. You will be redirected to the GitHub OAuth 2.0 access consent screen.
4. Authorize the connected application.
5. View success message.

---

## Using the sample

### Authentication

After your app has been successfully authorized, the access token is stored in a local text file.

Requests are authenticated via a Bearer access token included in the `Authorization` header of each request.

The token is retrieved from the file before each request is made.

### Making requests

When making requests to the GitHub, you must also include the following header:

```http
User-Agent: Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/47.0.2526.111 YaBrowser/16.3.0.7146 Yowser/2.5 Safari/537.36
```

---

## Template HTTP requests

The following custom functions wrap the different types of HTTP calls into their own re-usable functions which can be thought of as 'custom GitHub connectors'.

---

### GetAuthenticatedUser

Makes a `GET` request to the `/user` endpoint and returns the details of the authenticated user of the request.
