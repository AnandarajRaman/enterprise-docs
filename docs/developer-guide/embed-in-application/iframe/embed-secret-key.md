---
layout: post
title: Embed report using embed secret key | Bold Reports
description: This documentation explains how to embed report in an iframe using Embedded secret key of Bold Reports application.
platform: report-platform
documentation: ug
---

# Embed report using embed secret key

This section explains how to render the report into the web applications by using Single sign-on(SSO) authentication.

For this, you have to frame the embed URL by using embed secret key. To get embed secret key, please follow below steps:

1. Go to the settings page and click Embed. Enable the Enable embed authentication under that page.
    ![Embed settings page](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/embed-settings.png)
2. Click `Generate Secret` button.
    ![Generate secret button](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/generate-secret-button.png)
3. On clicking it, the secret key will be generated. Save the secret key safely, as it will not be able to retrieve or restore this generated secret.
    ![Copy secret key](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/copy-secret-key.png)
4. Once the secret key is generated, it can be reset by clicking the `Reset Secret` button.
    ![Reset secret Button](/static/assets/on-premise/images/embed-server-reports-in-application/iframe/reset-secret-button.png)
    > Resetting this code will break the previously working embedded reports

The embed URL should be in the below format,
`{report URL}/{embed parameters}&embed_signature={signature}`

<table>
<tr>
<td>

Example: `http://localhost:51778/reporting/en-us/site/site1/reports/5ff24040-cd74-42cf-a168-57f8cb7dafed/Sample%20Reports/Invoice&embed_nonce=3e253410-1a82-4fb3-a337-122a8007dafc&embed_user_email=test@syncfusion.com&embed_report_views_edit=true&embed_report_views=true`
`&embed_report_export=true&embed_report_comments=true&embed_timestamp=1583928213&embed_expirationtime=100`
`&embed_signature=W1oqFY6MvJ2lxCwCwLHWihSd19jPfzr`

</td>
</tr>
</table>

Please find the details of the parameter in the URL as below,
<table>
<tr>
<th>
Parameter
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
report URL
</td>
<td>
URL of the report to be embed.
</td>
</tr>
<tr>
<td>
embed parameters
</td>
<td>
Parameters required to embed the report with SSO.
</td>
</tr>
<tr>
<td>
signature
</td>
<td>
Authorized key for the report to be embed
</td>
</tr>
</table>

## Parameters to generate the signature in the embed URL

The below values are necessary to form the signature

<table>
<tr>
<th>
Parameter
</th>
<th>
Mandatory
</th>
<th>
Description
</th>
<th>
Example
</th>
</tr>
<tr>
<td>

`embed_nonce`

</td>
<td>
Yes
</td>
<td>
Random string that restricts the URL reconstruction or attacks from the hackers
</td>
<td>

`5ff24040-cd74-42cf-a168-57f8cb7dafed`

</td>
</tr>
<tr>
<td>

`embed_user_email`

</td>
<td>
Yes
</td>
<td>
The email id of the user.
</td>
<td>

`test@syncfusion.com`

</td>
</tr>
<tr>
<td>

`embed_report_views`

</td>
<td>
No
</td>
<td>
This value makes you to check the views in the embedded report.
</td>
<td>
true
</td>
</tr>
<tr>
<td>

`embed_report_views_edit`

</td>
<td>
No
</td>
<td>
This value allows you to perform the actions such as save view, update view and delete views in the embedded report.
</td>
<td>
true
</td>
</tr>
<tr>
<td>

`embed_report_export`

</td>
<td>
No
</td>
<td>
The export option to various format of the report and widget in embedded report is displayed based on this value.
</td>
<td>
true
</td>
</tr>
<tr>
<td>

`embed_report_comments`

</td>
<td>
No
</td>
<td>
The actions related to comments such as post, edit, delete, reply, watch, unwatch, posting the image and user mention list options can be performed in report based on this value.
</td>
<td>
true
</td>
</tr>
<tr>
<td>

`embed_timestamp`

</td>
<td>
Yes
</td>
<td>
The current time as UNIX time stamp. The embed URL formed is valid for 5 minutes from this embed time stamp.
</td>
<td>

`1583934776`

</td>
</tr>
<tr>
<td>

`embed_expirationtime`

</td>
<td>
No
</td>
<td>
Set the duration for the token to be alive. It must be represented in seconds. The default time is 86400 s and the maximum is 604800 s.
</td>
<td>

`604800`

</td>
</tr>
</table>

## Generating the signature for the embed URL

<table>
<td>

`embed_signature`

</td>
<td>
Yes
</td>
<td>
A signature generated using the secret code to authenticate the embed URL.
</td>
<td>

`W1oqFY6MvJ2lxCwCwLHWihSd`
`19jPfzr`

</td>
</tr>
</table>

The embed parameter should be formed as in the below format.

<table>
<tr>
<td>

`embed_nonce=5ff24040-cd74-42cf-a168-57f8cb7dafed&embed_user_email=test@syncfusion.com&embed_report_views_edit=true&embed_report_views=true&embed_report _export=true`
`&embed_report _comments=true& &embed_timestamp=1583935418&embed_expirationtime=100`

</td>
</tr>
</table>

The above formed embed parameter is signed with the secret code generated in the Bold Reports server using the HMACSHA256 algorithm and the generated signed key will be appended with the embed URL as `embed_signature`.

You can download the sample from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Embedreportusingsso1343889418).