---
layout: post
title: Adding Okta users in Bold Reports by OpenID connect
description: This documentation explains about how to add Okta user in Bold Reports using the OpenID connect settings
platform: report-platform
documentation: ug
---

# Single Sign-On(SSO) with Okta authentication in Bold Reports

 Users can be added to the Bold Reports application using the Okta provider. By importing them, you can share the reports and email exported reports with them.

## How to register the Bold Reports application in Okta

This section explains how to perform Single Sign-On for users in Okta with the Bold Reports application.

> This configuration has to be done in Okta website.

## Prerequisites

* An admin account in Okta.
* Install Bold Reports application.

## Steps to register the Bold Reports application

1. Login to the Okta website with an `admin` account.
![Login Okta](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/okta/okta-login.png)

2. Click `Applications` in the header menu.
![Click Application](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/okta/okta-application.png)

3. Click `Add Application` button.
![Add Application](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/okta/okta-add-application.png)

4. Click `web` and proceed with `Next`.
![Select Web Platform](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/okta/okta-platform-web.png)

5. Fill in the following application details in the next page and click `Done`.

    * Name
    * Login Redirect URIs
    * Logout Redirect URIs
![Redirect URI](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/okta/okta-redirect-uri.png)

6. The Login redirect URIs must be the URI in the settings of your Bold Reports application as in the following snap.
![Login Redirect URI](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/okta/login-redirect-uri.png)

7. In the next page, you will get the `Client ID` and `Client Secret` at the bottom of the page along with the other details you filled in the previous page.
![Okta Client Credential](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/okta/okta-client-credential.png)

## Enable Okta authentication in Bold Reports

Configure the settings in Bold Reports as in the following screenshot to enable the authentication using Okta.

![Configure Bold Report OpenID Okta](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/okta/configure-boldreport-openid-Okta.png)

The fields to be saved in the Bold Reports to enable the Okta for authentication is explained as follows.
<table>
<tr>
    <td>
        Provider Name
    </td>
    <td>
        It represents the name of the authentication provider to be displayed in the login page.
    </td>
</tr>
<tr>
    <td>
        Provider Logo
    </td>
    <td>
        It represents the logo of the authentication provider to be displayed in the login page.
    </td>
</tr>
<tr>
    <td>
        Authority
    </td>
    <td>
        The format is <span style="color:#0c9dd1">https://instancename.okta.com</span> It must be the URL of your Okta instance.
    </td>
</tr>
<tr>
    <td>
        Client ID
    </td>
    <td>
        The Client ID you get after registered the Bold Reports application in Okta website.
    </td>
</tr>
<tr>
    <td>
        Client Secret
    </td>
    <td>
        The Client Secret you get after registered the Bold Reports application in Okta website.
    </td>
</tr>
<tr>
    <td>
        Identifier
    </td>
    <td>
        preferred_username
    </td>
</tr>
</table>
