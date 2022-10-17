---
title: "Updating the MainSequence of an animation in a PowerPoint Slide"
type: docs
url: /updating-the-mainsequence-of-an-animation-in-a-powerpoint-slide/
weight: 30
---

## **Introduction**
Aspose.Slides Cloud allows you to add / udpdate the MainSequence of an animation in a PowerPoint Slide
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation/mainSequence|POST|Add / Update the main sequence of a Animation|[PostSlideAnimationEffect](https://apireference.aspose.cloud/slides/#/Animation/PostSlideAnimationEffect)|
|/slides/{name}/slides/{slideIndex}/animation/interactiveSequences/{sequenceIndex}|POST|Add / Update the main sequence of a Animation|[PostSlideAnimationInteractiveSequenceEffect](https://apireference.aspose.cloud/slides/#/Animation/PostSlideAnimationInteractiveSequenceEffect)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "granttype=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl -v -X POST "https://api.aspose.cloud/v3.0/slides/animation.pptx/slides/1/animation/mainSequence" -H "Content-Type:application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjEwNjM0NTAsImV4cCI6MTU2MTE0OTg1MCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.XURcZFFwPs__A4GHgzncfsCI5_F6R0NIWrTbdGcQqTKBV24jqbQYwe7POYMU8QT3_CKQ9zrlCX47Gtzx3XZ-1LyZAx3v6e6__r7HG9DsVCrzGXxzcIaYBwo9XohkfO5At9XcmXMqw1YoZvWskHUjhIAXzlg6Kt-k1hIPCL-0A1A0WkbdtWOJtWpTEVnIR2kBfXkUcNHLREq3S4JVshLmnjdPF6YViBM5AkV91diC33yj2Fwz-j572SjgwEuHkKNRLTngwsnu9DFEtfiN6bCCPBhulq6XG4DuqLrAtxyodD0Et5Y0YegUHUWOvf4-ZFbUd1ZHzU_rQ06dXzP6SDzMjg" --ssl-no-revoke -d {"type": "Appear", "presetClassType":"Entrance", "shapeIndex":1, "triggerType":"OnClick"}

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "mainSequence":[

      {

         "type":"Appear",

         "subtype":"None",

         "presetClassType":"Entrance",

         "shapeIndex":1,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      },

      {

         "type":"Bounce",

         "subtype":"None",

         "presetClassType":"Entrance",

         "shapeIndex":2,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      },

      {

         "type":"Fly",

         "subtype":"Bottom",

         "presetClassType":"Entrance",

         "shapeIndex":3,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      }

   ],

   "interactiveSequences":[

      {

         "effects":[

            {

               "type":"Fly",

               "subtype":"Bottom",

               "presetClassType":"Entrance",

               "shapeIndex":5,

               "triggerType":"OnClick",

               "triggerDelayTime":0.0

            }

         ],

         "triggerShapeIndex":1

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/animation.pptx/slides/1/animation",

      "relation":"self"

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
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Effect newEffect = new Effect
{
    Type = Effect.TypeEnum.Fly,
    Subtype = Effect.SubtypeEnum.Bottom,
    PresetClassType = Effect.PresetClassTypeEnum.Entrance,
    ShapeIndex = 4,
    TriggerType = Effect.TriggerTypeEnum.OnClick
};
SlideAnimation response = api.CreateAnimationInteractiveSequenceEffect("myPresentation.pptx", 1, 1, newEffect);
foreach (Effect effect in response.InteractiveSequences[0].Effects)
{
    Console.WriteLine($"{effect.ShapeIndex} - {effect.Type}"); //5 - Fly
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Effect newEffect = new Effect();
newEffect.setType(Effect.TypeEnum.FLY);
newEffect.setSubtype(Effect.SubtypeEnum.BOTTOM);
newEffect.setPresetClassType(Effect.PresetClassTypeEnum.ENTRANCE);
newEffect.setShapeIndex(4);
newEffect.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);

SlideAnimation response = api.createAnimationInteractiveSequenceEffect("myPresentation.pptx", 1, 1, newEffect, null, null, null);
for (Effect effect : response.getInteractiveSequences().get(0).getEffects()) {
    System.out.println(effect.getShapeIndex());
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Effect;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);
$dto = new Effect();
$dto->setType("Fly");
$dto->setSubtype("Bottom");
$dto->setPresetClassType("Entrance");
$dto->setShapeIndex(4);
$dto->setTriggerType("OnClick");

$response = $api->CreateAnimationInteractiveSequenceEffect("MyPresentation.pptx", 1, 1, $dto);
foreach ($response->getInteractiveSequences()[0]->getEffects() as $effect)
{
    print($effect->getShapeIndex());
}
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.effect import Effect

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)
dto = Effect()
dto.type = "Fly"
dto.subtype = "Bottom"
dto.preset_class_type = "Entrance"
dto.shape_index = 4
dto.trigger_type = "OnClick"

result = api.create_animation_interactive_sequence_effect("MyPresentation.pptx", 1, 1, dto)
for effect in result.interactive_sequences[0].effects:
    print(effect.shape_index)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new CloudSdk.Effect();
dto.type = CloudSdk.Effect.TypeEnum.Fly;
dto.subtype = CloudSdk.Effect.SubtypeEnum.Bottom;
dto.presetClassType = CloudSdk.Effect.PresetClassTypeEnum.Entrance;
dto.shapeIndex = 4;
dto.triggerType = CloudSdk.Effect.TriggerTypeEnum.OnClick;
api.createAnimationInteractiveSequenceEffect("MyPresentation.pptx", 1, 1, dto).then((result) => {
    result.body.interactiveSequences[0].effects.forEach((sequence) => { console.log(sequence.shapeIndex); });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

effect := NewEffect()
effect.Type_ = "Fly"
effect.Subtype = "Bottom"
effect.PresetClassType = "Entrance"
effect.ShapeIndex = 4
effect.TriggerType = "OnClick"

animation, _, e := api.SlidesApi.CreateAnimationInteractiveSequenceEffect("MyPresentation.pptx", 1, 1, effect, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    for i, sequence := range animation.getInteractiveSequences() {
        fmt.Printf("Sequence %v, trigger shape index: %v.", i + 1, sequence.getTriggerShapeIndex())
    }
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
