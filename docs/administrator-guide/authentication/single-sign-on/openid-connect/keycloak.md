---
layout: post
title: Integrating Bold Reports with Keycloak via OpenID Connect.
description: This documentation explains about how to add keycloak in Bold Reports using the OpenId Connect settings
platform: report-platform
documentation: ug
---

# Keycloak support for SSO authentication

Keycloak is an open-source identity and Access Management solution designed for modern applications and services.

This section explains how to perform single sign-on for users in Keycloak with the Bold Reports application using Open ID Connect.

## How to register the Bold Reports application in Keycloak

> **NOTE:** This configuration has to be done on the Keycloak website.

## Prerequisites

* An admin account in Keycloak.
* Install the Bold Reports application.

### Steps to register the Bold Reports application

1. Log in to the Keycloak website with an admin account.

    ![keycloak-admin-console](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-admin-console.png)

2. Navigate to the Security admin console, then to the Clients page, and select the Create client option.

    ![keycloak-create-client](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-client.png)

3. On the `Create Client` page, enter the client ID and select the `openid-connect` as the client protocol. Then, configure the required settings as shown in the below images and save the changes:

    ![keycloak-create-client](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-application.png)

    ![keycloak-create-client](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-config.png)

    ![keycloak-login](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-login.png)

4. Once the client has been created, you can make updates in the settings section.

    ![keycloak-settings](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-settings.png)

<table>
<tr>
    <td>
        Implicit Flow Enabled
    </td>
    <td>
        On
    </td>
</tr>
<tr>
    <td>
        Valid redirect URIs
    </td>
    <td>
        <b>URL Format:</b> https://{domain}/signin-oidc</br></br>
        <b>Example:</b> https://example.com/signin-oidc</br></br>
        <b>Note:</b> The Redirect URI is found under the OpenID Connect settings of your Bold Reports application, as in the following screenshot.
    </td>
</tr>
</table>

> Note: When configuring the access type, you can set it to `confidential`.
> After successful registration with Keycloak, save these settings in the Bold Reports settings page to enable this authentication.

### Enable Keycloak authentication support in Bold Reports

Configure the settings in Bold Reports as shown in the following screenshots to enable the authentication using Keycloak.

![keycloak-report-settings](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-report-settings.png)

![keycloak-report-save](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-save.png)

The fields required to be saved in Bold Reports to enable Keycloak for authentication are explained as follows:

<table>
<tr>
    <td>
        Enable Open ID Connect
    </td>
    <td>
        Enabled
    </td>
</tr>
<tr>
    <td>
        Provider Name
    </td>
    <td>
        It represents the name of the authentication provider to be displayed on the login page.
    </td>
</tr>
<tr>
    <td>
        Provider Logo
    </td>
    <td>
        It represents the logo of the authentication provider to be displayed on the login page.
    </td>
</tr>
<tr>
    <td>
        Authority
    </td>
    <td>
        It must be the URL of your Keycloak instance.</br></br>
        URL format: https://{host}/auth/realms/{realm}</br></br>
        <b>Note:</b>The Authority URL only accepts HTTPS, and Keycloak should be configured in HTTPS.
    </td>
</tr>
<tr>
    <td>
        Client ID
    </td>
    <td>
        The client ID is the one you get after registering the Bold Reports application on the Keycloak website.</br></br>
        <b>Note:</b> Client IDs are available on the Clients page of the Keycloak website.
    </td>
</tr>
<tr>
    <td>
        Client Secret
    </td>
    <td>
        The client secret is the one you get after registering the Bold Reports application on the Keycloak website.</br></br>
        <b>Note:</b> Client secrets are available in the Credentials section of the Client Details page.
    </td>
</tr>
<tr>
    <td>
        Identifier
    </td>
    <td>
        The Bold Reports application requires an email address to login to the application.</br></br>
        So, please set the identifier as the email.</br></br>
        <b>Note:</b> All accounts in Keycloak should have a valid email address.
    </td>
</tr>
<tr>
    <td>
        Logout Endpoint
    </td>
    <td>
        It is the endpoint on the Keycloak website that signs the user out.
    </td>
</tr>
</table>

### Login with Keycloak

1. Go to the login page and select the Keycloak option to log in.

    ![keycloak-report-login](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-reports-login-page.png)

2. Fill in the username and password on the Keycloak login screen and sign in.

    ![keycloak-initial-login](/static/assets/on-premise/images/authentication/single-sign-on/openid-connect/keycloak/keycloak-initial-login.png)