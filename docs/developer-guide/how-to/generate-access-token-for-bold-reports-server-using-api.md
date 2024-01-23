---
title: How to get authorization token using API in report server
description: This documentation explains about how to generate the access token using API in the Bold Reports On-Premise Edition.
keywords: report-platform
---

# How to generate the access token using API from the postman

You can generate the access token for the user in Bold Reports by using API. For this, pass the following parameters in request body.

 1. Open the `Postman` application and create a new `POST` Http request.
 2. In request URL, provide the Report Server URL and `reporting/api/site/{tenant-name}/token` for generating the access [token](../../../rest-api-reference/v1.0/#operation/Authentication).
 3. In body section, you need to add `username`, `password`, and `grant_type`. provide the value as a user login details and `grant_type` as a `password`.
  ![Access token](/static/assets/on-premise/images/how-to/rest-api/token.png)
 4. Click `Send` and access token is generated in response.
 ![Connection types](/static/assets/on-premise/images/how-to/rest-api/access-token.png)