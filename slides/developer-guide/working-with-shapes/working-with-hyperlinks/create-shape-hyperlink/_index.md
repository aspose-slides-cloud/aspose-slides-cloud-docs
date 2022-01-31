---
title: "Create a Hyperlink for a Shape"
type: docs
url: /create-shape-hyperlink/
weight: 10
---

## **Introduction**
Every type of shape has **HyperlinkClick** and **HyperlinkMouseOver** properties. You can set one of them to create a hyperlink. The entire shape becomes a link in that case.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Add Portion**

```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2" -d "@shape.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"
```

**shape.json example**

```javascript
{
    "type": "Shape",
    "hyperlinkClick": {
        "actionType": "Hyperlink",
        "externalUrl": "https://docs.aspose.cloud/slides"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "type": "Shape",
    "shapeType": "Rectangle",
    "name": "ShapeObject",
    "width": 500.0,
    "height": 200.0,
    "x": 100.0,
    "y":100.0,
    "lineFormat": {
        "alignment": "Center",
        "capStyle": "Flat",
        "dashStyle": "Solid",
        "joinStyle": "Round",
        "style": "Single",
        "miterLimit": 10.0,
        "width": 0.75
    },
    "hyperlinkClick": {
        "actionType": "Hyperlink",
        "externalUrl": "https://docs.aspose.cloud/slides"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/6",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
string fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Shape shape = new Shape
{
    HyperlinkClick = new Hyperlink
    {
        ActionType = Hyperlink.ActionTypeEnum.Hyperlink,
        ExternalUrl = "https://docs.aspose.cloud/slides"
    }
};
ShapeBase updatedShape = api.UpdateShape(fileName, slideIndex, shapeIndex, shape);
Console.WriteLine(updatedShape.HyperlinkClick.ExternalUrl); //https://docs.aspose.cloud/slides
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Shape shape = new Shape();
Hyperlink hyperlink = new Hyperlink();
hyperlink.setActionType(Hyperlink.ActionTypeEnum.HYPERLINK);
hyperlink.setExternalUrl("https://docs.aspose.cloud/slides");
shape.setHyperlinkClick(hyperlink);
Shape updatedShape = (Shape)api.updateShape(fileName, slideIndex, shapeIndex, shape, null, null, null);
System.out.println(updatedShape.getHyperlinkClick().getExternalUrl().size()); //https://docs.aspose.cloud/slides
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Shape;
use Aspose\Slides\Cloud\Sdk\Model\Hyperlink;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;

$shape = new Shape();
$hyperlink = new Hyperlink();
$hyperlink->setActionType("Hyperlink");
$hyperlink->setExternalUrl("https://docs.aspose.cloud/slides");
$shape->setHyperlinkClick($hyperlink);
$updatedShape = $api->updateShape(self::fileName, $slideIndex, $shapeIndex, $shape);
print(count($updatedShape->getHyperlinkClick()->getExternalUrl())); //https://docs.aspose.cloud/slides
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.shape import Shape
from asposeslidescloud.models.hyperlink import Hyperlink

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2

shape = Shape()
hyperlink = Hyperlink()
hyperlink.action_type = "Hyperlink"
hyperlink.external_url = "https://docs.aspose.cloud/slides"
shape.hyperlink_click = hyperlink
updated_shape = api.update_shape(file_name, slide_index, shape_index, shape)
print(len(updated_shape.hyperlink_click.external_url)) #https://docs.aspose.cloud/slides
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
const shapeIndex = 2;

const shape = new CloudSdk.Shape();
const hyperlink = new CloudSdk.Hyperlink();
hyperlink.actionType = CloudSdk.Hyperlink.ActionTypeEnum.Hyperlink;
hyperlink.externalUrl = "https://docs.aspose.cloud/slides";
shape.hyperlinkClick = hyperlink;
return api.updateShape(fileName, slideIndex, shapeIndex, shape).then((result) => {
    console.log(result.body.hyperlinkClick.externalUrl); //https://docs.aspose.cloud/slides
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
var slideIndex int32 = 1
var shapeIndex int32 = 2

shape := NewShape()
hyperlink := NewHyperlink()
hyperlink.ActionType = "Hyperlink"
hyperlink.ExternalUrl = "https://docs.aspose.cloud/slides"
shape.HyperlinkClick = hyperlink
updatedShape, _, e := c.SlidesApi.UpdateShape(fileName, 1, 1, shape, "password", folderName, "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}
fmt.Printf("Hyperlink URL: %v.", updatedShape.getHyperlinkClick().getExternalUrl())
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
