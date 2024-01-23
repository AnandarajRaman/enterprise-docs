---
title: User Token API | Bold Reports On-Premise Edition
description: This documentation explains about how to get user token using the API in the Bold Reports On-Premise Edition.
keywords: report-platform
---

# How to generate the access token for Bold Reports Report Server using credentials

You can generate the access token for the user in Bold Reports by using the <a href="../../../rest-api-reference/v1.0/#operation/Authentication" target="_blank">Authentication API</a>. To achieve this, pass the following parameters.

   `username` - Email address of the user.

   `password` - Password of the user.

   `grant_type` - This type of credentials are used to authorize the request for an access token. Valid values: **password**.

## .NET,.NET Core, and .NET Framework

Use `HTTPClient` with `ASP.NET Core`, `ASP.NET MVC`, and `ASP.NET Web Forms` applications to interact with RESTful APIs. Refer to the following code to generate the authorization using the credential.

```csharp
 public class TokenHelper
    {
        public string GenerateToken()
        {
            System.Net.ServicePointManager.SecurityProtocol |= System.Net.SecurityProtocolType.Tls11 | System.Net.SecurityProtocolType.Tls12;
            string userName = "guest@boldreports.com";
            string password = "demo";

            using (var client = new HttpClient())
            {
                client.DefaultRequestHeaders.Accept.Clear();

                var content = new FormUrlEncodedContent(new[]
                {
                new KeyValuePair<string, string>("grant_type", "password"),
                new KeyValuePair<string, string>("username", userName),
                new KeyValuePair<string, string>("password", password)
                  });

                var result = client.PostAsync("https://on-premise-demo.boldreports.com/reporting/api/site/site1/token", content).Result;
                string resultContent = result.Content.ReadAsStringAsync().Result;
                var token = JsonConvert.DeserializeObject<Token>(resultContent);

                return token.token_type + " " + token.access_token;
            }
        }
    }
    public class Token
    {
        public string access_token { get; set; }

        public string token_type { get; set; }

        public string expires_in { get; set; }

        public string userName { get; set; }

        public string serverUrl { get; set; }

        public string password { get; set; }
    }
```

## JavaScript

Use `Ajax` to interact with RESTful APIs. Refer to the following code to generate the authorization using the credential.

```js
   <script type="text/javascript">
         $(function () {
               var dataValue = "";
               var apiRequest = new Object();
               apiRequest.password = "demo";
               apiRequest.userid = "guest@boldreports.com";
               $.ajax({
                  type: "POST",
                  url: "https://on-premise-demo.boldreports.com/reporting/api/site/site1/get-user-key",
                  data: apiRequest,
                  success: function (data) {
                     dataValue = data.Token;
                     var token = JSON.parse(dataValue);
                  }
               });
         });
   </script>
```

## NODE JS

Use `Http` module to interact with RESTful APIs. Refer to the following code to generate the authorization using the credential.

```js
function token(res, callback, callbackInput) {
  var postData = JSON.stringify({
    userid: 'guest@boldreports.com',
    password: 'demo'
  })

  var options = {
    method: 'POST',
    host: 'on-premise-demo.boldreports.com',
    port: 443,
    path: '/reporting/api/site/site1/get-user-key',
    headers: {
      'Content-Type': 'application/json',
      'Content-Length': postData.length
    }
  };

  var request = gethttp().request(options, function (response) {
    var data = '';

    response.on('data', function (chunk) {
      data += chunk;
    });

    response.on('end', function () {
      var tokenData = JSON.parse(data);
      var tokenObject = JSON.parse(tokenData.Token);
      callbackFunction(res, tokenObject.token_type + ' ' + tokenObject.access_token, callback, callbackInput);
    });
  });

  request.on('error', error => {
    console.error(error)
  })

   request.end();
}
```

See also

* [How to generate the authorization from Report Server UI](../generate-access-token-for-bold-reports-server/)

* [How to generate the authorization token by using Embed Secret Key API](../generate-authorization-token-for-user-by-using-embed-secret-key-api/)
