---
title: Install Power Apps CLI | Microsoft Docs
description: "Get the Microsoft Power Apps CLI to create, debug, and deploy code components using Power Apps component framework."
keywords: Power Apps CLI, code components, component framework, CLI
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 01/28/2020
ms.service: "powerapps"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f393f227-7a88-4f25-9036-780b3bf14070
---

# What is Microsoft Power Apps CLI? 

Microsoft Power Apps CLI is a simple, single-stop developer command-line interface that empowers developers and app makers to create code components. 

Power Apps CLI tooling is the first step toward a comprehensive application life cycle management (ALM) story where the enterprise developers and ISVs can create, build, debug, and publish their extensions and customizations quickly and efficiently.  

## Install Power Apps CLI

To get Power Apps CLI, do the following:

1. Install [Npm](https://www.npmjs.com/get-npm) (comes with Node.js) or [Node.js](https://nodejs.org/en/) (comes with npm). We recommend LTS (Long Term Support) version 10.15.3 or higher.

1. Install [.NET Framework 4.6.2 Developer Pack](https://dotnet.microsoft.com/download/dotnet-framework/net462). 

1. If you don’t already have Visual Studio 2017 or later, follow one of these options:
   - Option 1: Install [Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2017) or later.
   - Option 2: Install [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/current) and then install [Visual Studio Code](https://code.visualstudio.com/Download).

1. Install [Power Apps CLI](https://aka.ms/PowerAppsCLI).

1. To take advantage of all the latest capabilities, update the Power Apps CLI tooling to the latest version using this command:

    ```CLI
    pac install latest
    ```

> [!NOTE]
> Currently, Power Apps CLI is supported only on Windows 10.

## Common commands

This table lists some common commands used in the CLI:

|Command|Description|Examples|
|------|-----------|--------|
|**pcf**|Commands for working with [Power Apps component framework](/powerapps/developer/component-framework/overview). It has the following parameters: <br/> - **init**: Initializes the code component project. It has the following parameters <br/> - *namespace*: Namespace of the code component. <br/> - *name*: Name of the code component. <br/> - *template*: Field or dataset <br/> - **push**: Pushes the code component to the Common Data Service instance with all the latest changes. It has the following parameter: <br/> - *publisher-prefix*: Publisher prefix of the organization.| `pac pcf init --namespace <specify your namespace here> --name <Name of the code component> --template <component type>` <br/> <br/> `pac pcf push --publisher-prefix <your publisher prefix>`|
|**solution**|Commands for working with [Common Data Service solution projects](/powerapps/maker/common-data-service/solutions-overview). It has the following parameters: <br/> - **init**: Initializes the solution project. It has the following parameters:<br/>  - *publisher-name*: Publisher name of the organization. <br/>  - *publisher-prefix*: Publisher prefix of the organization. <br/> - **add-reference**: Sets the reference path to the component project folder by passing the `path` parameter.<br/> - **clone**: Creates a solution project based up on the existing solution project by passing the following parameters `name`, `version`, and `include`|`pac solution init --publisher-name <enter your publisher name> --publisher-prefix <enter your publisher prefix>` <br/><br/> `pac solution add-reference --path <path to your Power Apps component framework project>`<br/><br/> `pac solution clone –name<name of the solution to be exported> --version <version of your solution> --include <settings that should be included>`|
|**auth**|Commands to [authenticate to Common Data Service](/powerapps/developer/component-framework/import-custom-controls#connecting-to-your-environment). It has the following parameters: <br/> - **create**: Creates the authentication profile for your organization by passing the `url` parameter. You need to pass the organization url for the `url` parameter. <br/> - **list**: Provides the list of authentication profiles. <br/> - **select**: Provides a way to switch between previously created authentication profiles by passing the `index` parameter.<br/>**delete**: Deletes the authentication profile created by passing  the `index` parameter.|`pac auth create --url <your Common Data Service org’s url>` <br/> <br/> `pac auth list` <br/><br/> `Pac auth select --index <index of the active profile>`|
|**telemetry**|Manages the telemetry settings. It has the following parameters: <br/>- *enable*: Enables the telemetry option.<br/> - *disable*: Disables the telemetry option.<br/> - *status*: Returns whether the telemetry is enabled or disabled.|`pac telemetry enable` <br/><br/> `pac telemetry disable`|
|**org**|Command to work with Common Data Service.|`pac org who`|
|**plugin**|Manages to create a [plug-in](/powerapps/developer/common-data-service/plug-ins) project|`pac plugin init`|

## Uninstall Power Apps CLI

To uninstall the Power Apps CLI tooling, run the MSI from [here](https://aka.ms/PowerAppsCLI).

If you are a **Private Preview** participant and have an older version of CLI, follow these steps:

1. To find out where the Power Apps CLI is installed, open a command prompt and type `where pac`.

1. Delete the PowerAppsCLI folder.

1. Open the Environment Variables tool by running the command `rundll32 sysdm.cpl,EditEnvironmentVariables` in the command prompt.

1. Double-click `Path` under the `User variable for...` section.

1. Select the row containing the PowerAppsCLI path and select the **Delete** button on the right-hand side.

1. Select **OK** twice.


## See also

[Power Apps component framework](../component-framework/overview.md)