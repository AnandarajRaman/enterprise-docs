---
layout: post
title: Adding Amazon Cognito users in Bold Reports by Oauth 2.0
description: This documentation explains about how to add Amazon Cognito user in Bold Reports using the OAuth 2.0 settings
platform: report-platform
documentation: ug
---

# Single Sign-On(SSO) with Amazon Cognito authentication in Bold Reports

Users can be added to the Bold Reports application using the Amazon Cognito provider. By importing them, you can share the reports and email exported reports with them.

## How to register the Bold Reports application in Amazon Cognito

This section explains how to perform Single Sign-On for users in Amazon Cognito with the Bold Reports application.

> This configuration has to be done in Amazon Cognito website.

## Prerequisites

* An admin account in Amazon Cognito.
* An user pool in Amazon Cognito.
* Install Bold Reports application.

## Steps to register the Bold Reports application

1. Login to the `Amazon Cognito` website with an admin account and open the console and then click `Manage User pool`.
![Click Manage User Pool](/static/assets/on-premise/images/authentication/single-sign-on/oauth/amazon-cognito/click-manage-user-pool.png)

2. Click `App Clients` under General Settings in the left side menu, and then `add` the `application`.
![Click App Client](/static/assets/on-premise/images/authentication/single-sign-on/oauth/amazon-cognito/cognito-click-app-client.png)

3. Save the App client name and click on `Create app client`.
![Create App Client](/static/assets/on-premise/images/authentication/single-sign-on/oauth/amazon-cognito/cognito-create-app-client.png)

4. Click on `Show details` to know the Client Secret.
![Cognito Client Secret](/static/assets/on-premise/images/authentication/single-sign-on/oauth/amazon-cognito/cognito-client-secret.png)

5. Make use of the `App client id` and `App client secret` as in the following screenshot.
![Congnito Credential](/static/assets/on-premise/images/authentication/single-sign-on/oauth/amazon-cognito/cognito-clientsecret-clientid.png)

6. Click on `App client settings` under App integration in the left side menu and add the `Callback URL(s)`.
![Congnito Call Back URL](/static/assets/on-premise/images/authentication/single-sign-on/oauth/amazon-cognito/congnito-call-back-url.png)

7. The Callback URL(s) must be the URI in the settings of your BoldReports application as in the following screenshot.
![Login Redirect URI](/static/assets/on-premise/images/authentication/single-sign-on/oauth/amazon-cognito/login-redirect-uri.png)

After successful registration in Amazon Cognito, save these settings in BoldReports settings page to enable this authentication.

## Enable Amazon Cognito authentication in Bold Reports

Configure the settings in Bold Reports as in the following snap to enable the authentication using Amazon Cognito.

![Configure BoldReports](/static/assets/on-premise/images/authentication/single-sign-on/oauth/amazon-cognito/configure-boldreport-amazon-coginto.png)

The fields to be saved in the Bold Reports to enable the Amazon Cognito for authentication is explained as below.

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
        It should be in the format <span style="color:#0c9dd1">https://AUTH_DOMAIN/oauth2/authorize</span> Please refer <a href="https://docs.aws.amazon.com/cognito/latest/developerguide/authorization-endpoint.html">here</a> for more details.
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
        It should be in the format <span style="color:#0c9dd1">https://AUTH_DOMAIN/oauth2/token</span> Please refer <a href="https://docs.aws.amazon.com/cognito/latest/developerguide/token-endpoint.html">here</a> for more details.
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
        It should be in the format <span style="color:#0c9dd1">https://AUTH_DOMAIN/oauth2/userinfo</span> Please refer <a href="https://docs.aws.amazon.com/cognito/latest/developerguide/userinfo-endpoint.html">here</a> for more details.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Client ID
    </td>
    <td>
        The Client ID you get after registered the Bold Reports application in Amazon Cognito website.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Client Secret
    </td>
    <td>
        The Client ID you get after registered the Bold Reports application in Amazon Cognito website.
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
        This must be the email of an admin account of Amazon Cognito website.
    </td>
</tr>
</table>
