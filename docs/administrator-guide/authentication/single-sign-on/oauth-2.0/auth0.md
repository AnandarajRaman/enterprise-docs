---
layout: post
title: Adding Auth0 users in Bold Reports by Oauth 2.0
description: This documentation explains about how to add Auth0 user in Bold Reports using the OAuth 2.0 settings
platform: report-platform
documentation: ug
---

# Single Sign-On(SSO) with Auth0 authentication in Bold Reports

Users can be added to the Bold Reports application using the Auth0 provider. By importing them, you can share the reports and email exported reports with them.

## How to register the Bold Reports application in Auth0

This section explains how to perform Single Sign-On for users in Auth0 with the Bold Reports application.

> This configuration has to be done in Auth0 website.

## Prerequisites

* An admin account in Auth0.
* Install Bold Reports application.

## Steps to register the Bold Reports application

1. Login to the Auth0 website with an `admin` account.
![Auth0 Login Admin Account](/static/assets/on-premise/images/authentication/single-sign-on/oauth/auth0/auth0-login-admin-account.png)

2. Click `Applications` in the left menu and then click `CREATE APPLICATION` button.
![Auth0 create Application](/static/assets/on-premise/images/authentication/single-sign-on/oauth/auth0/auth0-create-application.png)

3. Click `Regular Web Applications` and proceed with `Next`.
![Select Regular Web Application](/static/assets/on-premise/images/authentication/single-sign-on/oauth/auth0/select-regular-web-application.png)

4. The application will be registered and directed to the application details page. Use the `Client ID` and `Client Secret` in the BoldReports application.
![auth0 ClientId and Client Secret](/static/assets/on-premise/images/authentication/single-sign-on/oauth/auth0/auth0-clientid-client-secret.png)

5. Scroll down and save the `Allowed Callback URLs`.
![Auth0 Save Callback URL](/static/assets/on-premise/images/authentication/single-sign-on/oauth/auth0/auth0-save-callback-url.png)

6. This URL must be the redirect URI in the settings of your Bold Reports application as in the following screenshot.
![Lodin Redirect URI](/static/assets/on-premise/images/authentication/single-sign-on/oauth/auth0/login-redirect-uri.png)

7. Fill the details and save the changes.

After successful registration in Auth0, save these settings in Bold Reports settings page to enable this authentication.

## Enable Auth0 authentication in Bold Reports

Configure the settings in Bold Reports as in the following snap to enable the authentication using Auth0.
![Configure Bold Report Auth0](/static/assets/on-premise/images/authentication/single-sign-on/oauth/auth0/configure-boldreport-auth0.png)

The fields to be saved in the Bold Reports to enable the Auth0 for authentication is explained as follows.

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
        Authorization Endpoint
    </td>
    <td>
        It should be in the format <span style="color:#0c9dd1">https://YOUR_DOMAIN/authorize</span> Please refer <a href="https://auth0.com/docs/flows/guides/auth-code/add-login-auth-code#authorize-the-user">here</a> for more details.
    </td>
</tr>
    <tr>
    <td>
        Token Endpoint Method
    </td>
    <td>
        POST
    </td>
</tr>
</tr>
    <tr>
    <td>
        Token Endpoint
    </td>
    <td>
        It should be in the format <span style="color:#0c9dd1">https://YOUR_DOMAIN/oauth/token</span> Please refer <a href="https://auth0.com/docs/flows/guides/auth-code/add-login-auth-code#request-tokens">here</a> for more details.
    </td>
</tr>
</tr>
    <tr>
    <td>
        User Information Endpoint Method
    </td>
    <td>
        GET
    </td>
</tr>
</tr>
    <tr>
    <td>
        User Information Endpoint
    </td>
    <td>
        It should be in the format <span style="color:#0c9dd1">https://YOUR_DOMAIN/userinfo<span> Please refer <a href="https://auth0.com/docs/api/authentication?http#get-user-info">here</a> for more details.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Client ID
    </td>
    <td>
        The Client ID you get after registered the Bold Reports application in Auth0 website.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Client Secret
    </td>
    <td>
        The Client Secret you get after registered the Bold Reports application in Auth0 website.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Scopes
    </td>
    <td>
        openid, profile, email
    </td>
</tr>
</tr>
    <tr>
    <td>
        Email
    </td>
    <td>
        This must be the email of an admin account of Auth0 website.
    </td>
</tr>
</table>