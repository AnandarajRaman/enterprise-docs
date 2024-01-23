---
title: User authorization token by Embed Secret key API
description: This documentation explains about how to generate user authorization token by using the embed secret key API in the Bold Reports Enterprise Reporting.
keywords: report-platform
---

# How to generate the authorization token by using the Embed Secret Key API

You can generate the authorization token for the user in Bold Reports by using the Embed Secret Key API. For this, pass the following parameters in request body.

   `username` - Email address of the user.

   `grant_type` - This type of credentials are used to authorize the request for an access token. Valid values: **embed_secret**.

   `embed_nonce` - A random string value that restricts attackers from hacking. Example **5ff24040-cd74-42cf-a168-57f8cb7dafed**.

   `timestamp` - The current time as UNIX timestamp. Example: **1583934776**

   `embed_signature` -  By using the `username`, `embed_nonce`, `timestamp` and the `embed secret key`(which can be generated from Bold Reports Reports server Embed settings) values, the `embed_signature` value can be generated using the `HMACSHA256` algorithm.

Here is a sample C# code to illustrate the approach.

Add the following assemblies in a namespace:

* `System.Collections.Generic`
* `System.Net.Http`
* `Newtonsoft.Json`
* `System.Security.Cryptography`
* `System.Net`

> Refer `Newtonsoft.Json` assembly from [nuget package](https://www.nuget.org/packages/Newtonsoft.Json/).

## .NET,.NET Core, and .NET Framework

```csharp
public class Token
{
    public string access_token { get; set; }

    public string token_type { get; set; }

    public string expires_in { get; set; }

    public string email { get; set; }

    public string error { get; set; }

    public string error_description { get; set; }

}

private static string tokenurl = "/reporting/api/site/site1/token";
private static string boldReportsUrl = "https://on-premise-demo.boldreports.com"; // Provide your Bold Reports URL
private static string username = "guest@boldreports.com"; // Provide your Email ID
private static string nonce = Guid.NewGuid().ToString();
private static string timeStamp = DateTimeToUnixTimeStamp(DateTime.UtcNow).ToString();
private static string secretCode = "lettffAEI0FtKDGdrDekEv7WUbHwOwO"; // Provide your embed secret key value from the Bold Reports Report Server Embed Settings.

public static void Main(string[] args)
{
    ServicePointManager.SecurityProtocol = SecurityProtocolType.Tls | SecurityProtocolType.Tls11 | SecurityProtocolType.Tls12; // This is required while running the Bold Reports from Azure App Service
    GetToken();
}

public static Token GetToken()
{
    var client = new HttpClient();
    client.BaseAddress = new Uri(boldReportsUrl);
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.ConnectionClose = true;
    string embedMessage = "embed_nonce=" + nonce + "&user_email=" + username + "&timestamp=" + timeStamp;
    string signature = SignURL(embedMessage.ToLower(), secretCode);

    var content = new FormUrlEncodedContent(new[]
    {
       new KeyValuePair<string, string>("grant_type", "embed_secret"),
       new KeyValuePair<string, string>("username", username),
       new KeyValuePair<string, string>("embed_nonce", nonce),
       new KeyValuePair<string, string>("embed_signature", signature),
       new KeyValuePair<string, string>("timestamp", timeStamp)
    });

    var result = client.PostAsync(tokenurl, content).Result;

    string resultContent = result.Content.ReadAsStringAsync().Result;

    if (JsonConvert.DeserializeObject<Token>(resultContent)?.error == "authorization_failed")
    {
        Console.WriteLine("authorization_failed: " + JsonConvert.DeserializeObject<Token>(resultContent)?.error_description);
        Console.ReadLine();
        Environment.Exit(-1);
    }

    return JsonConvert.DeserializeObject<Token>(resultContent);
}

public static double DateTimeToUnixTimeStamp(DateTime dateTime)
{
    DateTime unixStart = new DateTime(1970, 1, 1, 0, 0, 0, 0, System.DateTimeKind.Utc);
    long unixTimeStampInTicks = (dateTime.ToUniversalTime() - unixStart).Ticks;
    return unixTimeStampInTicks / TimeSpan.TicksPerSecond;
}

public static string SignURL(string embedMessage, string secretcode)
{
    var encoding = new UTF8Encoding();
    var keyBytes = encoding.GetBytes(secretcode);
    var messageBytes = encoding.GetBytes(embedMessage);
    using (var hmacsha1 = new HMACSHA256(keyBytes))
        {
            var hashMessage = hmacsha1.ComputeHash(messageBytes);
            return Convert.ToBase64String(hashMessage);
        }
}
````

After the token is generated, use the generated token by attaching in the request header (Authorization) for all subsequent API calls to authenticate the requests.

## See also

* [How to generate the authorization from Report server UI](../generate-access-token-for-bold-reports-server/)

* [How to generate the access token for Bold Reports Report Server using credentials?](../generate-access-token-for-bold-reports-server-using-credentials/)
