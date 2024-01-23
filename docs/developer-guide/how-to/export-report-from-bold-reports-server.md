---
title: Export Report API | Bold Reports On-Premise Edition
description: This documentation explains how to export report using the API in the Bold Reports On-Premise Edition.
keywords: report-platform
---

# How to export the report from Bold Reports Report Server

You can export the report into any format(Excel, PDF, HMTL, PPT CSV, XML and Word) from Bold Reports Server by using the <a href="../../../rest-api-reference/v1.0/#operation/Items_ExportReport" target="_blank">Export Report API</a>.

>User must have `Read` permission for the reports.

Pass the following parameters in request body.

   `Report Id` - Report Id.

   `Server Path` - Specifies the relative URL of the report.

   `Export Type` - Export Type(PDF, Excel, Html, PPT, CSV, XML and Word).

>Access token must be passed in authorization header. To get access token, use the <a href="../../../rest-api-reference/v1.0/#operation/Authentication" target="_blank">Authentication API</a>

Here is a sample C# code to illustrate the approach.

Add the following assemblies in namespace

* `System.Runtime.Serialization.Json`
* `System.IO`
* `Newtonsoft.Json`
* `System.Net`
* `System.Collections.Generic`
* `System.Text`
> Refer `Newtonsoft.Json` assembly from [nuget package](https://www.nuget.org/packages/Newtonsoft.Json/)

```csharp
public class ApiExportReport
{

   public Guid ReportId { get; set; }

   public string ServerPath { get; set; }

   public string ExportType { get; set; }
}

public class ItemResponse
{
   public bool Status { get; set; }

   public byte[] FileContent { get; set; }

   public string StatusMessage { get; set; }

   public string ApiStatus { get; set; }

}

public static ItemResponse ExportReport()
{
   var BoldReportsURL = "https://on-premise-demo.boldreports.com";
   var itemId = Guid.Parse("b401dfc7-91f8-42a6-9f30-0b3e1323a5cc");
   var exporttypeId = "PDF";
   var itemRequest = new ApiExportReport
      {
       ReportId = itemId,
       ExportType = exporttypeId
      };
      using (var proxy = new CustomWebClient())
      {
         var ser = new DataContractJsonSerializer(typeof(ApiExportReport));
         var mem = new MemoryStream();
         ser.WriteObject(mem, itemRequest);
         proxy.Headers["Content-type"] = "application/json";
         proxy.Headers["Authorization"] = token.token_type + " " + token.access_token; // token must be passed here
         proxy.Encoding = Encoding.UTF8;
         var data = Encoding.UTF8.GetString(mem.ToArray(), 0, (int)mem.Length);
         try
         {
           var rdata = proxy.UploadString(new Uri(BoldReportsURL + "/reporting/api/site/site1/v1.0/reports/export"), "POST", data);
            var result = JsonConvert.DeserializeObject<ItemResponse>(rdata);
            File.WriteAllBytes("D://Test.pdf", result.FileContent);
            return result;
         }
         catch (WebException ex)
         {
            if (ex.Response is HttpWebResponse)
               {
                  var resp = new StreamReader(ex.Response.GetResponseStream()).ReadToEnd();
                  dynamic obj = JsonConvert.DeserializeObject(resp);
                  Console.WriteLine(obj);
               }
         }
         return null;
      }
}

class CustomWebClient : WebClient
{
   protected override WebRequest GetWebRequest(Uri uri)
   {
      var request = base.GetWebRequest(uri);
      request.Timeout = 4 * 60 * 1000; //Increase time out
      if (request is HttpWebRequest)
      {
      (request as HttpWebRequest).KeepAlive = false;
      }
      return request;
   }
}
```