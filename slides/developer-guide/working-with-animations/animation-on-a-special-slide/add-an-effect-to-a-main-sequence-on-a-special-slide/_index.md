---
title: "Add an Effect to a Main Sequence"
type: docs
url: /add-an-effect-to-a-main-sequence-on-a-special-slide/
weight: 70
---

## **Introduction**

Aspose.Slides Cloud API allows you to work with the collection of effects in the main animation sequence in PowerPoint presentations. You can use the following method to add effects to main animation sequences on special slides (Master, Layout, or Notes). 

## **CreateSpecialSlideAnimationEffect**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/mainSequence|POST|Adds an effect to a main animation sequence on a special slide in a presentation saved in a storage.|[CreateSpecialSlideAnimationEffect](https://reference.aspose.cloud/slides/#/SpecialSlideAnimation/CreateSpecialSlideAnimationEffect)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|effect|`Effect`|body|true|The data transfer object with effect parameters.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

The document **MyPresentation.pptx** saved in the **default** storage contains two shapes on the **Layout** of the **first** slide. Add the **Wipe** effect to the **second** shape. The animation should play on a **mouse click**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the Wipe Effect**

```sh
curl POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/LayoutSlide/animation/mainSequence" \ 
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @Effect.json
```

Effect.json content:

```json
{
    "shapeIndex": 2,
    "type": "Wipe",
    "presetClassType": "Entrance",
    "triggerType": "OnClick"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "mainSequence": [
    {
      "type": "Wipe",
      "subtype": "Bottom",
      "presetClassType": "Entrance",
      "animateTextType": "AllAtOnce",
      "shapeIndex": 2,
      "triggerType": "OnClick",
      "duration": 0.5,
      "triggerDelayTime": 0
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

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

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
        SpecialSlideType slideType = SpecialSlideType.LayoutSlide;

        Effect effect = new Effect
        {
            ShapeIndex = 2,
            Type = Effect.TypeEnum.Wipe,
            PresetClassType = Effect.PresetClassTypeEnum.Entrance,
            TriggerType = Effect.TriggerTypeEnum.OnClick
        };

        SlideAnimation slideAnimation = slidesApi.CreateSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effect);


        int effectCount = slideAnimation.MainSequence.Count;
        Console.WriteLine("Number of effects: " + effectCount);
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
import com.aspose.slides.model.SpecialSlideType;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;

        Effect effect = new Effect();
        effect.setShapeIndex(2);
        effect.setType(Effect.TypeEnum.WIPE);
        effect.setPresetClassType(Effect.PresetClassTypeEnum.ENTRANCE);
        effect.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);

        SlideAnimation slideAnimation = slidesApi.createSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effect, null, null, null);

        int effectCount = slideAnimation.getMainSequence().size();
        System.out.println("Number of effects: " + effectCount);
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

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;

$effect = new Effect();
$effect->setShapeIndex(2);
$effect->setType(Effect::TYPE_WIPE);
$effect->setPresetClassType(Effect::PRESET_CLASS_TYPE_ENTRANCE);
$effect->setTriggerType(Effect::TRIGGER_TYPE_ON_CLICK);

$slideAnimation = $slidesApi->createSpecialSlideAnimationEffect($fileName, $slideIndex, $slideType, $effect);

$effectCount = count($slideAnimation->getMainSequence());
echo "Number of effects: ", $effectCount;
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
effect.shape_index = 2
effect.type = "Wipe"
effect.preset_class_type = "Entrance"
effect.trigger_type = "OnClick"

slide_animation = slides_api.create_special_slide_animation_effect(file_name, slide_index, slide_type, effect)

effect_count = slide_animation.main_sequence.length()
print "Number of effects: ", effect_count
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import SpecialSlideType
from asposeslidescloud.models import Effect

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = SpecialSlideType.LAYOUTSLIDE

effect = Effect()
effect.shape_index = 2
effect.type = "Wipe"
effect.preset_class_type = "Entrance"
effect.trigger_type = "OnClick"

slide_animation = slides_api.create_special_slide_animation_effect(file_name, slide_index, slide_type, effect)

effect_count = len(slide_animation.main_sequence)
print("Number of effects:", effect_count)
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
effect.shapeIndex = 2;
effect.type = cloudSdk.Effect.TypeEnum.Wipe;
effect.presetClassType = cloudSdk.Effect.PresetClassTypeEnum.Entrance;
effect.triggerType = cloudSdk.Effect.TriggerTypeEnum.OnClick;

slidesApi.createSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effect).then(slideAnimation => {
    effectCount = slideAnimation.body.mainSequence.length;
    console.log("Number of effects:", effectCount);
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
    effect->setShapeIndex(2);
    effect->setType(L"Wipe");
    effect->setPresetClassType(L"Entrance");
    effect->setTriggerType(L"OnClick");

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->createSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effect).get();

    int effectCount = slideAnimation->getMainSequence().size();
    std::wcout << L"Number of effects: " << effectCount;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Effect;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $slide_type = "LayoutSlide";

my $effect = AsposeSlidesCloud::Object::Effect->new();
$effect->{shape_index} = 2;
$effect->{type} = "Wipe";
$effect->{preset_class_type} = "Entrance";
$effect->{trigger_type} = "OnClick";

$slide_animation = $slides_api->create_special_slide_animation_effect(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, effect => $effect);

$effect_count = @{$slide_animation->{main_sequence}};
print("Number of effects: ", $effect_count);
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
	effect.ShapeIndex = 2
	effect.Type_ = "Wipe"
	effect.PresetClassType = "Entrance"
	effect.TriggerType = "OnClick"

	slideAnimation, _, _ := slidesApi.CreateSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effect, "", "", "")

	effectCount := len(slideAnimation.GetMainSequence())
	fmt.Println("Number of effects:", effectCount)
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
