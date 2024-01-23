---
layout: post
title: OAuth 2.0 in Bold Reports Enterprise Reporting
description: Describes step-by-step procedure to configure OAuth 2.0 Authentication so that the user can login to the Bold Reports application
platform: report-platform
documentation: ug
---

# Single Sign-On(SSO) with OAuth 2.0 authentication in Bold Reports

The Bold Reports application can be configured with OAuth 2.0 for Single Sign-On(SSO), so that users can log in directly to the Bold Reports application after authenticating using OAuth 2.0.

## Prerequisites

1. An account with an OAuth 2.0 provider.

2. Register the Bold Reports application in the OAuth 2.0 provider.

## Steps to configure OAuth 2.0 in Bold Reports

1. To configure the OAuth 2.0 connection details, click the settings option in the Report Server left-side panel.

2. Navigate to the Authentication tab and OAuth 2.0 as shown in the following image
![Authentication](/static/assets/on-premise/images/authentication/single-sign-on/oauth/authentication-settings.png)

3. Provide the following details in the OAuth 2.0 settings of Bold Reports application.
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
        It is the endpoint in the provider to authorize the user.
    </td>
</tr>
    <tr>
    <td>
        Token Endpoint Method
    </td>
    <td>
        It represents the request type to access the token endpoint.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Token Endpoint
    </td>
    <td>
        It is the endpoint in the provider that generates the token.
    </td>
</tr>
</tr>
    <tr>
    <td>
        User Information Endpoint Method
    </td>
    <td>
        It is the endpoint in the provider used to get the user details.
    </td>
</tr>
</tr>
    <tr>
    <td>
        User Information Endpoint
    </td>
    <td>
        It represents the request type to access the user information endpoint.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Client ID
    </td>
    <td>
        It is an unique identifier provided to each of the applications while registering in the providers.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Client Secret
    </td>
    <td>
        It is a secret key that is used to authorize the applications.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Scopes
    </td>
    <td>
        It is comma separated lists of identifiers that specifies the access privileges that are being requested from the provider.
    </td>
</tr>
</tr>
    <tr>
    <td>
        Email
    </td>
    <td>
        This must be the email of an admin account of the providers.
    </td>
</tr>
</table>

   ![Oauth Authentication](/static/assets/on-premise/images/authentication/single-sign-on/oauth/oauth-authentication.png)

The previous mentioned similar steps are applicable to configure the OAuth 2.0 in User Management Server by logging into the URL `{Bold Reports URL}/ums/administration/authentication` with admin credential.

Following are the list of few OAuth 2.0 providers and that explains how to connect with the Bold Reports application.

* [Amazon Cognito](./../oauth-2.0/amazon-cognito/)
* [Auth0](./../oauth-2.0/auth0/)
* [Okta](./../oauth-2.0/okta/)
* [OneLogin](./../oauth-2.0/onelogin/)

The OAuth 2.0 is provided in both the Bold Reports sites and User Management Server. OAuth 2.0 can be handled for each sites individually in the settings page by disabling the option as in the following screenshot.
![Oauth Group Setting](/static/assets/on-premise/images/authentication/single-sign-on/oauth/enableoauth.png)

## Set OAuth 2.0 as Default Authentication

OAuth 2.0 can be set as default authentication when [OAuth 2.0](#steps-to-configure-oauth-20-in-bold-reports) settings is enabled and saved. Follow the below steps.
1. In settings page, click on Authentication tab and select General.
2. Enable the option **Enable Default Authentication** and select the **OAuth 2.0** in default authentication provider as in the following screenshot.
![Oauth Default Setting](/static/assets/on-premise/images/authentication/single-sign-on/oauth/oauth-default-authentication.png)

### Disabling OAuth 2.0 Settings

When OAuth 2.0 is set as default authentication and try to disable the [OAuth 2.0 settings](#steps-to-configure-oauth-20-in-bold-reports) will display below pop-up. Proceeding by clicking `Yes` will disable the [OAuth 2.0 default authentication](#set-oauth-20-as-default-authentication).

![Oauth Default Setting Popup](/static/assets/on-premise/images/authentication/single-sign-on/oauth/oauth-default-authentication-popup.png)

### Bypassing OAuth 2.0 Authentication

Use the below custom login URL to login as normal user that is not from OAuth, when [OAuth 2.0 default authentication](#set-oauth-20-as-default-authentication) is enabled.
>**`{Bold Reports URL}/reporting/site/{tenant-name}/login?use_default_authentication=false`**