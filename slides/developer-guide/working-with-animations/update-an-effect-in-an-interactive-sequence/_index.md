---
title: "Update an Effect in an Interactive Sequence"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- animation
- update animation
- shape animation
- text animation
type: docs
url: /update-an-effect-in-an-interactive-sequence/
weight: 45
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, and modify animations in PowerPoint presentations. You can use the following method to update an effect in an interactive animation sequence on a presentation slide.

## **UpdateAnimationInteractiveSequenceEffect**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation/interactiveSequences/{sequenceIndex}/{effectIndex}|PUT|Updates an effect in an interactive animation sequence on a slide.|[UpdateAnimationInteractiveSequenceEffect](https://reference.aspose.cloud/slides/#/Animation/UpdateAnimationInteractiveSequenceEffect)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|sequenceIndex|integer|path|true|The 1-based index of an interactive sequence.|
|effectIndex|integer|path|true|The 1-based index of an effect to be modified.|
|effect|`Effect`|body|true|The data transfer object with effect parameters.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Example**

The document **MyPresentation.pptx** contains **one** interactive animation sequence with two effects on the **first** slide. Change the **second** effect to **Split** and trigger it **on click** by the same shape.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Update the Effect**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/interactiveSequences/1/2" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @Effect.json
```

Effect.json content:

```json
{
  "Type": "Split",
  "TriggerType": "OnClick"
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
          "type": "Fade",
          "subtype": "None",
          "presetClassType": "Entrance",
          "shapeIndex": 3,
          "triggerType": "WithPrevious",
          "duration": 0.5,
          "triggerDelayTime": 0.0
        },
        {
          "type": "Split",
          "subtype": "HorizontalIn",
          "presetClassType": "Entrance",
          "shapeIndex": 4,
          "triggerType": "OnClick",
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
        int effectIndex = 1;

        Effect effect = new Effect
        {
            Type = Effect.TypeEnum.Split,
            TriggerType = Effect.TriggerTypeEnum.OnClick
        };

        SlideAnimation slideAnimation = slidesApi.UpdateAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, effectIndex, effect);

        Effect updatedEffect = slideAnimation.InteractiveSequences[sequenceIndex - 1].Effects[effectIndex - 1];
        Console.WriteLine("Effect type: " + updatedEffect.Type); // Split
        Console.WriteLine("Trigger type: " + updatedEffect.TriggerType); // OnClick
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
        int effectIndex = 1;

        Effect effect = new Effect();
        effect.setType(Effect.TypeEnum.SPLIT);
        effect.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);

        SlideAnimation slideAnimation = slidesApi.updateAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, effectIndex, effect, null, null, null);

        Effect updatedEffect = slideAnimation.getInteractiveSequences().get(sequenceIndex - 1).getEffects().get(effectIndex - 1);
        System.out.println("Effect type: " + updatedEffect.getType()); // Split
        System.out.println("Trigger type: " + updatedEffect.getTriggerType()); // OnClick
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
$effectIndex = 1;

$effect = new Effect();
$effect->setType(Effect::TYPE_SPLIT);
$effect->setTriggerType(Effect::TRIGGER_TYPE_ON_CLICK);

$slideAnimation = $slidesApi->updateAnimationInteractiveSequenceEffect($fileName, $slideIndex, $sequenceIndex, $effectIndex, $effect);

$updatedEffect = $slideAnimation->getInteractiveSequences()[$sequenceIndex - 1]->getEffects()[$effectIndex - 1];
echo "Effect type: ", $updatedEffect->getType(), "\n"; // Split
echo "Trigger type: ", $updatedEffect->getTriggerType(); // OnClick
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
effect_index = 1

effect = Effect.new
effect.type = "Split"
effect.trigger_type = "OnClick"

slide_animation = slides_api.update_animation_interactive_sequence_effect(file_name, slide_index, sequence_index, effect_index, effect)

updated_effect = slide_animation.interactive_sequences[sequence_index - 1].effects[effect_index - 1]
puts "Effect type: #{updated_effect.type}" # Split
puts "Trigger type: #{updated_effect.trigger_type}" # OnClick
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
effect_index = 1

effect = Effect()
effect.type = "Split"
effect.trigger_type = "OnClick"

slide_animation = slides_api.update_animation_interactive_sequence_effect(file_name, slide_index, sequence_index, effect_index, effect)

updated_effect = slide_animation.interactive_sequences[sequence_index - 1].effects[effect_index - 1]
print("Effect type:", updated_effect.type)  # Split
print("Trigger type:", updated_effect.trigger_type)  # OnClick
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
sequenceIndex = 1;
effectIndex = 1;

effect = new cloudSdk.Effect();
effect.type = cloudSdk.Effect.TypeEnum.Split;
effect.triggerType = cloudSdk.Effect.TriggerTypeEnum.OnClick;

slidesApi.updateAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, effectIndex, effect).then(slideAnimation => {
    updatedEffect = slideAnimation.body.interactiveSequences[sequenceIndex - 1].effects[effectIndex - 1];
    console.log("Effect type:", updatedEffect.type); // Split
    console.log("Trigger type:", updatedEffect.triggerType); // OnClick
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
    int effectIndex = 1;

    std::shared_ptr<Effect> effect = std::make_shared<Effect>();
    effect->setType(L"Split");
    effect->setTriggerType(L"OnClick");

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->updateAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, effectIndex, effect).get();

    std::shared_ptr<Effect> updatedEffect = slideAnimation->getInteractiveSequences()[sequenceIndex - 1]->getEffects()[effectIndex - 1];
    std::wcout << L"Effect type: " << updatedEffect->getType() << "\n"; // Split
    std::wcout << L"Trigger type: " << updatedEffect->getTriggerType(); // OnClick
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
my $effect_index = 1;

my $effect = AsposeSlidesCloud::Object::Effect->new();
$effect->{type} = "Split";
$effect->{trigger_type} = "OnClick";

my %parameters = (name => $file_name, slide_index => $slide_index, sequence_index => $sequence_index, effect_index => $effect_index, effect => $effect);
my $slide_animation = $slides_api->update_animation_interactive_sequence_effect(%parameters);

my $updated_effect = $slide_animation->{interactive_sequences}[$sequence_index - 1]->{effects}[$effect_index - 1];
print("Effect type: ", $updated_effect->{type}, "\n"); # Split
print("Trigger type: ", $updated_effect->{trigger_type}); # OnClick
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
