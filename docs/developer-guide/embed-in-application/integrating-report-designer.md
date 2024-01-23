---
layout: post
title: Integrate Report Designer | Report Server | Syncfusion
description: Explains about how to integrate Bold Reporting Tools Report Designer into other application using the Bold Reports Server built-in API service.
control: report-platform
documentation: ug
---

# Integrate a Bold Reporting Tools Report Designer

Bold Report Server provides built-in restful API to integrate Bold Reporting Tools Report Designer into other applications. For this, set the `serviceAuthorizationToken`, `reportServerUrl` and `serviceUrl` property for Report Designer.

<table>
<tr>
<th>
Report Designer Property
</th>
<th>
Value
</th>
</tr>
<tr>
<td>
serviceAuthorizationToken
</td>
<td>
Pass the access token of the user. Get access token using the Bold Reports Server <a href="../../../rest-api-reference/v1.0/#operation/Authentication" target="_blank">Authentication API</a>

bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InN1
YmhhLnN1a3VtYXJhbkBzeW5jZnVzaW9uLmNvbSIsIm5hbWVpZCI6IjEiLCJ1
bmlxdWVfbmFtZSI6ImM0NWFiZmE0LTBlNjAtNGI4Yy04NWM4LWMxNTBiOGJh
MjlkNyIsIklQIjoiOjoxIiwiaXNzdWVkX2RhdGUiOiIxNjMxNzEyOTYzIiwi
bmJmIjoxNjMxNzEyOTYzLCJleHAiOjE2MzIzMTc3NjMsImlhdCI6MTYzMTcx
Mjk2MywiaXNzIjoiaHR0cDovL2xvY2FsaG9zdDo1MTc3OC9yZXBvcnRpbmcv
c2l0ZS9zaXRlOTEiLCJhdWQiOiJodHRwOi8vbG9jYWxob3N0OjUxNzc4L3Jl
cG9ydGluZy9zaXRlL3NpdGU5MSJ9.d24190nn6i2UNz_8hX1mI0JZTNO9zPX
1HYSlGClkUyw
</td>
</tr>
<tr>
<td>
reportServerUrl
</td>
<td>
Bold Reports On-Premise server URL.

<https://example.com/reporting/api/site/site1>
</td>
</tr>
<tr>
<td>
serviceUrl
</td>
<td>
Bold Reports On-Premise built-in service URL.

<https://example.com/reporting/reportservice/api/Designer>
</td>
</tr>
</table>

You can get more details of embedding with Bold Reporting Tools respective platforms as follows.

  [Angular](https://help.boldreports.com/embedded-reporting/angular-reporting/report-designer/server-integration/)

  [ASP.NET Core](https://help.boldreports.com/embedded-reporting/aspnet-core-reporting/report-designer/server-integration/)

  [ASP.NET MVC](https://help.boldreports.com/embedded-reporting/aspnet-mvc-reporting/report-designer/server-integration/)

  [ASP.NET Web Forms](https://help.boldreports.com/embedded-reporting/aspnet-web-forms-reporting/report-designer/server-integration/)

  [Javascript](https://help.boldreports.com/embedded-reporting/javascript-reporting/report-designer/server-integration/)