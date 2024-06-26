---
title: "Add an Effect to an Interactive Sequence"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- animation
- add animation
- shape animation
- text animation
type: docs
url: /add-an-effect-to-an-interactive-sequence/
weight: 40
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, modify, and delete animations from PowerPoint presentations. You can add effects to interactive animation sequences on a presentation slide using the following method.

## **CreateAnimationInteractiveSequenceEffect**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation/interactiveSequences/{sequenceIndex}|POST|Adds a new effect to an interactive animation sequence on a presentation slide.|[CreateAnimationInteractiveSequenceEffect](https://reference.aspose.cloud/slides/#/Animation/CreateAnimationInteractiveSequenceEffect)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|sequenceIndex|integer|path|true|The 1-based index of an interactive animation sequence.|
|effect|`Effect`|body|true|The data transfer object with effect parameters.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the folder is located.|

### **Example**

The document **MyPresentation.pptx** contains two interactive animation sequences on the **first** slide, each with a single effect (Fly and Split, for example). Add a **Fade** effect for the **fourth** shape into the **first** interactive sequence.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the Effect**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/interactiveSequences/1" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @Effect.json
```

Effect.json content:

```json
{
  "ShapeIndex": 4,
  "Type": "Fade",
  "TriggerType": "AfterPrevious"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "mainSequence": [],
  "interactiveSequences": [
    {
      "effects": [
        {
          "type": "Fly",
          "subtype": "Bottom",
          "presetClassType": "Entrance",
          "shapeIndex": 2,
          "duration": 0.5,
          "triggerDelayTime": 0.0
        }
      ],
      "triggerShapeIndex": 1
    },
    {
      "effects": [
        {
          "type": "Split",
          "subtype": "HorizontalIn",
          "presetClassType": "Entrance",
          "shapeIndex": 3,
          "duration": 0.5,
          "triggerDelayTime": 0.0
        },
        {
          "type": "Fade",
          "subtype": "None",
          "presetClassType": "Entrance",
          "shapeIndex": 4,
          "duration": 0.5,
          "triggerDelayTime": 0.0
        }
      ],
      "triggerShapeIndex": 2
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation",
    "relation": "self",
    "slideIndex": 1
  }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int sequenceIndex = 1;

        Effect animationEffect = new Effect
        {
            ShapeIndex = 4,
            Type = Effect.TypeEnum.Fade,
            TriggerType = Effect.TriggerTypeEnum.AfterPrevious
        };

        SlideAnimation slideAnimation = slidesApi.CreateAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, animationEffect);

        int effectCount = slideAnimation.InteractiveSequences[sequenceIndex - 1].Effects.Count;
        Console.WriteLine("Number of effects in the 2nd interactive sequence: " + effectCount); // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Effect;
import com.aspose.slides.model.SlideAnimation;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int sequenceIndex = 1;

        Effect animationEffect = new Effect();
        animationEffect.setShapeIndex(4);
        animationEffect.setType(Effect.TypeEnum.FADE);
        animationEffect.setTriggerType(Effect.TriggerTypeEnum.AFTERPREVIOUS);

        SlideAnimation slideAnimation = slidesApi.createAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, animationEffect, null, null, null);

        int effectCount = slideAnimation.getInteractiveSequences().get(sequenceIndex - 1).getEffects().size();
        System.out.println("Number of effects in the 2nd interactive sequence: " + effectCount); // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Effect;
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$sequenceIndex = 1;

$animationEffect = new Effect();
$animationEffect->setShapeIndex(4);
$animationEffect->setType(Effect::TYPE_FADE);
$animationEffect->setTriggerType(Effect::TRIGGER_TYPE_AFTER_PREVIOUS);

$slideAnimation = $slidesApi->createAnimationInteractiveSequenceEffect($fileName, $slideIndex, $sequenceIndex, $animationEffect);

$effectCount = count($slideAnimation->getInteractiveSequences()[$sequenceIndex - 1]->getEffects());
echo "Number of effects in the 2nd interactive sequence: ", $effectCount; // 2
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
sequence_index = 1

animation_effect = Effect.new
animation_effect.shape_index = 4
animation_effect.type = "Fade"
animation_effect.trigger_type = "AfterPrevious"

slide_animation = slides_api.create_animation_interactive_sequence_effect(file_name, slide_index, sequence_index, animation_effect)

effect_count = slide_animation.interactive_sequences[sequence_index - 1].effects.length()
print "Number of effects in the 2nd interactive sequence: ", effect_count # 2
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.effect import Effect

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
sequence_index = 1

animation_effect = Effect()
animation_effect.shape_index = 4
animation_effect.type = "Fade"
animation_effect.trigger_type = "AfterPrevious"

slide_animation = slides_api.create_animation_interactive_sequence_effect(file_name, slide_index, sequence_index, animation_effect)

effect_count = len(slide_animation.interactive_sequences[sequence_index - 1].effects)
print("Number of effects in the 2nd interactive sequence:", effect_count)  # 2
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
sequenceIndex = 1;

animationEffect = new cloudSdk.Effect();
animationEffect.shapeIndex = 4;
animationEffect.type = cloudSdk.Effect.TypeEnum.Fade;
animationEffect.triggerType = cloudSdk.Effect.TriggerTypeEnum.AfterPrevious;

slidesApi.createAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, animationEffect).then(slideAnimation => {
    effectCount = slideAnimation.body.interactiveSequences[sequenceIndex - 1].effects.length;
    console.log("Number of effects in the 2nd interactive sequence:", effectCount); // 2
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;
    int sequenceIndex = 1;

    std::shared_ptr<Effect> animationEffect = std::make_shared<Effect>();
    animationEffect->setShapeIndex(4);
    animationEffect->setType(L"Fade");
    animationEffect->setTriggerType(L"AfterPrevious");

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->createAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, animationEffect).get();

    int effectCount = slideAnimation->getInteractiveSequences()[sequenceIndex - 1]->getEffects().size();
    std::wcout << L"Number of effects in the 2nd interactive sequence: " << effectCount; // 2
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Effect;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $sequence_index = 1;

my $animation_effect = AsposeSlidesCloud::Object::Effect->new();
$animation_effect->{shape_index} = 4;
$animation_effect->{type} = "Fade";
$animation_effect->{trigger_type} = "AfterPrevious";

my %parameters = (name => $file_name, slide_index => $slide_index, sequence_index => $sequence_index, effect => $animation_effect);
my $slide_animation = $slides_api->create_animation_interactive_sequence_effect(%parameters);

my $effect_count = @{$slide_animation->{interactive_sequences}[$sequence_index - 1]->{effects}};
print("Number of effects in the 2nd interactive sequence: ", $effect_count);  # 2
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
