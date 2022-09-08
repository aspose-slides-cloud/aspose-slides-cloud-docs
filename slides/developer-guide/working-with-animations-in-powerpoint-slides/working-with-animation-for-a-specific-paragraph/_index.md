---
title: "Working with Animation for a Specific Paragraph"
type: docs
url: /working-with-animation-for-a-specific-paragraph/
weight: 50
---

## **Introduction**
You can get or set animation effects related to a specific paragraph.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

**Add Animation effect to the 1st paragraph of the 2nd shape**

```java

curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/mainSequence" -d "@animation.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Get Animation effects for the 1st paragraph of the 2nd shape**

```java

curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation?shapeIndex=2&paragraphIndex=1" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**animation.json example**

```javascript
{
    "type": "Blink",
    "shapeIndex": 2
    "paragraphIndex": 1
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "mainSequence": [
        {
            "type": "Blink",
            "subtype": "None",
            "presetClassType": "Emphasis",
            "shapeIndex": 2,
            "paragraphIndex": 1,
            "triggerType": "OnClick",
            "triggerDelayTime": 0.0
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation",
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
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Effect dto = new Effect
{
    Type = Effect.TypeEnum.Blink,
    ShapeIndex = shapeIndex,
    ParagraphIndex = paragraphIndex
};
api.CreateAnimationEffect(fileName, slideIndex, dto);

SlideAnimation animation = api.GetAnimation(fileName, slideIndex, shapeIndex, paragraphIndex);
Console.WriteLine(animation.MainSequence.Count); //1
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
int paragraphIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Effect dto = new Effect();
dto.setType(Effect.TypeEnum.BLINK);
dto.setShapeIndex(shapeIndex);
dto.setParagraphIndex(paragraphIndex);
api.createAnimationEffect(fileName, slideIndex, dto, null, null, null);

SlideAnimation animation = api.getAnimation(fileName, slideIndex, shapeIndex, paragraphIndex, null, null, null);
System.out.println(animation.getMainSequence().size()); //1
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;
use Aspose\Slides\Cloud\Sdk\Model\Effect;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$paragraphIndex = 1;

$dto = new Effect();
$dto->setType("Blink");
$dto->setShapeIndex($shapeIndex);
$dto->setParagraphIndex($paragraphIndex);
$animation = $api->createAnimationEffect($fileName, $slideIndex, $dto);

$animation = $api->getAnimation($fileName, $slideIndex, $shapeIndex, $paragraphIndex);
print(count($animation->getMainSequence())); //1
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_animation import SlideAnimation
from asposeslidescloud.models.effect import Effect

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
paragraph_index = 1

dto = Effect()
dto.type = "Blink"
dto.shape_index = shape_index
dto.paragraph_index = paragraph_index
animation = api.create_animation_effect(file_name, slide_index, dto)

animation = api.get_animation(file_name, slide_index, shape_index, paragraph_index)
print(len(animation.main_sequence)) //1
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
const dto = new CloudSdk.SlideAnimation();
dto.type = CloudSdk.Effect.TypeEnum.Blink;
dto.shapeIndex = shapeIndex;
dto.paragraphIndex = paragraphIndex;
api.createAnimationEffect(fileName, slideIndex, dto).then(() => {
    api.getAnimation(fileName, slideIndex, shapeIndex, paragraphIndex).then((result) => {
        console.log(result.body.mainSequence.length); //1
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

dto := NewEffect()
dto.Type_ = "Blink"
dto.ShapeIndex = 2
dto.ParagraphIndex = 1
_, _, e := api.SlidesApi.CreateAnimationEffect("MyPresentation.pptx", 1, dto, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
}

animation, _, e := api.SlidesApi.GetAnimation("MyPresentation.pptx", 1, 2, 1, "", "MyStorageFolder", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v effects.", len(animation.getMainSequence()))
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
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
