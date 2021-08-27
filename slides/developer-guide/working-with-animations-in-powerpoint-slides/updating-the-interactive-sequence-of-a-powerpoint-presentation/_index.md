---
title: "Updating the interactive sequence of a PowerPoint Presentation"
type: docs
url: /updating-the-interactive-sequence-of-a-powerpoint-presentation/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud allows you to update information from a Power Point Presentation. 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{slide-index}/animation/interactiveSequences|GET|Get Animation Information from a PowerPoint Slide|[PostSlideAnimationInteractiveSequence](https://apireference.aspose.cloud/slides/#/Animation/PostSlideAnimationInteractiveSequence)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=xxxxx&client_secret=xxxx-xxx" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl -v -X POST "https://api.aspose.cloud/v3.0/slides/animation.pptx/slides/1/animation/interactiveSequences" -H "Content-Type:application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjEwNjM0NTAsImV4cCI6MTU2MTE0OTg1MCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.XURcZFFwPs__A4GHgzncfsCI5_F6R0NIWrTbdGcQqTKBV24jqbQYwe7POYMU8QT3_CKQ9zrlCX47Gtzx3XZ-1LyZAx3v6e6__r7HG9DsVCrzGXxzcIaYBwo9XohkfO5At9XcmXMqw1YoZvWskHUjhIAXzlg6Kt-k1hIPCL-0A1A0WkbdtWOJtWpTEVnIR2kBfXkUcNHLREq3S4JVshLmnjdPF6YViBM5AkV91diC33yj2Fwz-j572SjgwEuHkKNRLTngwsnu9DFEtfiN6bCCPBhulq6XG4DuqLrAtxyodD0Et5Y0YegUHUWOvf4-ZFbUd1ZHzU_rQ06dXzP6SDzMjg" --ssl-no-revoke -d {"effects": [{"type": "Fly", "subtype": "Bottom", "presetClassType": "Entrance", "shapeIndex": 5, "triggerType": "OnClick"} ], "triggerShapeIndex": 1 }

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
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
InteractiveSequence sequence = new InteractiveSequence
{
    TriggerShapeIndex = 1,
    Effects = new List<Effect>
    {
        new Effect
        {
            Type = Effect.TypeEnum.Fly,
            Subtype = Effect.SubtypeEnum.Bottom,
            PresetClassType = Effect.PresetClassTypeEnum.Entrance,
            ShapeIndex = 5,
            TriggerType = Effect.TriggerTypeEnum.OnClick
        }
    }
};
SlideAnimation response = api.CreateAnimationInteractiveSequence("myPresentation.pptx", 1, sequence);
foreach (InteractiveSequence sequence in response.InteractiveSequences)
{
    Console.WriteLine(sequence.TriggerShapeIndex); //should display 1
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
SlideAnimation response = api.CreateAnimationInteractiveSequence("myPresentation.pptx", 1, sequence);
foreach (InteractiveSequence sequence in response.InteractiveSequences)
{
    Console.WriteLine(sequence.TriggerShapeIndex); //should display 1
}

InteractiveSequence dto = new InteractiveSequence();
dto.setTriggerShapeIndex(1);

List<Effect> effects = new ArrayList<Effect>();
Effect effect = new Effect();
effect.setType(Effect.TypeEnum.FLY);
effect.setSubtype(Effect.SubtypeEnum.BOTTOM);
effect.setPresetClassType(Effect.PresetClassTypeEnum.ENTRANCE);
effect.setShapeIndex(5);
effect.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);
effects.add(effect);
dto.setEffects(effects);

SlideAnimation response = api.createAnimationInteractiveSequence("myPresentation.pptx", 1, dto, null, null, null);
for (InteractiveSequence sequence : response.getInteractiveSequences()) {
    System.out.println(sequence.getTriggerShapeIndex());
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\InteractiveSequence;
use Aspose\Slides\Cloud\Sdk\Model\Effect;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);
$dto = new InteractiveSequence();
$dto->setTriggerShapeIndex(1);

$effect = new Effect();
$effect->setType("Fly");
$effect->setSubtype("Bottom");
$effect->setPresetClassType("Entrance");
$effect->setShapeIndex(5);
$effect->setTriggerType("OnClick");
$dto->setEffects([ effect ]);

$response = $api->createAnimationInteractiveSequence("MyPresentation.pptx", 1, $dto);
foreach ($response->getInteractiveSequences() as $sequence)
{
    print(count($sequence->getTriggerShapeIndex()));
}
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.interactive_sequence import InteractiveSequence
from asposeslidescloud.models.effect import Effect

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)
dto = InteractiveSequence()
dto.trigger_shape_index = 1

effect = Effect()
effect.type = "Fly"
effect.subtype = "Bottom"
effect.preset_class_type = "Entrance"
effect.shape_index = 5
effect.trigger_type = "OnClick"
dto.effects = [ effect ]

result = api.create_animation_interactive_sequence("MyPresentation.pptx", 1, dto)
for sequence in result.intercative_sequences:
    print(sequence.trigger_shape_index)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new model.InteractiveSequence();
dto.triggerShapeIndex = 1;

const effect = new model.Effect();
effect.type = model.Effect.TypeEnum.Fly;
effect.subtype = model.Effect.SubtypeEnum.Bottom;
effect.presetClassType = model.Effect.PresetClassTypeEnum.Entrance;
effect.shapeIndex = 5;
effect.triggerType = model.Effect.TriggerTypeEnum.OnClick;
dto.effects = [ effect ];
return api.createAnimationInteractiveSequence("MyPresentation.pptx", 1, chart).then((result) => {
    (result.body as model.SlideAnimation).interactiveSequences.forEach((sequence) => { console.log(sequence.triggerShapeIndex); });
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
