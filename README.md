# github-api-connectors

## Description

Managing the different aspects of your GitHub instance can become a overwhelming task with the various flows and procedures that typically happen when working in teams on multiple development projects. 

Using [Linx](https://linx.software) and the [GitHub REST API](https://docs.github.com/en/rest), you're able to automate many of your existing tasks and devops on GitHub such as retrieving commit history, updating resources or triggering other external tasks and events based on GitHub activity.

This sample contains multiple functions which allow you to connect and make HTTP requests to the different resources on the GitHub API. These 'connector' functions have been built and tested to handle to the specifics of interacting with the various GitHub API methods and objects. 

The goal of this Linx Solution is to ultimately include custom built connector functions for all the methods of the GitHub API specified [here](https://docs.github.com/en/rest/reference). For a full list of the current connector functions contained in the sample, take a look at the [wiki](https://github.com/linx-software/github-api-connectors/wiki).

---
## Installation

1. Install the Linx Designer. Download it [here.](https://linx.software)
2. Open the sample Solution 'GitHubConnectors.lsoz' in your Linx Designer.
2. Right-click on the **GitHub** folder in the Solution Explorer.
3. Select **Copy**.
4. Open your own Solution.
5. Right-click on your Solution Explorer and click **Paste**.
4. A validation error will occur referencing a missing setting value, to resolve this error, add the below as $.Setting to your Solution:
   - Name: `GitHubApiBaseUri`
   - Value: `https://api.github.com`  
1. **Save** your Solution.

You can now drag the required connector functions into your own custom functions.

---

## Using the connector functions

This sample contains generic "connector" functions which can be imported and used in your own Linx Solution.
 
Each connector function in the Solution follows the below structure:
- Takes in an `access token` as an input parameter.
- Takes in any data used for the request parameters such as query, path or requestBody values.
- Makes a HTTP request to the API and returns a string response.
- The response string is then de-serialized into the function result object type.

For more technical details on the specific functions and Solution architecture take a look at the [wiki](https://github.com/linx-software/github-api-connectors/wiki).

These functions do not persist any data and only return or send data that is received at runtime, therefore you must add your own data persistence layer if required.

Authentication of requests is achieved via access tokens, the functions take in the `access_token` used in the request as an input parameter which is then added to the header of the request. This 'access token' needs to be passed in to each function by you, this could be retrieved from a database, file or external service. 

You're able to generate and retrieve your token from an external authentication service or, alternatively, you're able to host your own Linx authentication service which generates the access tokens and stores them locally on your environment for later retrieval.


## Contributing

For questions and issues please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)


