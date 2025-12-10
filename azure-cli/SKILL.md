---
name: Azure DevOps CLI
description: When users share links (such as visualstudio.com or dev.azure.com) and/or mention Azure DevOps, use the Azure DevOps CLI to interact with work items, pull requests (PRs), repositories, and more.
---

# Azure DevOps CLI

You have access to an already signed in version of the Azure CLI with devops access (other functionality may be limited). When users share links to work items, pull requests, repositories, or other Azure DevOps resources, you can use the Azure DevOps CLI to interact with those resources.

The Azure CLI does not always have first-class commands for every Azure DevOps resource, so you may need to use the `az devops invoke` command to call specific REST API endpoints.

## Invoke Example: Getting PR Comment Threads

When a user shares a link to a pull request in Azure DevOps, run the following command to get comment threads:

```shell
az devops invoke --area git --resource pullRequestThreads --route-parameters project={project} repositoryId={repository} pullRequestId={prId} --org {orgUrl} --api-version 7.1
```

You can modify the command as needed for additional filtering (limit to active comments) or leverage `jq` for processing the JSON response.
