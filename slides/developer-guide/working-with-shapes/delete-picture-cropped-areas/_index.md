---
title: "Delete Cropped Areas from a Picture Frame"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- picture
- image
- picture frame
- crop an image
- cropped area
type: docs
url: /delete-picture-cropped-areas/
weight: 210
---

## **Introduction**

You can use the [CompressImage](https://apireference.aspose.cloud/slides/#/Shapes/CompressImage) method to delete cropped areas from a picture frame.
This can help you reduce the size of the presentation. However, keep in mind that the method converts the picture to PNG format, which may increase the image size in some cases.

The method requires a presentation file name, slide index, and shape index. The shape must be a picture frame, or you will get an exception. You should set the **deletePictureCroppedAreas** parameter to **true**, and you can optionally specify the image resolution.

Below is an example of using the **CompressImage** method.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Delete picture cropped areas**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/4/compressImage?deletePictureCroppedAreas=true" -H "Authorization: Bearer <AuthToken>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

Empty response

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
string fileName = "MyPresentation.pptx";
int slideIndex = 2;
int shapeIndex = 4;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.CompressImage(fileName, slideIndex, shapeIndex, null, true);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 2;
int shapeIndex = 4;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.compressImage(fileName, slideIndex, shapeIndex, null, true, null, null, null);
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

$fileName = "MyPresentation.pptx";
$slideIndex = 2;
$shapeIndex = 4;

$api->CompressImage($fileName, $slideIndex, $shapeIndex, null, true);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

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

file_name = "MyPresentation.pptx"
slide_index = 2
shape_index = 4

api.compress_image(file_name, slide_index, shape_index, None, True)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 2;
const shapeIndex = 4;

await api.CompressImage(fileName, slideIndex, shapeIndex, null, true);
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
var slideIndex int32 = 2
var shapeIndex int32 = 4

var deletePictureCroppedAreas bool = true
_, e := api.SlidesApi.CompressImage(fileName, slideIndex, shapeIndex, nil, &deletePictureCroppedAreas, "", "", "")
if e != nil {
	fmt.Printf("Error: %v.", e)
}
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
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
