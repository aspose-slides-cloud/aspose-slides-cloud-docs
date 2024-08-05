---
title: "Set an Animation"
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
url: /set-an-animation-on-a-special-slide/
weight: 20
---

## **Introduction**

Animation in PowerPoint presentations is a potent tool for creating interactive and engaging slides. It adds motion and transition effects between slides, making your presentation dynamic and memorable. The following method allows you to animate shapes or text in both main and interactive sequences on special slides (Master, Layout, or Notes) in presentations.

## **SetSpecialSlideAnimation**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/animation|PUT|Sets an animation for a shape or text on a special slide in a presentation saved in a storage.|[SetSpecialSlideAnimation](https://reference.aspose.cloud/slides/#/SpecialSlideAnimation/SetSpecialSlideAnimation)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|animation|`SlideAnimation`|body|true|The data transfer object with animation parameters.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the folder is located.|

### **Example 1**

The document **MyPresentation1.pptx** saved in the **default** storage contains three shapes on the **Layout** of the **first** regular slide. Set the **Fade** effect to the **second** shape and trigger it to begin playing **after the previous** animation. Set the **Blink** effect to the **third** shape and trigger it to begin playing when **clicked**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the Animations**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation1.pptx/slides/1/LayoutSlide/animation" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @Animation1.json
```

Animation1.json content:

```json
{
  "MainSequence": [
    {
      "ShapeIndex": 2,
      "Type": "Fade",
      "TriggerType": "AfterPrevious"
    },
    {
      "ShapeIndex": 3,
      "Type": "Blink",
      "TriggerType": "OnClick"
    }
  ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "mainSequence": [
    {
      "type": "Fade",
      "subtype": "None",
      "presetClassType": "Entrance",
      "shapeIndex": 2,
      "duration": 0.5,
      "triggerDelayTime": 0.0
    },
    {
      "type": "Blink",
      "subtype": "None",
      "presetClassType": "Emphasis",
      "shapeIndex": 3,
      "triggerType": "OnClick",
      "duration": 1.0,
      "triggerDelayTime": 0.0
    }
  ],
  "interactiveSequences": [],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1/animation",
    "relation": "self"
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
using System.Collections.Generic;

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string fileName = "MyPresentation1.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LayoutSlide;

        SlideAnimation newAnimation = new SlideAnimation
        {
            MainSequence = new List<Effect>
            {
                new Effect
                {
                    ShapeIndex = 2,
                    Type = Effect.TypeEnum.Fade,
                    TriggerType = Effect.TriggerTypeEnum.AfterPrevious
                },
                new Effect
                {
                    ShapeIndex = 3,
                    Type = Effect.TypeEnum.Blink,
                    TriggerType = Effect.TriggerTypeEnum.OnClick
                }
            }
        };

        SlideAnimation slideAnimation = slidesApi.SetSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation);

        int effectCount = slideAnimation.MainSequence.Count;
        Console.WriteLine("Effect count: " + effectCount); // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SpecialSlideType;
import com.aspose.slides.model.SlideAnimation;
import com.aspose.slides.model.Effect;

import java.util.List;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation1.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;

        Effect effect1 = new Effect();
        effect1.setShapeIndex(2);
        effect1.setType(Effect.TypeEnum.FADE);
        effect1.setTriggerType(Effect.TriggerTypeEnum.AFTERPREVIOUS);

        Effect effect2 = new Effect();
        effect2.setShapeIndex(3);
        effect2.setType(Effect.TypeEnum.BLINK);
        effect2.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);

        SlideAnimation newAnimation = new SlideAnimation();
        newAnimation.setMainSequence(Arrays.asList(effect1, effect2));

        SlideAnimation slideAnimation = slidesApi.setSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation, null, null, null);

        int effectCount = slideAnimation.getMainSequence().size();
        System.out.println("Effect count: " + effectCount); // 2
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
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation1.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;

$effect1 = new Effect();
$effect1->setShapeIndex(2);
$effect1->setType(Effect::TYPE_FADE);
$effect1->setTriggerType(Effect::TRIGGER_TYPE_AFTER_PREVIOUS);

$effect2 = new Effect();
$effect2->setShapeIndex(3);
$effect2->setType(Effect::TYPE_BLINK);
$effect2->setTriggerType(Effect::TRIGGER_TYPE_ON_CLICK);

$newAnimation = new SlideAnimation();
$newAnimation->setMainSequence([$effect1, $effect2]);

$slideAnimation = $slidesApi->setSpecialSlideAnimation($fileName, $slideIndex, $slideType, $newAnimation);

$effectCount = count($slideAnimation->getMainSequence());
echo "Effect count: ", $effectCount; // 2
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

file_name = "MyPresentation1.pptx"
slide_index = 1
slide_type = SpecialSlideType::LAYOUT_SLIDE

effect1 = Effect.new
effect1.shape_index = 2
effect1.type = "Fade"
effect1.trigger_type = "AfterPrevious"

effect2 = Effect.new
effect2.shape_index = 3
effect2.type = "Blink"
effect2.trigger_type = "OnClick"

new_animation = SlideAnimation.new
new_animation.main_sequence = [effect1, effect2]

slide_animation = slides_api.set_special_slide_animation(file_name, slide_index, slide_type, new_animation)

effect_count = slide_animation.main_sequence.length()
print "Effect count: ", effect_count # 2
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import SpecialSlideType
from asposeslidescloud.models import Effect
from asposeslidescloud.models import SlideAnimation

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation1.pptx"
slide_index = 1
slide_type = SpecialSlideType.LAYOUTSLIDE

effect1 = Effect()
effect1.shape_index = 2
effect1.type = "Fade"
effect1.trigger_type = "AfterPrevious"

effect2 = Effect()
effect2.shape_index = 3
effect2.type = "Blink"
effect2.trigger_type = "OnClick"

new_animation = SlideAnimation()
new_animation.main_sequence = [effect1, effect2]

slide_animation = slides_api.set_special_slide_animation(file_name, slide_index, slide_type, new_animation)

effect_count = len(slide_animation.main_sequence)
print("Effect count:", effect_count)  # 2
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation1.pptx";
slideIndex = 1;
slideType = cloudSdk.SpecialSlideType.LayoutSlide;

effect1 = new cloudSdk.Effect();
effect1.shapeIndex = 2;
effect1.type = cloudSdk.Effect.TypeEnum.Fade;
effect1.triggerType = cloudSdk.Effect.TriggerTypeEnum.AfterPrevious;

effect2 = new cloudSdk.Effect();
effect2.shapeIndex = 3;
effect2.type = cloudSdk.Effect.TypeEnum.Blink;
effect2.triggerType = cloudSdk.Effect.TriggerTypeEnum.OnClick;

newAnimation = new cloudSdk.SlideAnimation();
newAnimation.mainSequence = [effect1, effect2];

slidesApi.setSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation).then(slideAnimation => {
    effectCount = slideAnimation.body.mainSequence.length;
    console.log("Effect count:", effectCount); // 2
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

    const wchar_t* fileName = L"MyPresentation1.pptx";
    int slideIndex = 1;
    const wchar_t* slideType = L"LayoutSlide";

    std::shared_ptr<Effect> effect1 = std::make_shared<Effect>();
    effect1->setShapeIndex(2);
    effect1->setType(L"Fade");
    effect1->setTriggerType(L"AfterPrevious");

    std::shared_ptr<Effect> effect2 = std::make_shared<Effect>();
    effect2->setShapeIndex(3);
    effect2->setType(L"Blink");
    effect2->setTriggerType(L"OnClick");

    std::shared_ptr<SlideAnimation> newAnimation = std::make_shared<SlideAnimation>();
    newAnimation->setMainSequence({ effect1, effect2 });

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->setSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation).get();

    int effectCount = slideAnimation->getMainSequence().size();
    std::wcout << L"Effect count: " << effectCount; // 2
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Effect;
use AsposeSlidesCloud::Object::SlideAnimation;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation1.pptx";
my $slide_index = 1;
my $slide_type = "LayoutSlide";

my $effect1 = AsposeSlidesCloud::Object::Effect->new();
$effect1->{shape_index} = 2;
$effect1->{type} = "Fade";
$effect1->{trigger_type} = "AfterPrevious";

my $effect2 = AsposeSlidesCloud::Object::Effect->new();
$effect2->{shape_index} = 3;
$effect2->{type} = "Blink";
$effect2->{trigger_type} = "OnClick";

my $new_animation = AsposeSlidesCloud::Object::SlideAnimation->new();
$new_animation->{main_sequence} = [$effect1, $effect2];

my $slide_animation = $slides_api->set_special_slide_animation(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, animation => $new_animation);

my $effect_count = @{$slide_animation->{main_sequence}};
print("Effect count: ", $effect_count); # 2
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

	fileName := "MyPresentation1.pptx"
	var slideIndex int32 = 1
	slideType := string(asposeslidescloud.SpecialSlideType_LayoutSlide)

	effect1 := asposeslidescloud.NewEffect()
	effect1.ShapeIndex = 2
	effect1.Type_ = "Fade"
	effect1.TriggerType = "AfterPrevious"

	effect2 := asposeslidescloud.NewEffect()
	effect2.ShapeIndex = 3
	effect2.Type_ = "Blink"
	effect2.TriggerType = "OnClick"

	newAnimation := asposeslidescloud.NewSlideAnimation()
	newAnimation.MainSequence = []asposeslidescloud.IEffect{effect1, effect2}

	slideAnimation, _, _ := slidesApi.SetSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation, "", "", "")

	mainEffectCount := len(slideAnimation.GetMainSequence())
	fmt.Println("Effect count:", mainEffectCount)
}
```

{{< /tab >}}

{{< /tabs >}}

### **Example 2**

The document **MyPresentation2.pptx** saved in the **default** storage contains **four** shapes on the **Layout** slide of the **first** regular slide. Set the **Fly** effect from **below** for the **fourth** shape by clicking on the **second** shape.

**cURL Solution**

{{< tabs tabTotal="2" tabID="11" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the Animation**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation2.pptx/slides/1/LayoutSlide/animation" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @Animation2.json
```

Animation2.json content:

```json
{
  "InteractiveSequences": [
    {
      "TriggerShapeIndex": 2,
      "Effects": [
        {
          "ShapeIndex": 4,
          "Type": "Fly",
          "Subtype": "Bottom",
          "TriggerType": "OnClick"
        }
      ]
    }
  ]
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
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation2.pptx/slides/1/LayoutSlide/animation",
    "relation": "self",
    "slideIndex": 1
  }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

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

        string fileName = "MyPresentation2.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LayoutSlide;

        SlideAnimation newAnimation = new SlideAnimation
        {
            InteractiveSequences = new List<InteractiveSequence>
            {
                new InteractiveSequence
                {
                    TriggerShapeIndex = 2,
                    Effects = new List<Effect>
                    {
                        new Effect
                        {
                            ShapeIndex = 4,
                            Type = Effect.TypeEnum.Fly,
                            Subtype = Effect.SubtypeEnum.Bottom,
                            TriggerType = Effect.TriggerTypeEnum.OnClick
                        },
                    }
                }
            }
        };

        SlideAnimation slideAnimation = slidesApi.SetSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation);

        int interactiveSequenceCount = slideAnimation.InteractiveSequences.Count;
        Console.WriteLine("Interactive sequence count: " + interactiveSequenceCount); // 1
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SpecialSlideType;
import com.aspose.slides.model.InteractiveSequence;
import com.aspose.slides.model.SlideAnimation;
import com.aspose.slides.model.Effect;

import java.util.List;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation2.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;

        Effect effect = new Effect();
        effect.setShapeIndex(4);
        effect.setType(Effect.TypeEnum.FLY);
        effect.setSubtype(Effect.SubtypeEnum.BOTTOM);
        effect.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);

        InteractiveSequence interactiveSequence = new InteractiveSequence();
        interactiveSequence.setTriggerShapeIndex(2);
        interactiveSequence.setEffects(Arrays.asList(effect));

        SlideAnimation newAnimation = new SlideAnimation();
        newAnimation.setInteractiveSequences(Arrays.asList(interactiveSequence));

        SlideAnimation slideAnimation = slidesApi.setSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation, null, null, null);

        int interactiveSequenceCount = slideAnimation.getInteractiveSequences().size();
        System.out.println("Interactive sequence count: " + interactiveSequenceCount); // 1
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
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation2.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;

$effect = new Effect();
$effect->setShapeIndex(4);
$effect->setType(Effect::TYPE_FLY);
$effect->setSubtype(Effect::SUBTYPE_BOTTOM);
$effect->setTriggerType(Effect::TRIGGER_TYPE_ON_CLICK);

$interactiveSequence = new InteractiveSequence();
$interactiveSequence->setTriggerShapeIndex(2);
$interactiveSequence->setEffects([$effect]);

$newAnimation = new SlideAnimation();
$newAnimation->setInteractiveSequences([$interactiveSequence]);

$slideAnimation = $slidesApi->setSpecialSlideAnimation($fileName, $slideIndex, $slideType, $newAnimation);

$interactiveSequenceCount = count($slideAnimation->getInteractiveSequences());
echo "Interactive sequence count: ", $interactiveSequenceCount; // 1
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

file_name = "MyPresentation2.pptx"
slide_index = 1
slide_type = SpecialSlideType::LAYOUT_SLIDE

effect = Effect.new
effect.shape_index = 4
effect.type = "Fly"
effect.subtype = "Bottom"
effect.trigger_type = "OnClick"

interactive_sequence = InteractiveSequence.new
interactive_sequence.trigger_shape_index = 2
interactive_sequence.effects = [effect]

new_animation = SlideAnimation.new
new_animation.interactive_sequences = [interactive_sequence]

slide_animation = slides_api.set_special_slide_animation(file_name, slide_index, slide_type, new_animation)

interactive_sequence_count = slide_animation.interactive_sequences.length()
print "Interactive sequence count: ", interactive_sequence_count # 1
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud import SpecialSlideType
from asposeslidescloud.models.effect import Effect
from asposeslidescloud.models.interactive_sequence import InteractiveSequence
from asposeslidescloud.models.slide_animation import SlideAnimation

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation2.pptx"
slide_index = 1
slide_type = SpecialSlideType.LAYOUTSLIDE

effect = Effect()
effect.shape_index = 4
effect.type = "Fly"
effect.subtype = "Bottom"
effect.trigger_type = "OnClick"

interactive_sequence = InteractiveSequence()
interactive_sequence.trigger_shape_index = 2
interactive_sequence.effects = [effect]

new_animation = SlideAnimation()
new_animation.interactive_sequences = [interactive_sequence]

slide_animation = slides_api.set_special_slide_animation(file_name, slide_index, slide_type, new_animation)

interactive_sequence_count = len(slide_animation.interactive_sequences)
print("Interactive sequence count:", interactive_sequence_count)  # 1
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation2.pptx";
slideIndex = 1;
slideType = cloudSdk.SpecialSlideType.LayoutSlide;

effect = new cloudSdk.Effect();
effect.shapeIndex = 4;
effect.type = cloudSdk.Effect.TypeEnum.Fly;
effect.subtype = cloudSdk.Effect.SubtypeEnum.Bottom;
effect.triggerType = cloudSdk.Effect.TriggerTypeEnum.OnClick;

interactiveSequence = new cloudSdk.InteractiveSequence();
interactiveSequence.triggerShapeIndex = 2;
interactiveSequence.effects = [effect];

newAnimation = new cloudSdk.SlideAnimation();
newAnimation.interactiveSequences = [interactiveSequence];

slidesApi.setSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation).then(slideAnimation => {
    interactiveSequenceCount = slideAnimation.body.interactiveSequences.length;
    console.log("Interactive sequence count:", interactiveSequenceCount); // 1
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

    const wchar_t* fileName = L"MyPresentation2.pptx";
    int slideIndex = 1;
    const wchar_t* slideType = L"LayoutSlide";

    std::shared_ptr<Effect> effect = std::make_shared<Effect>();
    effect->setShapeIndex(4);
    effect->setType(L"Fly");
    effect->setSubtype(L"Bottom");
    effect->setTriggerType(L"OnClick");

    std::shared_ptr<InteractiveSequence> interactiveSequence = std::make_shared<InteractiveSequence>();
    interactiveSequence->setTriggerShapeIndex(2);
    interactiveSequence->setEffects({ effect });

    std::shared_ptr<SlideAnimation> newAnimation = std::make_shared<SlideAnimation>();
    newAnimation->setInteractiveSequences({ interactiveSequence });

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->setSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation).get();

    int interactiveSequenceCount = slideAnimation->getInteractiveSequences().size();
    std::wcout << L"Interactive sequence count: " << interactiveSequenceCount; // 1
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Effect;
use AsposeSlidesCloud::Object::InteractiveSequence;
use AsposeSlidesCloud::Object::SlideAnimation;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation2.pptx";
my $slide_index = 1;
my $slide_type = "LayoutSlide";

my $effect = AsposeSlidesCloud::Object::Effect->new();
$effect->{shape_index} = 4;
$effect->{type} = "Fly";
$effect->{subtype} = "Bottom";
$effect->{trigger_type} = "OnClick";

my $interactive_sequence = AsposeSlidesCloud::Object::InteractiveSequence->new();
$interactive_sequence->{trigger_shape_index} = 2;
$interactive_sequence->{effects} = [$effect];

my $new_animation = AsposeSlidesCloud::Object::SlideAnimation->new();
$new_animation->{interactive_sequences} = [$interactive_sequence];

my $slide_animation = $slides_api->set_special_slide_animation(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, animation => $new_animation);

my $interactive_sequence_count = @{$slide_animation->{interactive_sequences}};
print("Interactive sequence count: ", $interactive_sequence_count); # 1
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

	fileName := "MyPresentation2.pptx"
	var slideIndex int32 = 1
	slideType := string(asposeslidescloud.SpecialSlideType_LayoutSlide)

	effect := asposeslidescloud.NewEffect()
	effect.ShapeIndex = 4
	effect.Type_ = "Fly"
	effect.Subtype = "Bottom"
	effect.TriggerType = "OnClick"

	interactiveSequence := asposeslidescloud.NewInteractiveSequence()
	interactiveSequence.TriggerShapeIndex = 2
	interactiveSequence.Effects = []asposeslidescloud.IEffect{effect}

	newAnimation := asposeslidescloud.NewSlideAnimation()
	newAnimation.InteractiveSequences = []asposeslidescloud.IInteractiveSequence{interactiveSequence}

	slideAnimation, _, _ := slidesApi.SetSpecialSlideAnimation(fileName, slideIndex, slideType, newAnimation, "", "", "")

	interactiveSequenceCount := len(slideAnimation.GetInteractiveSequences())
	fmt.Println("Interactive sequence count:", interactiveSequenceCount) // 1
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
