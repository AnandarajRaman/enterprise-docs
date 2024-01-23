---
layout: post
title: Install Bold Reports Enterprise Reporting in Silent Mode
description: Read this guide to learn about how to install the Bold Reports Enterprise Reporting using silent mode.
platform: report-platform
documentation: ug
---

# Install the Bold Reports Enterprise Reporting in silent mode

This section explains how to install and deploy the Bold Reports Enterprise Reporting in silent mode. This silent installer can be included in your existing installation process.

## Installing the Bold Reports Enterprise Reporting in command line

Please follow the below steps to install the Bold Reports Enterprise Reporting in silent mode.

1. First you need to [download](https://help.boldreports.com/enterprise-reporting/administrator-guide/getting-started/#registration--download) the `BoldReports_EnterpriseReporting.exe` from your account.

2. Run the downloaded `BoldReports_EnterpriseReporting.exe` by double-clicking it. The installer wizard automatically opens and extracts the package into the `%temp%` folder.

3. The file `boldreports_enterprisereporting(version)(timestamp).exe` file will be extracted into the `%temp%` directory.

4. Run `%temp%.`, then Temp folder will be opened. The `boldreports_enterprisereporting(version)(timestamp).exe` file will be present in one of the temp folders. The folder name will start with `is`.

    ![Temp-folder](/static/assets/on-premise/images/installation/silent-installation/temp-folder.png)

5. Copy the extracted `boldreports_enterprisereporting(version)(timestamp).exe` file and paste it in any of the local drive.

6. Exit the Wizard.

    ![Exit-wizard](/static/assets/on-premise/images/installation/silent-installation/exit-wizard.png)

7. Open the windows command prompt in **Administrator** mode and navigate to the `boldreportenterprisereport(version)(timestamp).exe` file location which has been copied and pasted to the local drive.

8. Provide the necessary arguments in the below command to install the the above `Bold Reports Enterprise Edition` installer in silent mode.

      **parameters:**
     ```console
    boldreports_enterprisereporting_(version)_(timestamp).exe /Install Silent /InstallPath:{Location to install} /IISPortNo:{Port_No} /IISSiteName:{siteName} /IsSetFirewall:{true/false} /IsDesktopShortcut:{true/false} /IsStartMenuShortcut:{true/false} /IsSilentStartUp:{true/false} /JsonFilePath:{Location of the Startup JSON file path}
    ```

9. You can install the Bold Reports Enterprise Edition installer in two ways.

     a. [Configuring the application startup details during the installation](#configuring-the-application-startup-details-during-the-installation)

     b. [Silent installation alone without providing the application startup details](#silent-installation-alone-without-providing-the-application-startup-details)

### Configuring the application startup details during the installation

If you need to set the application configuration details during the setup installation itself, you can use this parameter list.

Once the silent installation was completed, your application will be configured by default and you can proceed to use the boldreports.

Download the [application_startup](https://github.com/boldreports/api-payload/blob/master/v2/application_startup.json) JSON file and provide ServerConfiguration and UmsConfiguration details in application_startup.json file.

We have to provide Database, Storage and Site details in **ServerConfiguration**

![ServerConfiguration-reference](/static/assets/on-premise/images/installation/silent-installation/server-configuration-reference.png)

**Example,**

![ServerConfiguration-example](/static/assets/on-premise/images/installation/silent-installation/server-configuration-example.png)

> NOTE: We don't need to provide **DataStoreConfiguration** details, which is required only for BoldBI. Hence, we can ignore it.

We have to provide Database, Storage, User and unlockkey details in **UmsConfiguration**

Please follow the below steps to get **unlockkey**
1. Go to [Bold Reports Account](https://www.boldreports.com/account/downloads) and login with your account credentials.
2. Go to the Subscriptions section.
3. Click the Get Offline License Key File to download the offline key.
![Unlock-key](/static/assets/on-premise/images/installation/silent-installation/unlock-key.png)

![UmsConfiguration-reference](/static/assets/on-premise/images/installation/silent-installation/ums-configuration-reference.png)

**Example,**

![UmsConfiguration-example](/static/assets/on-premise/images/installation/silent-installation/ums-configuration-example.png)

After providing your inputs in the file, then set **IsSilentStartUp** to **true** and provide the path of JSON file to the installer as an argument.

![Silent-startUp-true](/static/assets/on-premise/images/installation/silent-installation/silent-startup-true.png)

**Example,**

![Command-line-startUp-true](/static/assets/on-premise/images/installation/silent-installation/command-line-startup-true.png)

![Bold-Reports-application](/static/assets/on-premise/images/installation/silent-installation/bold-reports-application.png)

### Silent installation alone without providing the application startup details

If you don’t want to provide the application startup configuration details during the silent installation, then set **IsSilentStartUp** to **false** and proceed with the installation.

![Silent-startUp-false](/static/assets/on-premise/images/installation/silent-installation/silent-startup-false.png)

**Example,**

![Command-line-startUp-false](/static/assets/on-premise/images/installation/silent-installation/command-line-startup-false.png)

![BoldReports-start-up](/static/assets/on-premise/images/installation/silent-installation/bold-ums-startup.png)

Once the setup installation is completed, you can provide the startup details in the Bold Reports application itself and configure it. Refer to the following [link](https://help.boldreports.com/enterprise-reporting/administrator-guide/application-startup/) for more information on application startup.
