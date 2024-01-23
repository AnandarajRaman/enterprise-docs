---
layout: post
title: Get an embed code of report from Bold Reports On-Premise
description: Explains about how to get an embed code of report from the Bold Reports On-Premise Edition to use it in your web application.
platform: report-platform
documentation: ug
---

# Get an embed code of report

This section explains how to get an embed code of report from the Bold Reports On-Premise to use it in your web application page. Embed server reports provide the option to render the reports into other web applications. Follow these steps to embed server reports into other web applications.

## Getting an embed URL

1. To get the embed URL, click the `Share icon` of the respective report.

   ![Share Icon](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/share-option.png)

2. Click the `Get Embed Code` link in the `Share` dialog box.

    ![Disabled Comment](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/get-embed-code-link.png)

3. By Default, Reports Comments and Views options are disabled. You can enable this option by sliding the button given in `Embed` dialog box.

    ![Sliding Option](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/sliding-option.png)

    <table>
    <tr>
      <td>
       Report Comments
      </td>
      <td>
       Report comment panel would be shown in embedded view, if enabled this parameter.
      </td>
    </tr>
    <tr>
      <td>
       Views
      </td>
      <td>
       Report views panel would be shown in embedded view, if enabled this parameter.
      </td>
    </tr>
</table>  

## Steps to embed report using the embed URL

1. Copy the embed URL by clicking the copy icon from the `Embed Code` dialog box.
    ![Embed URL](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/embed-code-copy-option.png)

2. Embed the copied URL into other web application with the help of the following code snippet.

  ```html
  <html>
  <head>
    <meta content="text/html;charset=utf-8" http-equiv="Content-Type">
    <meta content="utf-8" http-equiv="encoding">
  </head>
  <body>
    <div id="report">
  <iframe src='http://localhost:61405/reporting/en-us/site/site1/reports/81cd3e3e-d611-4ef8-9762-8012bae416be/Sample%20Reports/Grouping%20Aggregate?isembed=true' id='report-frame' width='100%' height='720px' allowfullscreen frameborder='0'></iframe>
   </div>
   </body>
  </html>
  ```

Run the web application, it will show the login window or report based on the type of the report. Click `login` and login with valid user credentials and the report will render automatically.
  ![Embed Login Page](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/login.png)

  ![Embed Report](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/report-loaded.png)

### Public embedding

If you want to embed the report without user authentication, then make the report public and embed it. The public report will be rendered automatically without credentials. You cannot enable the comments panel for public report embedding.

>Embedding the public report will not work when public report setting is disabled. Learn more about the report settings [here](./../../../../administrator-guide/manage-app-settings/report-settings/).

### Private embedding

Private reports can be embedded, which are accessible to users in the Bold Reports, who has the read permission, and these reports would be requested to login into Bold Report server before rendering. So, embedded report will show the login page whenever private reports are embedded and the user is not authenticated yet.

>By default, report access mode will be set to private until it is changed to the public by the owner of the report.