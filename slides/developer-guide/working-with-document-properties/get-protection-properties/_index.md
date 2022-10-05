---
title: "Get Protection Properties"
type: docs
url: /get-protection-properties/
weight: 50
---
## **Introduction**

Aspose.Slides Cloud allows you to check whether a presentation is password protected. The method can be invoked with or without a password parameter. If the password is not provided some properties in the response are unavaliable. 

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/protection|GET|Read presentation protection properties|[GetProtectionProperties](https://apireference.aspose.cloud/slides/#/Protection/GetProtectionProperties)|
### **cURL Example**
The code example below shows how to read protection properties.
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Read protection properties with password**
```sh
curl -v -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/protection" -H "Content-Type: text/json" -H "password: mypassword" -H "Authorization: Bearer [Access Token]"
```
**Read protection properties without password**
```sh
curl -v -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/protection" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
```
{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns protection properties data.

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
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
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

#Code example will be added soon.
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
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

//Code example will be added soon.
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

#Code example will be added soon.
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}