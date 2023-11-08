---
title: "Replace an Image"
type: docs
url: /replace-an-image/
weight: 50
---

## **Introduction**
Aspose.Slides Cloud API provides methods to replace an image in a PowerPoint Presentation. Both storage presentations and presentations uploded as a part of the request are supported. 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/images/{imageIndex}/replace|PUT|Replace image in a PowerPoint Presentation|[ReplaceImage](https://reference.aspose.cloud/slides/#/Images/ReplaceImage)|
|/slides/images/{imageIndex}/replace|POST|Replace image in a PowerPoint Presentation (without using storage)|[ReplaceImageOnline](https://reference.aspose.cloud/slides/#/Images/ReplaceImageOnline)|
### **cURL Example**
In the example below we assume that the target paresention is stored in a storage. The example shows how to replace an image with index 1.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/1/replace" -H "Content-Type: application/json" -H "Authorization: Bearer MyAuthToken" -F "image=@MyImage.png"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

200

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
Stream imageFile = File.OpenRead("MyImage.png");
api.ReplaceImage("MyPresentation.pptx", 1, imageFile);
Console.WriteLine("The image with the index 1 is replaced.");
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
byte[] imageFile = Files.readAllBytes(Paths.get("MyImage.png"));
api.replaceImage("MyPresentation.pptx", 1, imageFile, null, null, null);
System.out.println("The image with the index 1 is replaced.");
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

$imageFile = fopen("MyImage.png", 'r');
$api->replaceImage("MyPresentation.pptx", 1, $imageFile);
print("The image with the index 1 is replaced.");
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid =  "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)
image = File.binread("MyImage.png")
result = api.replace_image("MyPresentation.pptx", 1, image)
p("The image with the index 1 is replaced.")
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

with open("MyImage.png", 'rb') as f:
   image_source = f.read()
result = api.replace_image("MyPresentation.pptx", 1, image_source)
print("The image with the index 1 is replaced.")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
var image = fs.createReadStream("MyImage.png");
api.replaceImage("MyPresentation.pptx", 1, image).then((response) => {
    console.log("The image with the index 1 is replaced.");
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

image, e := ioutil.ReadFile("MyImage.png")
	if e != nil {
		t.Errorf("Error: %v.", e)
		return
	}

result, _, e := api.SlidesApi.replaceImage("MyPresentation.pptx", 1, image, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("%v", "The image with the index 1 is replaced.")
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}
//perl
{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
