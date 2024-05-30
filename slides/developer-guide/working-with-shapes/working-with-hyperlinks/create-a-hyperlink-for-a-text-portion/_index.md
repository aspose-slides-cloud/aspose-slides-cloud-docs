---
title: "Create a Hyperlink for a Text Portion"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- text
- hyperlink
- create a hyperlink
- add a hyperlink
type: docs
url: /create-a-hyperlink-for-a-text-portion/
weight: 20
---

## **Introduction**
**Portion** class has **HyperlinkClick** and **HyperlinkMouseOver** properties. You can set one of them to turn the portion into a hyperlink.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Add Portion**

```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/3/portions/1" -d "@portion.json" -H "Content-Type: text/json" -H "Authorization: Bearer AuthToken"
```

**portion.json example**

```json
{
    "hyperlinkMouseOver": {
        "actionType": "JumpLastSlide"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "text": "New portion",
    "fontBold": "True",
    "fontHeight":22.0,
    "hyperlinkMouseOver": {
        "actionType":"JumpLastSlide",
        "targetSlideIndex":5,
        "history":true,
        "colorSource":"Styles"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/3/portions/1",
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
int paragraphIndex = 1;
int portionIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Portion dto = new Portion
{
    HyperlinkMouseOver = new Hyperlink
    {
        ActionType = Hyperlink.ActionTypeEnum.JumpLastSlide
    }
};
Portion portion = api.UpdatePortion(fileName, slideIndex, shapeIndex, paragraphIndex, portionIndex, dto);
Console.WriteLine(portion.HyperlinkMouseOver.TargetSlideIndex); //5
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
int paragraphIndex = 1;
int portionIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Portion dto = new Portion();
Hyperlink hyperlink = new Hyperlink();
hyperlink.setActionType(Hyperlink.ActionTypeEnum.JUMPLASTSLIDE);
dto.setHyperlinkMouseOver(hyperlink);
Portion portion = api.updatePortion(fileName, slideIndex, shapeIndex, paragraphIndex, portionIndex, dto, null, null, null, null);
System.out.println(portion.getHyperlinkMouseOver().getTargetSlideIndex()); //5
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Portion;
use Aspose\Slides\Cloud\Sdk\Model\Hyperlink;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$paragraphIndex = 1;
$portionIndex = 1;

$dto = new Portion();
$hyperlink = new Hyperlink();
$hyperlink->setActionType("JumpLastSlide");
$dto->setHyperlinkMouseOver($hyperlink);
$portion = $api->updatePortion($fileName, $slideIndex, $shapeIndex, $paragraphIndex, $portionIndex, $dto);
print($portion->getHyperlinkMouseOver()->getTargetSlideIndex()); //5
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.portion import Portion
from asposeslidescloud.models.hyperlink import Hyperlink

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
paragraph_index = 1
portion_index = 1

dto = Portion()
hyperlink = Hyperlink()
hyperlink.action_type = "JumpLastSlide"
dto.hyperlink_mouse_over = hyperlink
portion = api.update_portion(file_name, slide_index, shape_index, paragraph_index, portion_index, dto)
print(f"{portion.hyperlink_mouse_over.target_slide_index}") #5
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
const shapeIndex = 2;
const paragraphIndex = 1;
const portionIndex = 1;

const dto = new CloudSdk.Portion();
const hyperlink = new CloudSdk.Hyperlink();
hyperlink.actionType = CloudSdk.Hyperlink.ActionTypeEnum.JumpLastSlide;
dto.hyperlinkMouseOver = hyperlink;
return api.updatePortion(fileName, slideIndex, shapeIndex, paragraphIndex, portionIndex, dto).then(result => {
    console.log(result.body.hyperlinkMouseOver.targetSlideIndex); //5
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
var paragraphIndex int32 = 1
var portionIndex int32 = 1

dto := asposeslidescloud.NewPortion()
hyperlink := asposeslidescloud.NewHyperlink()
hyperlink.ActionType = "JumpLastSlide"
dto.HyperlinkMouseOver = hyperlink
portion, _, e := api.SlidesApi.UpdatePortion(fileName, slideIndex, shapeIndex, paragraphIndex, portionIndex, dto, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Hyperlink Type: %v.", portion.GetHyperlinkMouseOver().GetActionType())
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
