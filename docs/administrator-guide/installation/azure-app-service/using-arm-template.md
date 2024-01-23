---
layout: post
title: Bold Reports Azure App deployment using the ARM Template
description: This topic describes how to deploy the Bold Reports Azure App Service in the Microsoft Azure using the ARM template.
platform: report-platform
documentation: ug
---

# Create a Bold Reports Azure App Service using the ARM template

> If you already having Report Server Azure App Service with Syncfusion Report Platform Report Server or Bold Reports v1.x Report Server, then refer to the Syncfusion Report Server migration or upgrade v1.x for your startup.

This section explains how to create the Bold Reports Report Server into Azure cloud as App Service using the ARM template by following these steps:

1. Log in to [Azure portal](https://portal.azure.com/).

2. Click **Create resource** from the top menu.
![New in Azure portal](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/new-template.png)

3. Search `Template deployment` in the marketplace and select **Template deployment**.
![Search Template deployment option](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/search-template.png)

4. Click **Create**.
![Create Template deployment](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/create-template.png)

5. Now, select **Build your own template in the editor** in the Custom Deployment window.
![Build your own template in the editor option](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/build-your-own-template.png)

6. [Click here](https://raw.githubusercontent.com/boldreports/bold-reports-azure/master/armtemplates/v5.4.20/BoldReportsAppServiceTemplate.json)  to download the ARM template file.

7. Copy all the contents in the template file and replace them in the Edit template window, and then click **Save**.
![Edit the template and replace the template](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/edit-template.png)

8. Fill the details as instructed in the following to complete the deployment steps.
    * **Subscription**: Choose the subscription that you have with Azure. Learn more about subscriptions from [here](https://blogs.msdn.microsoft.com/arunrakwal/2012/04/09/create-windows-azure-subscription/).

    * **Resource group**: This is a logical group in Azure to group your resources like web app, storage account, network etc. Learn more about resource groups from [here](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview#resource-groups).

    * **Location**: Choose the location to deploy the app. **East US** is our recommended location.

    * **Web App name**: This is the name of the Report Server that you want to have in the URL. As this is going to be the URL, it should be unique globally. Deployment process will be failed, if this is already present and you should start once again with another name.

    * **Storage account name**: This is mandatory for Blob storage and also must be unique as that of the Web App name. Learn more about storage accounts from [here](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-overview).

    * **Storage account type**: This is optional, if you have chosen file storage in storage type and mandatory for Blob storage. Learn more about storage account types from [here](https://learn.microsoft.com/en-us/azure/storage/blobs/object-replication-overview).

   > **Note:** Web App name and Storage account name should be in lowercase only.

9. Select the agreement check box and click **Purchase** to deploy the Bold Reports On-Premise Web App.
![Fill app service details](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/custom-template-details-form.png)

   Now, Bold Reports Multi-tenant App Service(Web App) deployment get started.

   > **Note:** Deployment process will take around 15 minutes to complete.

   The App Service plan for the Web App is created, which will be in `Basic – B1` by default. Learn more about App Service plans from [here](https://docs.microsoft.com/en-us/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview). Bold Reports On-Premise Web App does not support free or shared App Service plans.

   Bold Reports On-Premise supports basic, standard, and premium App Service plans in the Azure. The minimum recommended App Service plan to run the application is the basic plan.

   To get better performance, scale up the App Service plan from basic to standard or premium plans. Refer to the following documentation links to learn how to scale up and scale out the App Service plan.

   Scale up: <https://docs.microsoft.com/en-us/azure/app-service-web/web-sites-scale>

   Scale out: <https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/insights-how-to-scale>

## Configure a new Bold Reports

Configure the Bold Reports Multi-tenant Azure App Service by following these steps:

1. Click the `Proceed to Setup`.
   ![Proceed to Setup](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/proceed-to-setup-button.png)

2. Provide the [user details](../../../application-startup/#new-user---system-administrator) and this user will be an admin for Bold Reports, and then click `Next`.
   ![Admin Details](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/admin-details.png)
   >If you wish to migrate your Syncfusion Report Server Azure app service(`v4.x`) data or Bold Reports Azure app service version(`v1.x`) data to Bold Reports Multi-tenant Azure App Service, while configuring the admin details you must use the admin email id of Syncfusion Reports Server or Bold Reports Server (Single Tenant).

3. Provide your [Database details](../../../application-startup/#database-configuration) to maintain your reports, users, and their access permissions, and then click `Next`.
   ![Report Server Database Configuration](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/report-server-database-configuration.png)

4. Click the check box to fetch the pre-configured blob details at the deployment time to maintain your physical files of reports, datasets, data sources etc, and then click `Next`.
   ![Azure Blob Configuration](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/azure-blob-configuration.png)

5. Once the configuration is done, then you can able to navigate sites or reports page by success login.