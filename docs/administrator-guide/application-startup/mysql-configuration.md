---
layout: post
title: MySQL Configuration for the Bold Reports Enterprise Edition
description: Learn how to configure MySQL Database storage option for BoldID and Bold Reports Server in Bold Reports
platform: report-platform
documentation: ug
---

# MySQL Configuration

Starting with the version v2.4.19, Bold Reports introduced MySQL database support for storing the user identities and report details.

## MySQL Database Configuration for Bold Reports Server Sites

This configuration stores the reports, users, and their access permissions in MySQL Server Database.

You can connect to the existing MySQL Server instance by following the below steps.

1. Select the server type as `MySQL` and provide the `Server name` and `Port number`.

2. Provide the Username and password of the server to be connected.

3. You can connect to the MySQL Server with the below options.

    * Create new database.
    * Use an existing database.

4. Provide the database name and proceed further.

![MySQL Server](/static/assets/on-premise/images/getting-started/application-startup-mySQL-bold-reports-server.png)

> **Important:** The Bold Reports server will accept all the connections that use Transport Layer Security (TLS 1.1/1.2) encryption and AES Cryptography (128 bits). While configuring the Bold Reports Server, choose the `Enable SSL` option to support encrypted data transfer.

> **Note:** We do not have option to create database in MySQL from Azure App service.

Here, user can select simple or advanced mode for configuration.

### Simple mode

Configure a single database for Bold ID and Bold Reports.

This configuration stores the user identities, sites details, reports, users and their access permissions in a single database.

The sites will be deployed to the local file system by default in **Simple mode**

![Simple Mode](/static/assets/on-premise/images/getting-started/mysql-simple-mode-site-registration.png)

### Advanced mode

Configure individual databases for Bold ID, Bold Reports, and choose between local file system and Azure Blob Storage for Bold ID and Bold Reports.

`Bold ID` database stores user identities and sites details.

`Bold Reports` database stores reports, users, and their access permissions.

![Advanced Mode](/static/assets/on-premise/images/getting-started/mysql-advanced-mode-site-registration.png)

## See also

* [**Storage Configuration**](../../application-startup/#storage-configuration)