---
title: "Update an Effect in a Main Sequence"
type: docs
url: /update-an-effect-in-a-main-sequence-on-a-special-slide/
weight: 80
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, and modify animations in PowerPoint presentations. You can use the following method to update effects in main animation sequences on special slides (Master, Layout, or Notes) in presentations.

## **UpdateSpecialSlideAnimationEffect**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/mainSequence/{effectIndex}|PUT|Updates an effect in a main animation sequence on a special slide in a presentation saved in a storage.|[UpdateSpecialSlideAnimationEffect](https://reference.aspose.cloud/slides/#/SpecialSlideAnimation/UpdateSpecialSlideAnimationEffect)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|effectIndex|integer|path|true|The 1-based index of an effect to be modified.|
|effect|`Effect`|body|true|The data transfer object with effect parameters.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Example**

The document **MyPresentation.pptx** saved in the **default** storage contains two effects in the **main** animation sequence on the **Layout** of the **first** slide. Change the **second** effect to **Blink** and trigger it **with the previous** effect.

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
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/LayoutSlide/animation/mainSequence/2" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @Effect.json
```

Effect.json content:

```json
{
  "Type": "Blink",
  "TriggerType": "WithPrevious"
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
      "animateTextType": "AllAtOnce",
      "shapeIndex": 1,
      "triggerType": "OnClick",
      "duration": 0.5,
      "triggerDelayTime": 0
    },
    {
      "type": "Blink",
      "subtype": "None",
      "presetClassType": "Emphasis",
      "animateTextType": "AllAtOnce",
      "shapeIndex": 2,
      "triggerType": "WithPrevious",
      "duration": 1,
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
        SpecialSlideType slideType = SpecialSlideType.LayoutSlide;
        int effectIndex = 1;
        
        Effect effect = new Effect
        {
            Type = Effect.TypeEnum.Blink,
            TriggerType = Effect.TriggerTypeEnum.WithPrevious
        };

        SlideAnimation slideAnimation = slidesApi.UpdateSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex, effect);

        Effect animationEffect = slideAnimation.MainSequence[effectIndex - 1];
        Console.WriteLine("Effect type: " + animationEffect.Type); // Blink
        Console.WriteLine("Trigger Type: " + animationEffect.TriggerType); // WithPrevious
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SpecialSlideType;
import com.aspose.slides.model.Effect;
import com.aspose.slides.model.SlideAnimation;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;
        int effectIndex = 1;

        Effect effect = new Effect();
        effect.setType(Effect.TypeEnum.BLINK);
        effect.setTriggerType(Effect.TriggerTypeEnum.WITHPREVIOUS);

        SlideAnimation slideAnimation = slidesApi.updateSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex, effect, null, null, null);

        Effect animationEffect = slideAnimation.getMainSequence().get(effectIndex - 1);
        System.out.println("Effect type: " + animationEffect.getType()); // Blink
        System.out.println("Trigger Type: " + animationEffect.getTriggerType()); // WithPrevious
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

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;
$effectIndex = 1;

$effect = new Effect();
$effect->setType(Effect::TYPE_BLINK);
$effect->setTriggerType(Effect::TRIGGER_TYPE_WITH_PREVIOUS);

$slideAnimation = $slidesApi->updateSpecialSlideAnimationEffect($fileName, $slideIndex, $slideType, $effectIndex, $effect);

$animationEffect = $slideAnimation->getMainSequence()[$effectIndex - 1];
echo "Effect type: ", $animationEffect->getType(), "\n"; // Blink
echo "Trigger Type: ", $animationEffect->getTriggerType(); // WithPrevious
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
effect_index = 1

effect = Effect.new
effect.type = "Blink"
effect.trigger_type = "WithPrevious"

slide_animation = slides_api.update_special_slide_animation_effect(file_name, slide_index, slide_type, effect_index, effect)

animation_effect = slide_animation.main_sequence[effect_index - 1]
puts "Effect type: #{animation_effect.type}" # Blink
puts "Trigger Type: #{animation_effect.trigger_type}" # WithPrevious
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
effect_index = 1

effect = Effect()
effect.type = "Blink"
effect.trigger_type = "WithPrevious"

slide_animation = slides_api.update_special_slide_animation_effect(file_name, slide_index, slide_type, effect_index, effect)

animation_effect = slide_animation.main_sequence[effect_index - 1]
print("Effect type:", animation_effect.type)  # Blink
print("Trigger Type:", animation_effect.trigger_type)  # WithPrevious
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
slideType = cloudSdk.SpecialSlideType.LayoutSlide;
effectIndex = 1;

effect = new cloudSdk.Effect();
effect.type = cloudSdk.Effect.TypeEnum.Blink;
effect.triggerType = cloudSdk.Effect.TriggerTypeEnum.WithPrevious;

slidesApi.updateSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex, effect).then(slideAnimation => {
    animationEffect = slideAnimation.body.mainSequence[effectIndex - 1];
    console.log("Effect type:", animationEffect.type); // Blink
    console.log("Trigger Type: " + animationEffect.triggerType); // WithPrevious
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
    int effectIndex = 1;

    std::shared_ptr<Effect> effect = std::make_shared<Effect>();
    effect->setType(L"Blink");
    effect->setTriggerType(L"WithPrevious");

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->updateSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex, effect).get();

    std::shared_ptr<Effect> animationEffect = slideAnimation->getMainSequence()[effectIndex - 1];
    std::wcout << "Effect type: " << animationEffect->getType() << "\n"; // Blink
    std::wcout << "Trigger Type: " << animationEffect->getTriggerType(); // WithPrevious
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
my $slide_type = "LayoutSlide";
my $effect_index = 1;

my $effect = AsposeSlidesCloud::Object::Effect->new();
$effect->{type} = "Blink";
$effect->{trigger_type} = "WithPrevious";

my $slide_animation = $slides_api->update_special_slide_animation_effect(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, effect_index => $effect_index, effect => $effect);

my $animation_effect = $slide_animation->{main_sequence}[$effect_index - 1];
print("Effect type: ", $animation_effect->{type}, "\n"); # Blink
print("Trigger Type: ", $animation_effect->{trigger_type}); # WithPrevious
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
	var effectIndex int32 = 1

	effect := asposeslidescloud.NewEffect()
	effect.Type_ = "Blink"
	effect.TriggerType = "WithPrevious"

	slideAnimation, _, _ := slidesApi.UpdateSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex, effect, "", "", "")

	animationEffect := slideAnimation.GetMainSequence()[effectIndex-1]
	fmt.Println("Effect type:", animationEffect.GetType())         // Blink
	fmt.Println("Trigger Type:", animationEffect.GetTriggerType()) // WithPrevious
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
