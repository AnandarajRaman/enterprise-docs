---
layout: post
title: Azure Active Directory authentication | Bold Reports
description: Azure active directory authentication settings to let your users use their Azure AD credentials to login into the Bold Reports On-Premise Edition.
platform: Report-platform
documentation: ug
---

# How to set up Azure Active Directory for SSO authentication in Bold Reports

This section explains how to perform Single Sign-On (SSO) for users in the Azure Active Directory with Bold Reports application.

> NOTE: This configuration has to been done in [Azure Portal](https://portal.azure.com/#home).

## Prerequisites

* An Azure account with Active Directory support.
* Install the Bold Reports application and log in with an administrator account.

## Steps to set up Bold Reports to perform Single Sign-On

1. Login to the URL `{Bold Reports URL}/ums/administration/sso?view=azure-ad-settings` using the admin credential.

2. Click `Settings` in the left menu.

    ![application-settings](/static/assets/on-premise/images/authentication/single-sign-on/azure-active-directory/sso-settings.png)

3. Click `Authentication`, and then go to the `Azure AD` tab and save the following fields in UMS settings:

    ![azure-ad-settings](/static/assets/on-premise/images/authentication/single-sign-on/azure-active-directory/enable-sso.png)

    > **NOTE:** Refer to this following link to register the [Bold Reports web application](https://help.boldreports.com/enterprise-reporting/administrator-guide/how-to/set-up-azure-active-directory/#steps-to-register-bold-reports-on-premise-application-in-azure-active-directory) and [Bold Reports mobile application](https://help.boldreports.com/enterprise-reporting/administrator-guide/how-to/set-up-azure-active-directory/#steps-to-register-bold-reports-on-premise-mobile-application-in-azure-active-directory) in Azure Active Directory.

    ***Application Id:** Go to the registered application and click the `Overview`, and then copy the `Application Id` and paste it.

    ![application-id](/static/assets/on-premise/images/authentication/single-sign-on/azure-active-directory/app-id.png)

    ***Application Id URI:** Go to the registered application and click the `Overview`, and then copy the `Application Id URI` and paste it.

    ![application-id-uri](/static/assets/on-premise/images/authentication/single-sign-on/azure-active-directory/app-id-uri.png)

    ***Tenant Name:** Navigate to the created `Azure Active Directory` and copy the domain name from the `Overview`.

    ![tenant-name](/static/assets/on-premise/images/authentication/single-sign-on/azure-active-directory/tenant-name.png)

    ***Mobile App Client ID:** Go to the registered application for the Bold Reports mobile application. Copy the `Application ID` and paste it.

    ![mobile-app-id](/static/assets/on-premise/images/authentication/single-sign-on/azure-active-directory/mobile-app-id.png)

4. Now, click save. After the values are saved, the application will be `Restarted` to apply the settings.