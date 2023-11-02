---
title: "Working with Zoom Frames"
type: docs
url: /working-with-zoom-frames/
weight: 150
---

## **Introduction**
The example below shows how to create add a zoom frame to a slide.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Add Portion**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes" -d "@zoomFrame.json" -H "Content-Type: text/json" -H "Authorization: Bearer AuthToken"
```

**zoomFrame.json example**

```javascript
{
    "type": "ZoomFrame",
    "x": 20,
    "y": 20,
    "width": 200,
    "height": 100,
    "targetSlideIndex": 2
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "type": "ZoomFrame",
    "targetSlideIndex": 2,
    "imageType": 1,
    "name": "",
    "width": 200.0,
    "height": 100.0,
    "alternativeText": "",
    "alternativeTextTitle": "",
    "hidden": false,
    "x": 20.0,
    "y": 20.0,
    "zOrderPosition": 3,
    "fillFormat": { "type": "NoFill" },
    "threeDFormat": { "contourWidth": 0.0, "depth": 0.0, "extrusionHeight": 0.0 },
    "lineFormat": {
        "alignment": "Center",
        "capStyle": "Flat",
        "dashStyle": "Solid",
        "joinStyle": "Round",
        "style": "Single",
        "beginArrowHead": { "length": "Medium", "style": "None", "width": "Medium" },
        "endArrowHead": { "length": "Medium", "style": "None", "width": "Medium" },
        "fillFormat": { "type": "NoFill" },
        "miterLimit": 10.0,
        "width": 0.75
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/3",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with�working examples, to get you�started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
string fileName = "MyPresentation.pptx";
int slideIndex = 3;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ZoomFrame dto = new ZoomFrame
{
    X = 20,
    Y = 20,
    Width = 200,
    Height = 100,
    TargetSlideIndex = 2
};
ShapeBase shape = api.CreateShape(fileName, slideIndex, dto);
Console.WriteLine(((ZoomFrame)shape).TargetSlideIndex);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 3;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ZoomFrame dto = new ZoomFrame();
dto.setX(20.0);
dto.setY(20.0);
dto.setWidth(200.0);
dto.setHeight(100.0);
dto.setTargetSlideIndex(2);
ShapeBase shape = api.createShape(fileName, slideIndex, dto, null, null, null, null, null, null);
System.out.println(((ZoomFrame)shape).getTargetSlideIndex());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ZoomFrame;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 3;

$dto = new ZoomFrame();
$dto->setX(20);
$dto->setY(20);
$dto->setWidth(200);
$dto->setHeight(100);
$dto->setTargetSlideIndex(2);
$shape = $api->createShape($fileName, $slideIndex, $dto);
print($shape->getTargetSlideIndex());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.zoom_frame import ZoomFrame

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 3

dto = ZoomFrame()
dto.x = 20
dto.y = 20
dto.width = 200
dto.height = 100
dto.target_slide_index = 2
shape = api.create_shape(file_name, slide_index, dto)
print(shape.target_slide_index)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 3;

const dto = new CloudSdk.ZoomFrame();
dto.x = 20;
dto.y = 20;
dto.width = 200;
dto.height = 100;
dto.targetSlideIndex = 2;
return api.createShape(fileName, slideIndex, dto).then((result) => {
    console.log(result.body.targetSlideIndex);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
var slideIndex int32 = 3

dto := asposeslidescloud.NewZoomFrame()
dto.X = 0
dto.Y = 0
dto.Width = 200
dto.Height = 100
dto.TargetSlideIndex = 2
shape, _, e := api.SlidesApi.CreateShape(fileName, slideIndex, dto, nil, nil, "", "", "", "")
if e != nil {
	fmt.Printf("Error: %v.", e)
}
if shape == nil {
	fmt.Printf("Error: shape should not be nil.")
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
The Aspose Cloud SDK's can be downloaded from the following page:�[Available SDK's](/slides/available-sdks/)
