# github-api-connectors

## Description

This sample contains multiple pre-built [Linx](https://linx.software) functions which allow you to quickly connect and make HTTP requests the [GitHub REST API](https://docs.github.com/en/rest). These 'connector' functions have been built and tested to handle to the specifics of interacting with the various GitHub API methods and resources. You can copy and use these functions in your own Linx Solution to accelerate development. 


The goal of this Linx Solution is to ultimately include custom built connector functions for all the methods of the GitHub API specified [here](https://docs.github.com/en/rest/reference). 

For a full list of the current connector functions contained in the sample, take a look at the [wiki](https://github.com/linx-software/github-api-connectors/wiki).

## Installation

### Install Linx

1. Install the Linx Designer, download it [here](https://linx.software/).
2. Open the sample Solution (.lsoz) in your Linx Designer.

### Copy and paste the connector functions

1. Right-click on the **GitHubAPI** folder in the Solution Explorer.
3. Select **Copy**.
4. Open your own Solution.
5. Right-click on your Solution Explorer and click **Paste**.
4. A validation error will occur referencing the missing Solution setting values.
5. Copy and paste the setting names and values from the Sample solution into your own Solution.
6. The validation messages will dissapear and you can now drag the required connector functions into your own custom functions.


### Generate your access token

Authentication of requests is achieved via access tokens, the functions take in the "access token" used in the request as an input parameter at runtime, which is then added to the header of the request. 

This "access token" needs to be passed in to each function by you, this could be retrieved from a database, file or external service. 

You're able to generate and retrieve your token from an external authentication service or, alternatively, you're able to host your own Linx authentication service with the [linx-oauth-token-service](https://github.com/linx-software/linx-oauth2-token-service) project on GitHub. 


## Using the connector functions

This sample contains generic "connector" functions which can be imported and used in your own Linx Solution.

For a full list of the implemented methods, have a look at the [wiki](https://github.com/linx-software/github-api-connectors/wiki).
 
Each connector function in the Solution follows the below structure:
- Takes in an "access token" value as an input parameter.
- Takes in any data used for the request parameters such as query, path or requestBody values.
- Removed any empty fields and transforms the inputs into a JSON string.
- Makes a HTTP request to the API and returns a string response.
- The response body string is then parsed using a JSON reader.
- The content of the response body is then returned from the function as the result object type.

These functions do not persist any data and only return or send data that is received at runtime, therefore you must add your own data persistence layer if required.

## Automated tests

A 'Tests' project has been included in the sample Linx Solution to demonstrate the usage of the connector functions. This 'Tests' project contains custom built functions which execute some of the connector function's related to the different areas of the GitHub API as a demonstration. These automated tests will result in mock data being pushed and retrieved from your instance of GitHub. The 'access token' needed for the functions are passed in from a Solution Setting value which you can update with your access token to run the tests.

## Extending the sample

If there are specific GitHub API operations that you would like to see in the sample, contact support@linx.software.

For questions and issues please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 


## License



