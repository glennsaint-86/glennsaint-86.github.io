---
layout: single
title:  "VSCode Remote Development"
date:   2021-04-04 00:05:25 +0800
categories: blog
toc: true
toc_sticky: true
tags: vscode ms-vscode-remote remote-containers Azure-Functions
#permalink:
published: true
---
While updating my MacBook Pro 2011 the latest OS version was 10.13 (Mojave). The latest version of .NET Core I can run is also 3.1. I'm able to install Docker but Docker Desktop needs OSX version 10.13.  So I'm stuck with my current machine specs on setting up other developer tools. There are several options I can take, I can buy a new machine which for now isn't an option cause I seldom open my personal laptop. I can run ubuntu on a virtual box and setup my VS Code or I can try to use VS code remote containers. 


So the decision I've made was to try out VS code remote containers. This is where VS Code Remote Development comes into play, it allows to use a container, remote machine, or WSL (Windows Subsystem for Linux) as a full-featured development environment.  For in-depth details, see the following links below:
* https://code.visualstudio.com/docs/remote/remote-overview
* https://code.visualstudio.com/docs/remote/containers-tutorial


# Development Environment Setup 
In the host machine, it needs to install docker, VS Code and Remote Containers extension. In the development container, I plan to install .NET Core 3.1, Azure Function Core Tools for development of Azure Functions, VSCode extensions: CSharp, Azurite as a local emulator for storage account and REST Client for testing REST APIs.

## Setting up container folder / directory 
Create a new folder named "container-dotnet" or whatever name you've preferred and where it will be located. Once the folder is created, open the the newly created folder in vscode. 

## Creating a development container
Click on the green icon in the lower left of the status bar as illustrated below.

![vscode remote containers](/assets/images/vscode-remote-containers-01.png)

A menu selection would appear, choose the option *Remote Containers: Add Development Container Configuration Files*, once selected another menu will be shown to choose a predefined development container configuration file, scroll down into the selection until ***Show All Definitions*** is shown. As illustrated below:

![vscode remote containers selection](/assets/images/vscode-remote-containers-02.png)

Once the *Show All Definitions* has been chosen, type-in the **Azure Functions & C# - .NET Core 3.1** and select it. This would create a folder named `.devcontainer` and underneath it would have2 files: `devcontainer.json` and `Dockerfile`. At the same time in the lower left, a mesagge will popup to **Reopen in Container** file as illustrated below:

![vscode remote containers selection 2](/assets/images/vscode-remote-containers-03.png)

Ignore it first and don't **Reopen in Container** file, we'll make some minor edits on `devcontainer.json` file. Open the file and edit the following:

1. Look for the `name` field, and change the value as you wish. In my case, I've renamed it to `"dotnetcore-3.1.-azfunc".`
2. Look for the field `extensions` field, add `azurite.azurite` and `humao.rest-client` in the array.

Once the changes are done, save the file. Click on the green icon in the lower left of the status bar, a menu selection would appear and choose *Remote Containers: Reopen in Container*. This would build the development container, it would take some time depending on your internet connection. Once everything is setup and installed, the status bar would change as illustrated below: 

![vscode remote containers installed](/assets/images/vscode-remote-containers-04.png)
 
# Testing the new development container
For the test, we'll create a simple azure function, try to build it and run in the container. Under `dotnet-container` folder create a new folder `TestFunction` as illustrated below.

![azfunc 1](/assets/images/azfunc-quickguide-01.png)

Below is a sample illustration on how to create an azure function, and using C# and .NETCore 3.1.

![azfunc 2](/assets/images/azfunc-quickguide-02.gif)

This would take some time to create the project, once it's done notification message will appear in the lower left.

![azfunc 3](/assets/images/azfunc-quickguide-03.png)

Once done the folder structure would look like this
```
.vscode
TestFunction
  bin
  obj
  .gitignore
  host.json
  local.settings.json
  TestFunction.cs
  TriggerFunction.cs
```

## Configure function for testing
Now the newly created function is created, before it can be tested it needs to configure some settings. Open the `local.settings.json` file, set *AzureWebJobsStorage* field value to **"UseDevelopmentStorage=true"**.

Azurite is an Azure Storage emulator and it needs to be started prior to testing the newly created function app. To start, simple CMD+SHIFT+P (in Mac) and once the command palate pop-ups, type-in `Azurite: Start` and press ENTER.

Create a file named `test.http` and copy the content below and save it to `test.http` file. 
```
POST http://localhost:7071/runtime/webhooks/EventGrid?functionName=TriggerFunction
content-type: application/json
aeg-event-type: Notification

[
  {
    "topic": "/subscriptions/{subscription-id}/resourceGroups/Storage/providers/Microsoft.Storage/storageAccounts/xstoretestaccount",
    "subject": "/blobServices/default/containers/oc2d2817345i200097container/blobs/oc2d2817345i20002296blob",
    "eventType": "Microsoft.Storage.BlobCreated",
    "eventTime": "2017-06-26T18:41:00.9584103Z",
    "id": "831e1650-001e-001b-66ab-eeb76e069631",
    "data": {
      "api": "PutBlockList",
      "clientRequestId": "6d79dbfb-0e37-4fc4-981f-442c9ca65760",
      "requestId": "831e1650-001e-001b-66ab-eeb76e000000",
      "eTag": "0x8D4BCC2E4835CD0",
      "contentType": "application/octet-stream",
      "contentLength": 524288,
      "blobType": "BlockBlob",
      "url": "https://oc2d2817345i60006.blob.core.windows.net/oc2d2817345i200097container/oc2d2817345i20002296blob",
      "sequencer": "00000000000004420000000000028963",
      "storageDiagnostics": {
        "batchId": "b68529f3-68cd-4744-baa4-3c0498ec19f0"
      }
    },
    "dataVersion": "",
    "metadataVersion": "1"
  }
]
```

## Testing function in remote containers
Now it's time to test the function, open a new terminal and navigate to the `TestFunction` folder. Then type-in `func start host`, this will run the function locally. The indicator the functionis ready to be tested, you will see something like this in the terminal.
```
[2021-04-17T21:03:57.795Z] Found /workspaces/dotnet-container/TestFunction/TestFunction.csproj. Using for user secrets file configuration.

Functions:

        TriggerFunction: eventGridTrigger

For detailed output, run func with --verbose flag.
[2021-04-17T21:04:07.199Z] Host lock lease acquired by instance ID '000000000000000000000000E02E8362'.
```

To test, open the `test.http` file, on top of the POST http://url, you will notice a Send Request that is clickable.

![azfunc 4](/assets/images/azfunc-quickguide-04.png)

Click Send Request to run the test. Another window will open and the result should show the response of the HTTP test, see below for illustration:
```
HTTP/1.1 202 Accepted
Connection: close
Date: Sat, 17 Apr 2021 21:08:40 GMT
Server: Kestrel
Content-Length: 0
```

Since the function would display the **data** element of the event grid message, go to terminal, and the output would look something like this:
```
[2021-04-17T21:08:41.220Z] Executing 'TriggerFunction' (Reason='EventGrid trigger fired at 2021-04-17T21:08:41.1151969+00:00', Id=a8fe681d-7ad3-4c36-bad8-c98e80b25f47)
[2021-04-17T21:08:41.247Z] {
[2021-04-17T21:08:41.247Z]   "api": "PutBlockList",
[2021-04-17T21:08:41.247Z]   "clientRequestId": "6d79dbfb-0e37-4fc4-981f-442c9ca65760",
[2021-04-17T21:08:41.248Z]   "requestId": "831e1650-001e-001b-66ab-eeb76e000000",
[2021-04-17T21:08:41.248Z]   "eTag": "0x8D4BCC2E4835CD0",
[2021-04-17T21:08:41.249Z]   "contentType": "application/octet-stream",
[2021-04-17T21:08:41.249Z]   "contentLength": 524288,
[2021-04-17T21:08:41.249Z]   "blobType": "BlockBlob",
[2021-04-17T21:08:41.250Z]   "url": "https://oc2d2817345i60006.blob.core.windows.net/oc2d2817345i200097container/oc2d2817345i20002296blob",
[2021-04-17T21:08:41.250Z]   "sequencer": "00000000000004420000000000028963",
[2021-04-17T21:08:41.251Z]   "storageDiagnostics": {
[2021-04-17T21:08:41.251Z]     "batchId": "b68529f3-68cd-4744-baa4-3c0498ec19f0"
[2021-04-17T21:08:41.251Z]   }
[2021-04-17T21:08:41.252Z] }
[2021-04-17T21:08:41.299Z] Executed 'TriggerFunction' (Succeeded, Id=a8fe681d-7ad3-4c36-bad8-c98e80b25f47, Duration=163ms)
```

# Takeaways
* Development in Remote Containers can keep the host machine clean. Instead of installing the SDK / libraries needed for development in host machine, it can be done inside the container. 
* As illustrated above, developing and testing Azure Function in CSharp and .NET Core 3.1 is possible with Remote Containers
* To know more about Remote Containers, visit the links below:
  * https://code.visualstudio.com/docs/remote/remote-overview
  * https://code.visualstudio.com/docs/remote/containers-tutorial