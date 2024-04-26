---
title: "Create an Interactive Sequence"
keywords: "PowerPoint, presentation, REST API, Cloud API, animation, add animation, shape animation, text animation"
type: docs
url: /create-an-interactive-sequence-on-a-special-slide/
weight: 50
---

## **Introduction**

The interactive animation sequence represents animations that are triggered by click on a specified shape. The following method allows you to create interactive sequences on special slides (Master, Layout, or Notes) in PowerPoint presentations.

## **CreateSpecialSlideAnimationInteractiveSequence**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/interactiveSequences|POST|Adds an interactive animation sequence to a special slide in a presentation saved in a storage.|[CreateSpecialSlideAnimationInteractiveSequence](https://reference.aspose.cloud/slides/#/SpecialSlideAnimation/CreateSpecialSlideAnimationInteractiveSequence)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|sequence|`InteractiveSequence`|body|true|The collection of shape effects.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

The document **MyPresentation.pptx** saved in the **default** storage contains four shapes on the **Layout** of the **first** slide without animations. Add the **fly** effect from **below** for the **fourth** shape by clicking on the **second** shape.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the Shape Effect**

```sh
curl POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/LayoutSlide/animation/interactiveSequences" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @InteractiveSequence.json
```

InteractiveSequence.json content:

```json
{
  "Effects": [
    {
      "Type": "Fly",
      "Subtype": "Bottom",
      "PresetClassType": "Entrance",
      "ShapeIndex": 4,
      "TriggerType": "OnClick"
    }
  ],
  "TriggerShapeIndex": 2
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
          "animateTextType": "AllAtOnce",
          "shapeIndex": 4,
          "triggerType": "OnClick",
          "duration": 0.5,
          "triggerDelayTime": 0
        }
      ],
      "triggerShapeIndex": 2
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1/animation",
    "relation": "self"
  }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using System.Collections.Generic;

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LayoutSlide;

        InteractiveSequence interactiveSequence = new InteractiveSequence
        {
            TriggerShapeIndex = 2,
            Effects = new List<Effect>
            {
                new Effect
                {
                    ShapeIndex = 4,
                    Type = Effect.TypeEnum.Fly,
                    Subtype = Effect.SubtypeEnum.Bottom,
                    PresetClassType = Effect.PresetClassTypeEnum.Entrance,
                    TriggerType = Effect.TriggerTypeEnum.OnClick
                }
            }
        };

        SlideAnimation slideAnimation = slidesApi.CreateSpecialSlideAnimationInteractiveSequence(fileName, slideIndex, slideType, interactiveSequence);

        int sequenceCount = slideAnimation.InteractiveSequences.Count;
        Console.WriteLine("Interactive sequence count: " + sequenceCount); // 1
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Effect;
import com.aspose.slides.model.InteractiveSequence;
import com.aspose.slides.model.SlideAnimation;
import com.aspose.slides.model.SpecialSlideType;

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;

        Effect effect = new Effect();
        effect.setShapeIndex(4);
        effect.setType(Effect.TypeEnum.FLY);
        effect.setSubtype(Effect.SubtypeEnum.BOTTOM);
        effect.setPresetClassType(Effect.PresetClassTypeEnum.ENTRANCE);
        effect.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);

        InteractiveSequence interactiveSequence = new InteractiveSequence();
        interactiveSequence.setTriggerShapeIndex(2);
        interactiveSequence.setEffects(Arrays.asList(effect));

        SlideAnimation slideAnimation = slidesApi.createSpecialSlideAnimationInteractiveSequence(fileName, slideIndex, slideType, interactiveSequence, null, null, null);

        int sequenceCount = slideAnimation.getInteractiveSequences().size();
        System.out.println("Interactive sequence count: " + sequenceCount); // 1
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;
use Aspose\Slides\Cloud\Sdk\Model\Effect;
use Aspose\Slides\Cloud\Sdk\Model\InteractiveSequence;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;

$effect = new Effect();
$effect->setShapeIndex(4);
$effect->setType(Effect::TYPE_FLY);
$effect->setSubtype(Effect::SUBTYPE_BOTTOM);
$effect->setPresetClassType(Effect::PRESET_CLASS_TYPE_ENTRANCE);
$effect->setTriggerType(Effect::TRIGGER_TYPE_ON_CLICK);

$interactiveSequence = new InteractiveSequence();
$interactiveSequence->setTriggerShapeIndex(2);
$interactiveSequence->setEffects([ $effect ]);

$slideAnimation = $slidesApi->createSpecialSlideAnimationInteractiveSequence($fileName, $slideIndex, $slideType, $interactiveSequence);

$sequenceCount = count($slideAnimation->getInteractiveSequences());
echo "Interactive sequence count: ", $sequenceCount; // 1
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
slide_type = SpecialSlideType::LAYOUT_SLIDE

effect = Effect.new
effect.shape_index = 4
effect.type = "Fly"
effect.subtype = "Bottom"
effect.preset_class_type = "Entrance"
effect.trigger_type = "OnClick"

interactive_sequence = InteractiveSequence.new
interactive_sequence.trigger_shape_index = 2
interactive_sequence.effects = [effect]

slide_animation = slides_api.create_special_slide_animation_interactive_sequence(file_name, slide_index, slide_type, interactive_sequence)

sequence_count = slide_animation.interactive_sequences.length()
print "Interactive sequence count: ", sequence_count # 1
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import SpecialSlideType
from asposeslidescloud.models import Effect
from asposeslidescloud.models import InteractiveSequence

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = SpecialSlideType.LAYOUTSLIDE

effect = Effect()
effect.shape_index = 4
effect.type = "Fly"
effect.subtype = "Bottom"
effect.preset_class_type = "Entrance"
effect.trigger_type = "OnClick"

interactive_sequence = InteractiveSequence()
interactive_sequence.trigger_shape_index = 2
interactive_sequence.effects = [effect]

slide_animation = slides_api.create_special_slide_animation_interactive_sequence(file_name, slide_index, slide_type, interactive_sequence)

sequence_count = len(slide_animation.interactive_sequences)
print("Interactive sequence count:", sequence_count)  # 1
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
slideType = cloudSdk.SpecialSlideType.LayoutSlide;

effect = new cloudSdk.Effect();
effect.shapeIndex = 4;
effect.type = cloudSdk.Effect.TypeEnum.Fly;
effect.subtype = cloudSdk.Effect.SubtypeEnum.Bottom;
effect.presetClassType = cloudSdk.Effect.PresetClassTypeEnum.Entrance;
effect.triggerType = cloudSdk.Effect.TriggerTypeEnum.OnClick;

interactiveSequence = new cloudSdk.InteractiveSequence();
interactiveSequence.triggerShapeIndex = 2;
interactiveSequence.effects = [effect];

slidesApi.createSpecialSlideAnimationInteractiveSequence(fileName, slideIndex, slideType, interactiveSequence).then(slideAnimation => {
    sequenceCount = slideAnimation.body.interactiveSequences.length;
    console.log("Interactive sequence count:", sequenceCount); // 1
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
    const wchar_t* slideType = L"LayoutSlide";

    std::shared_ptr<Effect> effect = std::make_shared<Effect>();
    effect->setShapeIndex(4);
    effect->setType(L"Fly");
    effect->setSubtype(L"Bottom");
    effect->setPresetClassType(L"Entrance");
    effect->setTriggerType(L"OnClick");

    std::shared_ptr<InteractiveSequence> interactiveSequence = std::make_shared<InteractiveSequence>();
    interactiveSequence->setTriggerShapeIndex(2);
    interactiveSequence->setEffects({ effect });

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->createSpecialSlideAnimationInteractiveSequence(fileName, slideIndex, slideType, interactiveSequence).get();

    int sequenceCount = slideAnimation->getInteractiveSequences().size();
    std::wcout << L"Interactive sequence count: " << sequenceCount; // 1
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Effect;
use AsposeSlidesCloud::Object::InteractiveSequence;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $slide_type = "LayoutSlide";

my $effect = AsposeSlidesCloud::Object::Effect->new();
$effect->{shape_index} = 4;
$effect->{type} = "Fly";
$effect->{subtype} = "Bottom";
$effect->{preset_class_type} = "Entrance";
$effect->{trigger_type} = "OnClick";

my $interactive_sequence = AsposeSlidesCloud::Object::InteractiveSequence->new();
$interactive_sequence->{trigger_shape_index} = 2;
$interactive_sequence->{effects} = [$effect];

$slide_animation = $slides_api->create_special_slide_animation_interactive_sequence(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, sequence => $interactive_sequence);

$sequence_count = @{$slide_animation->{interactive_sequences}};
print("Interactive sequence count: ", $sequence_count);  # 1
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
import (
	"fmt"

	asposeslidescloud "github.com/aspose-slides-cloud/aspose-slides-cloud-go/v24"
)

func main() {
	configuration := asposeslidescloud.NewConfiguration()
	configuration.AppSid = "MyClientId"
	configuration.AppKey = "MyClientSecret"

	slidesApi := asposeslidescloud.NewAPIClient(configuration).SlidesApi

	fileName := "MyPresentation.pptx"
	var slideIndex int32 = 1
	slideType := string(asposeslidescloud.SpecialSlideType_LayoutSlide)

	effect := asposeslidescloud.NewEffect()
	effect.ShapeIndex = 4
	effect.Type_ = "Fly"
	effect.Subtype = "Bottom"
	effect.PresetClassType = "Entrance"
	effect.TriggerType = "OnClick"

	interactiveSequence := asposeslidescloud.NewInteractiveSequence()
	interactiveSequence.TriggerShapeIndex = 2
	interactiveSequence.Effects = []asposeslidescloud.IEffect{effect}

	slideAnimation, _, _ := slidesApi.CreateSpecialSlideAnimationInteractiveSequence(fileName, slideIndex, slideType, interactiveSequence, "", "", "")

	sequenceCount := len(slideAnimation.GetInteractiveSequences())
	fmt.Println("Interactive sequence count:", sequenceCount) // 1
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
