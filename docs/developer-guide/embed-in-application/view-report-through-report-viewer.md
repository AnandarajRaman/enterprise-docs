---
layout: post
title: Bold Report Server reports | Bold Reports | Syncfusion
description: Explains about rendering Bold Reports Server deployed RDL reports using the Bold Reporting Tools Report Viewer with the help of embedded Report Service.
control: report-platform
documentation: ug
---

# Report Server report using the Bold Reporting Tools Report Viewer

Bold Report Server provides build-in Restful API to embed Report Server reports using the Bold Reporting Tools Report Viewer. For this, set the `serviceAuthorizationToken`, `serverurl`, `reportServiceUrl` and `reportPath` property for Report Viewer.

<table>
<tr>
<th>
Report Viewer Property
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
Pass the access token of the user. Get access token using the Bold Reports Server <a href="../../../rest-api-reference/v1.0/#operation/Authentication" target="_blank">Authentication API</a>.

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
serverurl
</td>
<td>
Bold Reports On-Premise server URL.

<https://example.com/reporting/api/site/site1>
</td>
</tr>
<tr>
<td>
reportServiceUrl
</td>
<td>
Bold Reports On-Premise built-in service URL.

<https://example.com/reporting/reportservice/api/Viewer>
</td>
</tr>
<tr>
<td>
reportPath
</td>
<td>
Path of report, which is added on server.

{/category name}/{report name}
</td>
</tr>
</table>

   > You can also load the report using the Guid instead of report location. Set the Guid of the report in `reportPath` as like as `reportPath: ‘91f24bf1-e537-4488-b19f-b37f77481d00’`. You can use Bold Report Server  <a href="../../../rest-api-reference/v1.0/#operation/Items_GetItems" target="_blank">Get Items API</a> and find the Guid of the report.

You can get more details of embedding with Bold Reporting Tools respective platforms as follows.

  [Angular](https://help.boldreports.com/embedded-reporting/angular-reporting/report-viewer/reportserver-report/)

  [ASP.NET Core](https://help.boldreports.com/embedded-reporting/aspnet-core-reporting/report-viewer/reportserver-report/)

  [ASP.NET MVC](https://help.boldreports.com/embedded-reporting/aspnet-mvc-reporting/report-viewer/reportserver-report/)

  [ASP.NET Web Forms](https://help.boldreports.com/embedded-reporting/aspnet-web-forms-reporting/report-viewer/reportserver-report/)

  [Javascript](https://help.boldreports.com/embedded-reporting/javascript-reporting/report-viewer/reportserver-report/)

  [React](https://help.boldreports.com/embedded-reporting/react-reporting/report-viewer/reportserver-report/)

  [UWP](https://help.boldreports.com/embedded-reporting/uwp-reporting/report-viewer/reportserver-report/)

  [WPF](https://help.boldreports.com/embedded-reporting/wpf-reporting/report-viewer/reportserver-report/)