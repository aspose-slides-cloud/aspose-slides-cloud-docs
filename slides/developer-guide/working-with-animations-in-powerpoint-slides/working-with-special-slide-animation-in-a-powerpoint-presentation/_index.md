---
title: "Working with Special Slide Animation in a PowerPoint Presentation"
type: docs
url: /working-with-special-slide-animation-in-a-powerpoint-presentation/
weight: 40
---

## **Introduction**
Aspose.Slides Cloud API allows you to read, add, modify and delete special (master, layout) slide animation in a PowerPoint Presentation. A set of methods identical to those that work with ordinary slides can be used to do that.
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/animation|GET|Read slide animation information|[GetSpecialSlideAnimation](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/GetSpecialSlideAnimation)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/interactiveSequences|POST|Add an interactive sequence to slide animation|[CreateSpecialSlideAnimationInteractiveSequence](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/CreateSpecialSlideAnimationInteractiveSequence)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/mainSequence|POST|Add an effect to slide animation main sequence|[CreateSpecialSlideAnimationEffect](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/CreateSpecialSlideAnimationEffect)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/interactiveSequences/{sequenceIndex}|POST|Add an effect to slide animation interactive sequence|[CreateSpecialSlideAnimationInteractiveSequenceEffect](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/CreateSpecialSlideAnimationInteractiveSequenceEffect)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation|PUT|Update slide animation|[SetSpecialSlideAnimation](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/SetSpecialSlideAnimation)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/mainSequence/{effectIndex}|PUT|Update an effect in slide animation main sequence|[UpdateSpecialSlideAnimationEffect](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/UpdateSpecialSlideAnimationEffect)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/mainSequence/interactiveSequences/{sequenceIndex}/{effectIndex}|PUT|Update an effect in slide animation interactive sequence|[UpdateSpecialSlideAnimationInteractiveSequenceEffect](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/UpdateSpecialSlideAnimationInteractiveSequenceEffect)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation|DELETE|Remove animation from a slide|[DeleteSpecialSlideAnimation](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/DeleteSpecialSlideAnimation)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/mainSequence|DELETE|Clear the main sequence in a slide animation|[DeleteSpecialSlideAnimationMainSequence](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/DeleteSpecialSlideAnimationMainSequence)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/interactiveSequences|DELETE|Clear the all interactive sequences in a slide animation|[DeleteSpecialSlideAnimationInteractiveSequences](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/DeleteSpecialSlideAnimationInteractiveSequences)|
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/interactiveSequences/{sequenceIndex}|DELETE|Delete an effect from an interactive sequence in a slide animation|[DeleteSpecialSlideAnimationInteractiveSequenceEffect](https://apireference.aspose.cloud/slides/#/SpecialSlideAnimation/DeleteSpecialSlideAnimationInteractiveSequenceEffect)|

The following examples demonstrate manipulating master slide animation. You can access layout slide shape paragraphs the same way, just change the value of **slideType** parameter accordingly.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

**Get Animation**

```java

curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/animation" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Update Animation**

```java

curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/animation" -d "@animation.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Clear Animation**

```java

curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/animation" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Simple animation.json example**

```javascript
{
  "mainSequence": [
      {
          "type": "Blink",
          "shapeIndex": 2
      },
      {
          "type": "Appear",
          "shapeIndex": 3
      },
  ]
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
            "triggerType": "OnClick",
            "triggerDelayTime": 0.0
        },
        {
            "type": "Appear",
            "subtype": "None",
            "presetClassType": "Entrance",
            "shapeIndex": 3,
            "triggerType": "OnClick",
            "triggerDelayTime": 0.0
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/animation",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
string fileName = "MyPresentation.pptx";
int slideIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

SlideAnimation animation = api.GetSpecialSlideAnimation(fileName, slideIndex, SpecialSlideType.MasterSlide);
Console.WriteLine(animation.MainSequnece.Count);

SlideAnimation dto = new SlideAnimation
{
    MainSequence = new List<Effect>
    {
        new Effect
        {
            Type = Effect.TypeEnum.Blink,
            ShapeIndex = 2
        },
        new Effect
        {
            Type = Effect.TypeEnum.Appear,
            ShapeIndex = 3
        }
    }
};
animation = api.SetSpecialSlideAnimation(fileName, slideIndex, SpecialSlideType.MasterSlide, dto);
Console.WriteLine(animation.MainSequnece.Count); //2

animation = api.DeleteSpecialSlideAnimation(fileName, slideIndex, SpecialSlideType.MasterSlide);
Console.WriteLine(animation.MainSequnece.Count); //0
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

SlideAnimation animation = api.getSpecialSlideAnimation(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, null, null, null, null);
System.out.println(animation.getMainSequnece().size());

SlideAnimation dto = new SlideAnimation();
List<Effect> effects = new ArrayList<Effect>();
Effect effect1 = new Effect();
effect1.setType(Effect.TypeEnum.BLINK);
effect1.setShapeIndex(2);
effects.add(effect1);
Effect effect2 = new Effect();
effect2.setType(Effect.TypeEnum.APPEAR);
effect2.setShapeIndex(3);
effects.add(effect2);
dto.setMainSequence(effects);
animation = api.setSpecialSlideAnimation(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, dto, null, null, null);
System.out.println(animation.getMainSequnece().size()); //2

animation = api.deleteSpecialSlideAnimation(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, null, null, null);
System.out.println(animation.getMainSequnece().size()); //0
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;
use Aspose\Slides\Cloud\Sdk\Model\Effect;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$animation = $api->GetSpecialSlideAnimation($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE);
print($animation->getMainSequence());

$dto = new SlideAnimation();
$effect1 = new Effect();
$effect1->setType("Blink");
$effect1->setShapeIndex(2);
$effect2 = new Effect();
$effect2->setType("Appear");
$effect2->setShapeIndex(3);
$dto->setMainSequence([ $effect1, $effect2 ]);

$animation = api->SetSpecialSlideAnimation($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $dto);
print($animation->getMainSequence()); //2

$animation = api->DeleteSpecialSlideAnimation($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE);
print($animation->getMainSequence()); //0
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
animation = api.get_special_slide_animation(file_name, slide_index, 'masterSlide')
print(len(animation.main_sequence))

dto = SlideAnimation()
effect1 = Effect()
effect1.type = "Blink"
effect1.shape_index = 2
effect2 = Effect()
effect2.type = "Appear"
effect2.shape_index = 3
dto.main_sequence = [ effect1, effect2 ]

animation = api.set_special_slide_animation(file_name, slide_index, 'masterSlide', dto)
print(len(animation.main_sequence)) #2

animation = api.delete_special_slide_animation(file_name, slide_index, 'masterSlide')
print(len(animation.main_sequence)) #0
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
api.getSpecialSlideAnimation(fileName, slideIndex, CloudSdk.model.SpecialSlideType.MasterSlide).then((result) => {
    console.log((result.body as CloudSdk.model.SlideAnimation).mainSequence.length);
    const dto = new CloudSdk.model.SlideAnimation();
    const effect1 = CloudSdk.model.Effect();
    effect1.type = CloudSdk.model.Effect.TypeEnum.Blink;
    effect1.shapeIndex = 2;
    const effect2 = CloudSdk.model.Effect();
    effect2.type = CloudSdk.model.Effect.TypeEnum.Appear;
    effect2.shapeIndex = 3;
    dto.mainSequence = [ effect1, effect2 ];
    api.setSpecialSlideAnimation(fileName, slideIndex, CloudSdk.model.SpecialSlideType.MasterSlide, dto).then((putResult) => {
        console.log((putResult.body as CloudSdk.model.SlideAnimation).mainSequence.length); //2
        api.deleteSpecialSlideAnimation(fileName, slideIndex, CloudSdk.model.SpecialSlideType.MasterSlide).then((deleteResult) => {
            console.log((deleteResult.body as CloudSdk.model.SlideAnimation).mainSequence.length); //0
        });
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}
                                                                                                                                
{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< /tabs >}}

### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)