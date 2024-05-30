---
title: "Delete Unused Layout Slides"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- design
- slide
- layout
- delete layout
type: docs
url: /delete-unused-layout-slides/
weight: 40
---

## **Introduction**
Aspose.Slides Cloud API has methods to delete unused LayoutSlides from a PowerPoint Presentation
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/layoutSlides|DELETE|Delete unused LayoutSlides from a PowerPoint Presentation|[DeleteUnusedLayoutSlides](https://apireference.aspose.cloud/slides/#/LayoutSlides/DeleteUnusedLayoutSlides)|
|/slides/layoutSlides/delete|POST|Delete unused LayoutSlides from a PowerPoint Presentation (without using storage)|[DeleteUnusedLayoutSlidesOnline](https://apireference.aspose.cloud/slides/#/LayoutSlides/DeleteUnusedLayoutSlidesOnline)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides" -H "Content-Type: application/json" -H "Authorization: Bearer MyAuthToken"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "slideList":[

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/masterSlides/1",

            "relation":"self",

            "title":"Slice"

         }

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/masterSlides",

      "relation":"self"

   }

}

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
LayoutSlides result = api.DeleteUnusedLayoutSlides("MyPresentation.pptx");
Console.WriteLine(result.SlideList.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
LayoutSlides result = api.deleteUnusedLayoutSlides("MyPresentation.pptx", null, null, null);
System.out.println(result.getSlideList().size());
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
$result = $api->DeleteUnusedLayoutSlides("MyPresentation.pptx");
print(count($result->getSlideList()));
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)
result = api.delete_unused_layout_slides("MyPresentation.pptx")
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

result = api.delete_unused_layout_slides("MyPresentation.pptx")
print(len(result.slide_list))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
api.deleteUnusedLayoutSlides("MyPresentation.pptx").then(response => {
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

result, _, e := api.SlidesApi.DeleteUnusedLayoutSlides("MyPresentation.pptx", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("%v", len(result.(asposeslidescloud.ILayoutSlides).GetSlideList()))
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
