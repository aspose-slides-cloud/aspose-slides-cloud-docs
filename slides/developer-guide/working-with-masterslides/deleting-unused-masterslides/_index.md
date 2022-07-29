---
title: "Deleting Unused Masterslides"
type: docs
url: /deleting-unused-masterslides/
weight: 40
---
## **Introduction**
Aspose.Slides Cloud API allows you to delete unused Master slides from a PowerPoint Presentation.
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/materSlides|DELETE|Delete unused Master slides from a PowerPoint Presentation|[DeleteUnusedMasterSlides]()|
|/slides/masterSlides/delete|POST|Delete unused Master slides from a PowerPoint Presentation (without using storage)|[DeleteUnusedMasterSlidesOnline]())|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```sh

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides?ignorePreserveField=true" -H "Content-Type: application/json" -H "Authorization: Bearer MyAuthToken"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
Code: 200
Returns master slides info.
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
MasterSlides result = TestUtils.SlidesApi.DeleteUnusedMasterSlides("MyPresentation.pptx", true);
Console.WriteLine(result.SlideList.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
MasterSlides result = (MasterSlides) api.deleteUnusedMasterSlides("MyPresentation.pptx", true, null, null, null);
Console.WriteLine(result.getSlideList().size());
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
$result = $api->deleteUnusedMasterSlides(self::fileName, true);
print(count($result->getSlideList()));
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)
result = api.delete_unused_master_slides("MyPresentation.pptx", true)
p(result.slide_list.length)
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

result = api.delete_unused_master_slides("MyPresentation.pptx", True)
print(len(result.slide_list))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
api.deleteUnusedMasterSlides("MyPresentation.pptx", true).then((response) => {
    console.log(response.body.slideList.length);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

result, _, e := c.SlidesApi.DeleteUnusedMasterSlides("MyPresentation.pptx", "true", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf(len(result.(MasterSlides).getSlideList()))
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)