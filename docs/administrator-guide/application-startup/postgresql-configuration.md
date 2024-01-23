---
layout: post
title: PostgreSQL Configuration for Bold Reports Enterprise Edition
description: Learn how to configure PostgreSQL Database storage option for BoldID and Bold Reports Server in Bold Reports
platform: report-platform
documentation: ug
---

# PostgreSQL Configuration

Bold Reports have PostgreSQL database support for storing the user identities and report details.

## PostgreSQL Database Configuration for Bold Reports Server Sites

This configuration stores the reports, users and their access permissions in PostgreSQL Server Database.

You can connect to the existing PostgreSQL Server instance by following the below steps.

1. Select the server type as `PostgreSQL` and provide the server details.

2. You can connect to the PostgreSQL Server with the below options.

    * Create new database.
    * Use an existing database.

3. Provide the database name and proceed further.

![PostgreSQL Server](/static/assets/on-premise/images/getting-started/application-startup-site-registration-postgreSQL-server.png)

> **Important:** The Bold Reports server will accept all the connections that use Transport Layer Security (TLS 1.1/1.2) encryption and AES Cryptography (128 bits). While configuring the Bold Reports Server, choose the `Enable SSL` option to support encrypted data transfer.

Here, user can select simple or advanced mode for configuration.

### Simple mode

Configure a single database for Bold ID and Bold Reports.

This configuration stores the user identities, sites details, reports, users and their access permissions in a single database.

The sites will be deployed to the local file system by default in **Simple mode**

![Simple Mode](/static/assets/on-premise/images/getting-started/postgresql-simple-mode-site-registration.png)

### Advanced mode

Configure individual databases for Bold ID, Bold Reports, and choose between local file system and Azure Blob Storage for Bold ID and Bold Reports.

`Bold ID` database stores user identities and sites details.

`Bold Reports` database stores reports, users, and their access permissions.

![Advanced Mode](/static/assets/on-premise/images/getting-started/postgresql-advanced-mode-site-registration.png)

## See also

* [**Storage Configuration**](../../application-startup/#storage-configuration)