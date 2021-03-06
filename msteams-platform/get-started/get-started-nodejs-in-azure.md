---
title: Host your Node based Teams app in Azure
description: Host your Teams app in Azure using Node.JS
keywords: getting started azure teams apps Node
ms.date: 11/09/2018
---
# Host your Node Teams app in Azure

## You will need:

* **A Microsoft Azure account**. For testing you can use a free trial account and migrate to a production ready account when the app is ready for public use. If you have never used Azure before, you can get started by [creating a new free account](https://azure.microsoft.com/en-us/free/). If you already have an Azure account you can use your existing account to host this app for free.
* **Visual Studio Code**. This free code editor can be downloaded at: [Visual Studio Code](https://code.visualstudio.com/download). Once VS Code is installed, add support for Azure deployment by clicking this link to install the [App service extension](vscode:extension/ms-azuretools.vscode-azureappservice).
* **A downloaded sample app to deploy**. See [Getting Started with Node.JS](~/get-started/get-started-nodejs-app-studio#DownloadAndHost) to download and test the sample app. Return to this topic when it is time to host the app.

## Open the app in VS.Code

Open your preferred shell, and navigate to the root of the sample app *msteams-samples-hello-world-nodejs*, then enter:

```bash
code .
```

VS Code will start, pointing to the root directory for the sample.

<img width="450px" title="Visual Studio" src="~/assets/images/get-started/visual-studio-code.png" />

## Configure your Azure account

In VS Code, click on the Azure icon in the left hand tool bar.

<img title="Azure icon" src="~/assets/images/get-started/visual-studio-code-azure-icon.png" />

This will display the Azure sign in and management pane.

<img width="450px" title="Signing in to Azure" src="~/assets/images/get-started/visual-studio-code-azure-sign-in.png"/>

Click on *Sign in to Azure...*. A dialog will open in the lower right corner of VS Code. Read the instructions and Click *Copy & Open*.
A web page will be displayed where you can enter a confirmation code.

<img width="450px" title="Confirm in Azure" src="~/assets/images/get-started/visual-studio-code-azure-login-web.png"/>

Right click where it says *Code*, and select paste from the right click menu.  This will enter a code provided by the previous dialog.

You can now return to VS Code, where the Azure pane will now look something like this:

<img width="450px" title="Azure pane in VS Code" src="~/assets/images/get-started/visual-studio-azure-account.png"/>

What you actually see will depend on the type of account you have with Azure.

## Deploy the app to Azure

Look for the up-arrow button at the top of the Azure pane in VS Code. This is the *Deploy to Web App...* button. click on it to start.

You will first be asked if you want to create a new web app. Choose this option.

You will then be asked to enter a globally unique name for the new Web App. Do so and press enter.

<img title="Azure icon" src="~/assets/images/get-started/visual-studio-azure-name-web-app.png"/>

You will then be asked to select a Node.js runtime for your app. Choose the version marked LTS - Recommended for new apps.

You will see several status messages as your app is deployed.

You may be asked if you would like to update your workspace configuration to run `npm install` on the target server. Choose yes.

You may then be asked if you want to always deploy the workspace. You can answer yes to this also.

Finally you will see this message, assuming everything went well.

<img width="450px" title="Azure icon" src="~/assets/images/get-started/visual-studio-azure-new-web-app-finished.png"/>

<a name="configureenvironmentvariables"></a>

## Configure environment variables

Environment variables are used in Azure to securely hold sensitive information like app ids and passwords. You will need to manually add the following Application Settings (environment variables) in VS Code by right-clicking *Application Settings*.

```
MICROSOFT_BOT_APP_ID=<YOUR BOT'S APP ID>
MICROSOFT_BOT_APP_PASSWORD=<YOUR BOT'S PASSWORD>
WEBSITE_NODE_DEFAULT_VERSION=8.9.4
```

<img width="450px" title="Azure environment variables" src="~/assets/images/get-started/visual-studio-azure-env-var.png"/>

The values for these settings were generated by App Studio in Teams when you were setting up your app. If you have not run App Studio yet, you can update your app and redeploy after you have done so.

## Testing your app on Azure

Navigate to the following URLs and confirm that the correct pages appear.

* https://YourAzureSite.com
* https://YourAzureSite.com/hello
* https://YourAzureSite.com/first
* https://YourAzureSite.com/second
