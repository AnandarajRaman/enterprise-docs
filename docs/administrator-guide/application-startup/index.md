---
layout: post
title: Application Startup for the Bold Reports Enterprise Edition
description: Learn how to set up the  Bold Reports Enterprise by configuring storage options and registering a new user.
platform: report-platform
documentation: ug
---

# Application Startup

> **NOTE**: If you have already installed Bold Reports on your machine, please go to [this section](./../application-startup/#activate-bold-reports-license) to activate your Bold Reports account.

This topic describes how to activate the account and startup the Bold Reports Enterprise Application.

You can activate your account either by using your login credentials or by offline unlock key.

## Activate the account using login credentials

You can sign in with your registered email address to activate your subscription.

![Activate the account page](/static/assets/on-premise/images/getting-started/application-startup-login.png)

### Select Login option

From the login window, choose your account type and proceed to login.

* Bold Reports Login Credentials
* Azure AD

![Application startup login form](/static/assets/on-premise/images/getting-started/login-option.png)

### Select license

If you are having multiple Bold Reports licenses, then you will be getting this screen and select the corresponding license to proceed with application startup. Otherwise, you will be automatically redirected to the application startup screen.

![Select Portal License](/static/assets/on-premise/images/getting-started/check-license-option.png)

## Offline Installation

> **NOTE:** Offline unlock key available for selected customers only. Please [contact us](https://www.boldreports.com/contact) to get access to the offline unlock key.

![Activate the account with Unlock key option](/static/assets/on-premise/images/getting-started/application-startup-login-license.png)

If you are installing the Bold Reports in firewall restricted environments, you can use the offline unlock key to activate the account. Please download your offline unlock key [here](https://www.boldreports.com/account/downloads/embedded).

![Unlock key file page](/static/assets/on-premise/images/getting-started/offline-setup-page.png)

Once the unlock key is uploaded, proceed to the next screen for configuring the application.

![Select Unlcok key file ](/static/assets/on-premise/images/getting-started/offline-setup.png)

### Possible errors cases and their solution

| Cases      | Solution                                            |
|-------------------  |-----------------------------------------------------------  |
| Invalid File Type | Please ensure to upload the valid unlock key file (lic) downloaded from [here](https://www.boldreports.com/account/downloads/embedded).
|  unlock key Expired    | Your unlock key date was expired. Please download the new unlock key file from [here](https://www.boldreports.com/account/downloads/embedded).   |

> **NOTE:** If you are facing any other issues, please contact us from [here](https://www.boldreports.com/contact).

## No Trial / New Account Request

If you do not have an account for Bold Reports, you can request a new trial from this [link](https://www.boldreports.com/pricing).

![Activate the account with No Trail option](/static/assets/on-premise/images/getting-started/application-startup-sign-up.png)

## Application Startup for Bold Reports Enterprise

The application startup screen helps you to configure storage options and admin account setup.

The application startup holds the storage options configuration for the below application,
1. Bold Reports Sites - Manages user identities and sites
2. Bold Reports Server- Manages reports, data sources, dataset, schedules and the user permissions.

## New User - System Administrator

A new user should be created to access the Bold Reports sites and reports with the details mentioned in the below image.

![Admin User Registration](/static/assets/on-premise/images/getting-started/application-startup-admin.png)

While creating this new user account, a new group called `System Administrator` is also created.

By default, the `System Administrator` group has permission to do the following:

* Create Reports
* Create Data Sources
* Create Dataset
* Create Schedules
* Create Users
* Create Groups
* Manage Permissions for users and groups

The new user account created is assigned to this group by default.
![Bold Reports Server](/static/assets/on-premise/images/getting-started/starting-bold-reports-server.png)

## Database Configuration

This configuration helps you to configure single or individual databases for Bold ID and Bold Reports configuration.

`Bold ID` database stores the tenants, users, and their tenant access information.

`Bold Reports` database stores the reports, users, and their resource access permissions. You can use anyone of the following database to configure the Bold Reports Server.

## Storage Options

* SQL server, Azure SQL
* PostgreSQL
* MySQL

You can connect to the existing SQL Server instance with the below options.

* Create new database.
* Use an existing database.

  ![SQL Server Site](/static/assets/on-premise/images/getting-started/application-startup-site-registration.png)

### Create New Database

[Database Configuration for Bold Reports Server in SQL Server](./sql-configuration/#sql-server-database-configuration-for-bold-reports-server-sites)

[Database Configuration for Bold Reports Server in PostgreSQL](./postgresql-configuration/#postgresql-database-configuration-for-bold-reports-server-sites)

[Database Configuration for Bold Reports Server in MySQL](./mysql-configuration/#mysql-database-configuration-for-bold-reports-server-sites).

### Existing Database

Existing database can be used to configure the database to store the user identities and report details.

> The credentials that is given to connect to database Server instance must have permissions to
> * Create Database
> * Create Table
> * Insert
> * Update Table
> * Alter Table
> * Select
> * Drop Table
> * Drop Database

Here, user can select a simple or advanced mode for configuration.

#### Simple mode

Configure a single database for Bold ID and Bold Reports.

This configuration stores the user identities, site details, reports, users, and their access permissions in a single database.

The sites will be deployed to the local file system by default in **Simple mode**

![Simple Mode](/static/assets/on-premise/images/getting-started/simple-mode-site-registration.png)

#### Advanced mode

Configure individual databases for Bold ID and Bold Reports, and choose between local file system and Azure Blob Storage for Bold ID and Bold Reports.

`Bold ID` database stores user identities and site details.

`Bold Reports` database stores reports, users, and their access permissions.

![Advanced Mode](/static/assets/on-premise/images/getting-started/advanced-mode-site-registration.png)

## Storage Configuration

In advanced mode, the user can select the preferred storage type, either File Storage or Blob Storage, to store the resource in Bold ID and Bold Reports.

![Storage Configuration](/static/assets/on-premise/images/getting-started/advanced-mode-storage-configuration.png)

> By default, storage type is File Storage.
User can select the Blob Storage by giving Azure Blob Credential in the required field.

![Azure Blob Storage](/static/assets/on-premise/images/getting-started/azure-blob-storage.png)

You can find the details how to configure the Azure Blob [here](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-portal).

Once the process completed, you can able to

* Manage sites – where you can manage permissions for the sites you have created.
* Go to Reports - where you can create, edit, update the reports and so on.

![Launch Bold Reports Reports](/static/assets/on-premise/images/getting-started/launch-application.png)

## Report Server Database

Bold Reports Report Server stores the following information only to the server database:

* Information of reports
* Information of shared data sources
* Information of shared datasets
* Categories
* Schedules definitions
* Permissions settings associated for report, data source, data set, categories, and schedules
* Report Server configurations

> The reports, dataset, and data source, which are added to the Bold Reports Report Server will be maintained in some location based on storage type you have chosen while configuring the Bold Reports Server application. You can refer more details from this [link](./../faq/where-does-the-data-resides-in-bold-reports/).

## Activate Bold Reports license

You can activate your account either by using your login credentials or by offline unlock key.

Open the Manage License Page - `{domain}/ums/administration/license-settings`

Then, choose the Enterprise Reporting tab.

![Enterprise Reporting tab](/static/assets/on-premise/images/getting-started/manage-license-page-reports-tab.png)

### Activate Bold Reports license using the login credential

You can sign in with your registered email address to activate your subscription.

![Account activate using login](/static/assets/on-premise/images/getting-started/activate-boldreports-account.png)

If you are having multiple Bold Reports licenses, then you will be getting this screen and select the corresponding license to activate the Bold Reports. Otherwise, your Bold Reports license will be automatically activated.

![Choose Bold Reports License](/static/assets/on-premise/images/getting-started/check-license-option.png)

### Upload unlock key

> **NOTE:** Offline unlock key available for selected customers only. Please [contact us](https://www.boldreports.com/contact) to get access to the offline unlock key.

![Unlock Key option](/static/assets/on-premise/images/getting-started/upload-unlock-key-option.png)

Once the unlock key is uploaded, proceed to the `Upload License` button for activating the Bold Reports License.

![Updated Bold Reports License](/static/assets/on-premise/images/getting-started/update-license-key.png)

### Create site

Please refer to this [Create Site](./../manage-tenants/create-site/) document to create a new Bold Reports site.

## See Also

* [**Create another site in multi-tenant application**](./../manage-tenants/create-site/)