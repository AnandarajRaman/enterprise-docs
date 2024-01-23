---
layout: post
title:  Reset Application Database – Admin Utility | Bold Reports
description: Learn how to reset the application database of Bold Reports server application through the command line interface.
platform: Report-platform
documentation: ug
---

# Reset Application Database

Please refer to your operating system’s documentation for instructions on how to reset the database in the Bold Reports application.
* [Windows](#windows)
* [Linux](#linux)
* [Docker](#docker)
* [Kubernetes](#kubernetes)

## Windows

1. Open the command prompt and change the directory to the admin utility location.

   ```sh
   cd C:\BoldServices\utilities\adminutils
   ```

   ![command](/static/assets/on-premise/images/tenant-management/admin-utility/utilscmd-1.png)

2. After changing the directory, run the following command to the reset database.

   ```sh
   Syncfusion.Server.Commands.Utility.exe dbconfig -servername "localhost" -databasename "BoldReportsMasterDatabase" -u "Admin" -p "Admin@12345" -iswindowsauthentication false -sslenabled false
   ```

    > **IMPORTANT:**  command details:

    servername - SQL server hostname/IP

    databasename – SQL database name

    u – SQL server username

    p – SQL server password

    port - port number of SQL Server(Required PostgreSQL only)

    iswindowsauthentication – Is windows authentication required (this is optional)

    sslenabled – Is encrypted connection required (this is optional)

   ![reset-command](/static/assets/on-premise/images/tenant-management/admin-utility/reset-con-string-1.png)

3. Once the database has been updated successfully, restart the application in [IIS](../../faq/how-to-restart-the-bold-reports-enterprise-application/#windows).

## Linux

1. Open the command prompt and change the directory to the admin utility location.

   ```sh
   cd /var/www/bold-services/application/utilities/adminutils/
   ```

   ![linux-utility-path-command](/static/assets/on-premise/images/tenant-management/admin-utility/linux-utility-path.png)

2. After changing the directory, run the following command to reset the database:

   ```sh
   ../../../dotnet/dotnet Syncfusion.Server.Commands.Utility.dll dbconfig -servername "localhost" -databasename "BoldReportsMasterDatabase" -u "Admin" -p "Admin@12345" -iswindowsauthentication false -sslenabled false -port "5432"
   ```

   > **IMPORTANT:**  command details:

   servername – SQL server hostname/IP

   databasename – SQL database name

   u – SQL server username

   p – SQL server password

   port - Port number required for PostgreSQL and MySQL

   iswindowsauthentication – Is windows authentication required (Required for MSSQL only)

   sslenabled – Is encrypted connection required (this is optional)

   ![linux-reset-command](/static/assets/on-premise/images/tenant-management/admin-utility/linux-reset-cmd.png)

3. Once the database has been updated successfully, restart the application by following this [link](../../faq/how-to-restart-the-bold-reports-enterprise-application/#linux)

## Docker

### Single container image

1. Open the command prompt and bash the container, then change the directory to the admin utility location.

   ```sh
   docker exec -it <Container ID or Container name>
   ```

   ```sh
   cd /application/utilities/adminutils/
   ```

   ![single-docker-path-cmd](/static/assets/on-premise/images/tenant-management/admin-utility/single-docker-path.png)

2. After changing the directory, run the following command to reset the database:

   ```sh
   dotnet Syncfusion.Server.Commands.Utility.dll dbconfig -servername "localhost" -databasename "BoldReportsMasterDatabase" -u "Admin" -p "Admin@12345" -iswindowsauthentication false -sslenabled false -port "5432" -additionalparameters "Pooling=True"
   ```

   ![single-docker-reset-cmd](/static/assets/on-premise/images/tenant-management/admin-utility/single-docker-reset.png)

3. Once the database has been updated successfully, restart the application by using the below command.

   ```sh
   docker restart <container ID or container name>
   ```

## Multi container image

1. Open the command prompt and bash the `id_web_container` container, then change the directory to the admin utility location.

   ```sh
   docker exec -it <Container ID or Container name>
   ```

   ```sh
   cd /application/utilities/adminutils/
   ```

   ![single-docker-path-cmd](/static/assets/on-premise/images/tenant-management/admin-utility/single-docker-path.png)

2. After changing the directory, run the following command to reset the database:

   ```sh
   dotnet Syncfusion.Server.Commands.Utility.dll dbconfig -servername "localhost" -databasename "BoldReportsMasterDatabase" -u "Admin" -p "Admin@12345" -iswindowsauthentication false -sslenabled false -port "5432" -additionalparameters "Pooling=True"
   ```

   > **IMPORTANT:**  command details:

   servername – SQL server hostname/IP

   databasename – SQL database name

   u – SQL server username

   p – SQL server password

   port - Port number required for PostgreSQL and MySQL

   iswindowsauthentication – Is windows authentication required (Required for MSSQL only)

   sslenabled – Is encrypted connection required (this is optional)

   additionalparameters - Additional parameters required for database connection (this is optional)

   ![single-docker-reset-cmd](/static/assets/on-premise/images/tenant-management/admin-utility/single-docker-reset.png)
3. Once the database has been updated successfully, restart all containers by using the below command.

   ```sh
   docker ps
   ```

   ```sh
   docker restart <container ID or container name>
   ```

   > **Note:** Restart all seven containers using the above command, one by one, from the container name or ID.

## Kubernetes

1. Open the command prompt and bash the `id_web_deployment` pod, then change the directory to the admin utility location.

   ```sh
   kubectl exec -it <id-web-deployment-pod> -n namespace -- bash
   ```

   ```sh
   cd /application/utilities/adminutils/
   ```

   ![single-docker-path-cmd](/static/assets/on-premise/images/tenant-management/admin-utility/single-docker-path.png)
2. After changing the directory, run the following command to reset the database:

   ```sh
   dotnet Syncfusion.Server.Commands.Utility.dll dbconfig -servername "localhost" -databasename "BoldReportsMasterDatabase" -u "Admin" -p "Admin@12345" -iswindowsauthentication false -sslenabled false -port "5432" -additionalparameters "Pooling=True"
   ```

   > **IMPORTANT:**  command details:

   servername – SQL server hostname/IP

   databasename – SQL database name

   u – SQL server username

   p – SQL server password

   port - Port number required for PostgreSQL and MySQL

   iswindowsauthentication – Is windows authentication required (Required for MSSQL only)

   sslenabled – Is encrypted connection required (this is optional)

   additionalparameters - Additional parameters required for database connection (this is optional)

   ![single-docker-reset-cmd](/static/assets/on-premise/images/tenant-management/admin-utility/single-docker-reset.png)
3. Once the database has been updated successfully, restart the application using the below command.

   ```sh
   kubectl rollout restart deploy -n <namespace>
   ```