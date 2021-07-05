# GitHub API integration template

## Description
Integration template connecting Linx to the GitHub API.


## Installation
### Pre-requisites

- Linx Designer
- GitHub OAuth 2.0 access token



### Configure your Solution

1. Open the your Solution in your Linx Designer.
1. Add the below *$.Settings* value:

   | Name | Type | Value  
   | --- | --- | --- 
   | `GitHubApiBaseUri` |  string | `https://api.github.com` | 


1. **Save** the Solution.


### Import the sample functions into your Solution 

1. Open the sample Solution in your Linx Designer.
2. Right-click on the 'GitHub' folder in the Solution Explorer.
3. Select **Copy**.
4. Open your own Solution.
5. Right-click on your Solution Explorer and click **Paste**.


## Usage

### Get the details of authenticated user

Retrieve the details of the user associated with the access token.

1. Debug or drag the *GetAuthenticatedUser* function in your own function.
1. Add your GitHub `access_token` as the input parameter.
2. Run the function.
3. View the details of the authenticated user as the result of the function.

### Get a list of repositories

Retrieve a list of repositories for the authroized user.
1. Debug or drag the *GetRepos* function in your own function.
1. Add your GitHub `access_token` as the input parameter.
2. Add your repository owner name in the input parameter.
3. Run the function.
3. View the list of repository details as the result of the function.


### Get a list of commits for a repo

Retrieve a list of recent commit activity for a chosen repo based on a date filter.

1. Debug or drag the *GetCommitHistoryForRepo* function in your own function.
1. Add your GitHub `access_token` as the input parameter.
2. Add your repository owner name in the input parameter.
1. Configure the 'since' and 'until' input parameters with your chosen dates.
3. Run the function.
3. View the list of commit details as the result of the function.


## Contributing

If you'd like to extend this sample, get in touch with support@linx.software.

For questions please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)


