---
layout: post
title: Upgrade steps for Bold Reports Azure App Service
description: This documentation explains about how to upgrade the Bold Reports Azure App Service from v3.x to latest in the Microsoft Azure.
platform: report-platform
documentation: ug
---

# Upgrade Bold Reports Enterprise Reporting version from 3.x to latest

* Bold Reports releases several major versions in a year. Each version includes new features, bug fixes and other improvements.

* You can refer the features and enhancements from the [Release Notes](https://www.boldreports.com/release-history/embedded-reporting/5-1).

* To upgrade the Bold Reports Azure App Service to latest version you must have access rights to edit the Bold Reports Server App Service.

Follow these below steps to upgrade the Bold Reports Azure App service version from 3.x to latest.

1. Login to [Azure portal](https://portal.azure.com/).
2. Select `App Services` in Microsoft Azure Services.
   ![App Service](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/app-services.png)
3. Select `Bold Reports Azure App Service`.
4. In the `Overview` section, Click the `Stop` button.
   ![Stop App Service](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-stop-app-service.png)
5. Select `Deployment center` in the left panel of the Bold Reports App Service.
   ![Deployment center](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-deployment-center.png)
6. Once the deployment center is clicked, click the `Disconnect`. Now the deployment panel will open.
   ![Disconnect](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-disconnect-option.png)
7. Choose the `External Git`.
   ![External](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-external.png)
8. Now, fill the below details in the `Settings` tab and click the `Save`.
    * Repository - `https://github.com/boldreports/bold-reports-azure.git`
    * Branch - `v{release-version}`
    * Repository Type - `Public`
   ![Configure tab](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-configure-tab.png)
9. The “Successfully set up deployment” notification will be shown in the notification.
   ![Finish Upgrade](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-finish-upgrade.png)
   ![Set Up Success](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-setup-success.png)
10. Select the `Sync` button in the deployment center page.
    ![Sync option](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-sync-option.png)
11. Synchronization request submitted notification will be shown in the notification and synchronization progress is shown in the deployment center page.
    ![Synchronization Request Submitted](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-synchronization-request-submitted.png)
12. Please wait until synchronization is completed.
13. >**Breaking Changes:** This step is applicable only for upgrading Azure App Service from version 3.x to 5.1.20. Otherwise, skip this step.
      * In `Configuration` section, change the below value in `General Settings`.
         <table>
         <tr>
          <th>Settings</th>
          <th>Value</th>
         </tr>
         <tr>
          <td>.NET version</td>
          <td>.NET 6 (LTS)</td>
         </tr>
         </table>

    ![General Settings](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/dot-net-version-in-general-settings.png)
      * Add below Physical Path in `Path Mappings` and `Save` the settings.
         <table>
         <tr>
          <th>Virtual Path</th>
          <th>Physical Path</th>
         </tr>
         <tr>
          <td>/reporting/viewer</td>
          <td>site\wwwroot\reporting\viewer</td>
         </tr>
         </table>

    ![Path Mappings](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/viewer-service-in-path-mappings.png)
14. Start the Bold Reports Azure App Service by clicking `Start` button from Overview section.
    ![Start App Service](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-start-app-service.png)
15. Now, we have completed the Bold Reports upgrade process. Launch the Bold Reports by clicking the `browse` option or type in the Bold Reports URL in the browser.
    ![Browse option](/static/assets/on-premise/images/installation-and-deployment/upgrade/azure-app-service/upgrade-browse-option.png)