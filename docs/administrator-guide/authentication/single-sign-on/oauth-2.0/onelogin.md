---
layout: post
title: Adding OneLogin users in Bold Reports by Oauth 2.0
description: This documentation explains about how to add OneLogin user in Bold Reports using the OAuth 2.0 settings
platform: report-platform
documentation: ug
---

# Single Sign-On(SSO) with OneLogin authentication in Bold Reports

Users can be added to the Bold Reports application using the OneLogin provider. By importing them, you can share the reports and email exported reports with them.

## How to register the Bold Reports application in OneLogin

This section explains how to perform Single Sign-On(SSO) for users in OneLogin with Bold Reports application.

>This configuration has to be done in OneLogin website.

### Prerequisites

* An admin account in OneLogin.

* Install Bold Reports application.

#### Steps to register the Bold Reports application

1. Login to the OneLogin website with the admin account.

2. Click on `Applications` in the header menu.

   ![Application page](/static/assets/on-premise/images/authentication/single-sign-on/oauth/onelogin/oneloginadmin.png)

3. Click on `Add App` button.
   ![Add Application page](/static/assets/on-premise/images/authentication/single-sign-on/oauth/onelogin/oneloginaddapp.png)

4. Type the word `OpenId Connect`or `oidc` in the search box and click on the result.

    ![Openidconnect](/static/assets/on-premise/images/authentication/single-sign-on/oauth/onelogin/openidconnect.png)

5. Type the application name and click on `Add App`.

6. Save the application name in the `Display Name`.

   ![Applicationname](/static/assets/on-premise/images/authentication/single-sign-on/oauth/onelogin/oneloginname.png)

7. Click the `Configuration` tab and save the `Redirect URI's` and `Login Url`. For Bold Reports mobile application, use the `Mobile App Redirect URI` and use the `Redirect URI` for the web application.

   ![Redirect URI](/static/assets/on-premise/images/authentication/single-sign-on/oauth/onelogin/onelogin-save-redirect-uri.png)

8. The `Redirect URI` and `Login URL` is found under the `OpenID Connect` settings of your Bold Reports application as in the following screenshot.

   ![Redirecturi in setting](/static/assets/on-premise/images/authentication/single-sign-on/oauth/onelogin/login-redirect-uri.png)

9. Click `SSO` tab, you will find the `Client ID` and `Client Secret` and use it in the Bold Reports application.

   ![OneLoginClient details](/static/assets/on-premise/images/authentication/single-sign-on/oauth/onelogin/onelogin-client-secret.png)

After successful registration in OneLogin, save these settings in Bold Reports settings page to enable this authentication.

## Enable OneLogin authentication in Bold Reports

Configure the settings in Bold Reports as in the following snap to enable the authentication using OneLogin.

  ![OneLogin settings](/static/assets/on-premise/images/authentication/single-sign-on/oauth/onelogin/configure-boldreport-onelogin.png)

The fields to be saved in the Bold Reports to enable the OneLogin for authentication is explained as below.

<table>

<tr>
<td>Provider Name</td>
<td>It represents the name of the authentication provider to be displayed in the login page.</td>
</tr>

<tr>
<td>Provider Logo</td>
<td>It represents the logo of the authentication provider to be displayed in the login page.</td>
</tr>

<tr>
<td>Authorization Endpoint</td>
<td>It should be in the format <span style="color:#0c9dd1">https://subdomain.onelogin.com/oidc/auth</span> Please refer <a href="https://developers.onelogin.com/openid-connect/api/authorization-code">here</a> for more details.
</td>
</tr>

<tr>
<td>Token Endpoint Method</td>
<td>POST</td>
</tr>

<tr>
<td>Token Endpoint</td>
<td>It should be in the format <span style="color:#0c9dd1">https://subdomain.onelogin.com/oidc/token</span> Please refer <a href="https://developers.onelogin.com/openid-connect/api/authorization-code-grant">here</a> for more details.</td>
</tr>

<tr>
<td>User Information Endpoint Method</td>
<td>GET</td>
</tr>

<tr>
<td>User Information Endpoint</td>
<td>It should be in the format <span style="color:#0c9dd1">https://subdomain.onelogin.com/oidc/me</span> Please refer <a href="https://developers.onelogin.com/openid-connect/api/user-info">here</a> for more details.
</tr>

<tr>
<td>Client ID</td>
<td>The Client ID you get after registered the Bold Reports application in OneLogin website.</td>
</tr>

<tr>
<td>Client Secret</td>
<td>The Client Secret you get after registered the Bold Reports application in OneLogin website.</td>
</tr>

<tr>
<td>Scopes</td>
<td>openid, profile, email</td>
</tr>

<tr>
<td>Email</td>
<td>This must be the email of an admin account of OneLogin website.</td>
</tr>

</table>