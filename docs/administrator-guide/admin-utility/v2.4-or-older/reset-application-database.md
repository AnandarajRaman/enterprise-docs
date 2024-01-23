---
layout: post
title:  Reset Application Database – Utility for v2.4 | Bold Reports
description: Learn how to reset the application database of Bold Reports server application of v2.4 or earlier through the command line interface.
platform: Report-platform
documentation: ug
---

# Reset Application Database for Bold Reports version 2.4 or older

You can reset the database of the Bold Reports application using this command. Follow these steps:

* Open the command prompt and change the directory to the admin utility location.

   ```sh
   cd C:\Bold Reports\Utilities\AdminUtils
   ```

   ![command](/static/assets/on-premise/images/tenant-management/admin-utility/displaycmd.png)

* After changing the directory, run the following command to reset the database.

   ```sh
   AdminUtils.exe dbconfig -servername "localhost" -databasename "BoldReportsMasterDatabase" -u "Admin" -p "Admin@12345" -iswindowsauthentication false -sslenabled false
   ```

   > **IMPORTANT:**  command details:  
servername – SQL server hostname/IP  
databasename – SQL database name  
u – SQL server username  
p – SQL server password  
port - port number of Server(Required PostgreSQL only)  
iswindowsauthentication – Is windows authentication required (this is optional)  
sslenabled – Is encrypted connection required (this is optional)

   ![reset-command](/static/assets/on-premise/images/tenant-management/admin-utility/reset-con-string.png)

* Once the database has been updated successfully, then restart the application in IIS.
