---
title: List of Items using the API in Bold Reports On-Premise
description: This documentation explains about how to get list of items using the API in the Bold Reports On-Premise Edition.
keywords: report-platform
---

# How to get the list of items from Bold Reports Report Server

You can get the list of items(Category, Reports, Dataset, Data source, and Schedule) from Bold Reports by using the <a href="../../../rest-api-reference/v1.0/#operation/Items_GetItems" target="_blank">Get Items API</a>.

For this, pass the following parameters in query parameters.

   `itemType` - Pass the item type(Category, Reports, Dataset, Data source, and Schedule).

   `serverPath` - Category Path.

>Access token must be passed in authorization header. To get access token, use the <a href="../../../rest-api-reference/v1.0/#operation/Authentication" target="_blank">Authentication API</a> or [Embed Secret Key API](../../../developer-guide/how-to/generate-authorization-token-for-user-by-using-embed-secret-key-api/).

Here is a sample C# code to illustrate the approach.

Add the following assemblies in namespace

* `System.IO`
* `Newtonsoft.Json`
* `System.Net`
* `System.Collections.Generic`
* `System.Text`
> Refer `Newtonsoft.Json` assembly from [nuget package](https://www.nuget.org/packages/Newtonsoft.Json/)

```csharp
public class ApiItems
{
   public bool CanRead { get; set; }

   public bool CanWrite { get; set; }

   public bool CanDelete { get; set; }

   public bool CanSchedule { get; set; }

   public bool CanDownload { get; set; }

   public bool CanOpen { get; set; }

   public bool CanMove { get; set; }

   public bool CanCopy { get; set; }

   public bool CanClone { get; set; }

   public bool CanCreateItem { get; set; }

   public Guid? CategoryId { get; set; }

   public string CategoryName { get; set; }

   public int ModifiedById { get; set; }

   public string CreatedByDisplayName { get; set; }

   public int CreatedById { get; set; }

   public string ModifiedByFullName { get; set; }

   public string ItemLocation { get; set; }

   public int ItemType { get; set; }

   public Guid Id { get; set; }

   public string CreatedDate { get; set; }

   public string ModifiedDate { get; set; }

   public DateTime ItemModifiedDate { get; set; }

   public DateTime ItemCreatedDate { get; set; }

   public Guid ReportId { get; set; }

   public string ReportName { get; set; }

   public string Name { get; set; }

   public string Description { get; set; }

}

public static List<ApiItems> GetItems()
{
   var BoldReportsURL = "https://on-premise-demo.boldreports.com";
   var itemType = "Report";

   using (var proxy = new CustomWebClient())
   {
     proxy.Headers["Content-type"] = "application/json";
     proxy.Headers["Authorization"] = token.token_type + " " + token.access_token; // token must be passed here
     proxy.Encoding = Encoding.UTF8;

     try
      {
         var rdata = proxy.DownloadString(new Uri(BoldReportsURL + "/reporting/api/site/site1/v1.0/items?itemType=" + itemType));
         var response = JsonConvert.DeserializeObject<List<ApiItems>>(rdata);
         return response;
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
