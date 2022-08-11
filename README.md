# Azure Pipelines Tasks
![Tasks](/taskbanner.png "Tasks")

## Adopted tasks

This repo is a clone of the official Microsoft Azure Pipeline tasks. I decided it was time to adopt some tasks because [my pr](https://github.com/microsoft/azure-pipelines-tasks/pull/16283) was open for 3 months without any feedback and I needed to updated version.

Not sure how this works with licenses, I'm not trying to infringe anyone. Just looking for a way to start using my updated version of some tasks.

If you're facing the same issue, give me a PR with your changes. Be sure to also change the `make-options.json` file to include your task(s).

```json
{
  ...
  "adoptedTasks": [
      "AzureResourceGroupDeploymentV2",
      "AzureResourceManagerTemplateDeploymentV3"
  ]
}
```

## Overview

This repo contains the tasks that are provided out-of-the-box with Azure Pipelines and Team Foundation Server.

This provides open examples on how we write tasks which will help you write other tasks which can be uploaded to your account or server.  See **Writing Tasks** below.

## Status

|   | Build & Test |
|---|:-----:|
|![Win](docs/res/win_med.png) **Windows**|[![Build & Test][win-build-badge]][win-build]| 
|![macOS](docs/res/apple_med.png) **macOS**|[![Build & Test][macOS-build-badge]][macOS-build]| 
|![Linux](docs/res/linux_med.png) **Linux**|[![Build & Test][linux-build-badge]][linux-build]|

[win-build-badge]: https://dev.azure.com/mseng/PipelineTools/_apis/build/status/azure-pipelines-tasks.ci-windows
[win-build]: https://dev.azure.com/mseng/PipelineTools/_build/latest?definitionId=7634

[macOS-build-badge]: https://dev.azure.com/mseng/PipelineTools/_apis/build/status/azure-pipelines-tasks.ci-macos
[macOS-build]: https://dev.azure.com/mseng/PipelineTools/_build/latest?definitionId=7635

[linux-build-badge]: https://dev.azure.com/mseng/PipelineTools/_apis/build/status/azure-pipelines-tasks.ci-linux
[linux-build]: https://dev.azure.com/mseng/PipelineTools/_build/latest?definitionId=7636

## How to Use Tasks

See the documentation for [Continuous integration and deployment](https://aka.ms/tfbuild).

## Writing Tasks

If you need custom functionality in your build/release, it is usually simpler to use the existing script running tasks such as the PowerShell or Bash tasks.  Writing a new task may be appropriate if you need deeper integration or reusability in many build definitions

Tasks are simply tool runners.  They know how to run MSBuild, VSTest, etc... in a first class way and handle return codes, how to treat std/err out, and how to write timeline records based on expected output.  They also get access to credentials to write back to TFS/Azure Pipelines. 

For uploading custom tasks to Azure Pipelines use the [TFS Cross Platform Command Line utility](https://github.com/Microsoft/tfs-cli).

Tasks can also be deployed with an Azure DevOps extension. See [this tutorial](https://docs.microsoft.com/en-us/vsts/extend/develop/add-build-task) for how to write a custom task and package it inside an extension.

## Contributing

This project welcomes [contributions and suggestions](docs/contribute.md).

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Issues

We accept issue reports both here (file a GitHub issue) and in [Developer Community](https://developercommunity.visualstudio.com/spaces/21/index.html).

Do you think there might be a security issue? Have you been phished or identified a security vulnerability? Please don't report it here - let us know by sending an email to secure@microsoft.com.
