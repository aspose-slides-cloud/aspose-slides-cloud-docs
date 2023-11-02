---
title: "Read Protection Properties"
type: docs
url: /read-protection-properties/
weight: 10
---

## **Introduction**

Aspose.Slides Cloud allows you to check whether a presentation is password protected. The method below can be invoked with or without a password parameter. If the password is not specified, some properties in the response will not be available.

## **GetProtectionProperties**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/protection|GET|Reads protection properties of a presentation.|[GetProtectionProperties](https://apireference.aspose.cloud/slides/#/Protection/GetProtectionProperties)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of the presentation file.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Check if the **MyPresentation.pptx** document is encrypted.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**
```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read Protection Properties with a Password**
```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/protection" \
     -H "Content-Type: text/json" \
     -H "password: MyPassword" \
     -H "Authorization: Bearer MyAccessToken"
```

**Read Protection Properties without a Password**
```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/protection" \
     -H "Content-Type: text/json" \
     -H "Authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```
Protection properties data.
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ProtectionProperties protectionProperties = api.GetProtectionProperties("MyPresentation.pptx");

if (protectionProperties.IsEncrypted.Value)
    Console.WriteLine("The presentation is protected.");
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ProtectionProperties protectionProperties = api.getProtectionProperties("MyPresentation.pptx", null, null, null);

if (protectionProperties.isIsEncrypted())
    System.out.println("The presentation is protected.");
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$api = new SlidesApi(null, $config);

$response = $api->getProtectionProperties("MyPresentation.pptx");

if ($response->getIsEncrypted())
    print("The presentation is protected.");
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi.new(configuration)

response = api.get_protection_properties("MyPresentation.pptx")

if response.is_encrypted
    puts "The presentation is protected."
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi(configuration)

response = api.get_protection_properties("MyPresentation.pptx")

if response.is_encrypted:
    print("The presentation is protected.")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const response = await api.getProtectionProperties("MyPresentation.pptx");

if (response.body.isEncrypted)
    console.log("The presentation is protected.");
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"

api := asposeslidescloud.NewAPIClient(cfg)

response, _, e := api.SlidesApi.GetProtectionProperties("MyPresentation.pptx", "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

if response.GetIsEncrypted() {
    fmt.Printf("The presentation is protected.")
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %parameters = (name => "MyPresentation.pptx");
my $response = $api->get_protection_properties(%parameters);

if ($response->{is_encrypted}) {
    print("The presentation is protected.");
}
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

The Aspose.Slides for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/).
