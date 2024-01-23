---
layout: post
title: Install the client libraries for Azure App service.
description: Bold Reports Enterprise Edition uses client libraries such as Oracle, MySQL, and PostgreSQL to connect with their respective SQL database variants. You need to read and accept client library license to install client libraries.
platform: report-platform
documentation: ug
---

# Install Client libraries

Bold Reports Enterprise Edition uses client libraries such as Oracle, MySQL, and PostgreSQL to connect with their respective SQL database variants. You need to read and accept client library license to install client libraries.

Please follow the below step to install client libraries.

1. Open **kudu PowerShell console** for Bold Reports Azure App service. We can access the Kudu service through the portal by navigating to `Web App dashboard > Advanced Tools > Click on Go`.
![Kudo powershell](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/kudo-powershell.png)

2. Select **PowerShell** console.
![Kudo console option](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/kudo-console-tool.png)

3. Go to client library location

     **{drive}\home\site\wwwroot\clientlibrary\boldreports**

4. Here, you can see the client library consent document consent-to-deploy-client-libraries.txt. Read client libraries LICENSE details and execute the following command to install client libraries.

5. .\install-optional-libs.ps1 -ClientLibraries "oracle,postgresql,mysql"
![Kudo ClientLibraries](/static/assets/on-premise/images/installation-and-deployment/azure-deployment/app-service-using-arm-template/kudo-clientlibraries.png)
