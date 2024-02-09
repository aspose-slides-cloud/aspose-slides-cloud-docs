---
title: "Update an Effect in a Main Sequence"
type: docs
url: /update-an-effect-in-a-main-sequence/
weight: 31
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, and modify animations in PowerPoint presentations. You can use the following method to update an effect in a main animation sequence on a presentation slide.

## **UpdateAnimationEffect**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation/mainSequence/{effectIndex}|PUT|Updates an effect in a main animation sequence on a slide.|[UpdateAnimationEffect](https://reference.aspose.cloud/slides/#/Animation/UpdateAnimationEffect)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|effectIndex|integer|path|true|The 1-based index of an effect to be modified.|
|effect|`Effect`|body|true|The data transfer object with effect parameters.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Example**

The document **MyPresentation.pptx** contains two effects in the **main** animation sequence on the **first** slide. Change the **second** effect to **Blink** and trigger it **with the previous** effect.

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
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/mainSequence/2" \
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
      "shapeIndex": 1,
      "triggerType": "OnClick",
      "duration": 0.5,
      "triggerDelayTime": 0.0
    },
    {
      "type": "Blink",
      "subtype": "None",
      "presetClassType": "Emphasis",
      "shapeIndex": 2,
      "triggerType": "WithPrevious",
      "duration": 1.0,
      "triggerDelayTime": 0.0
    }
  ],
  "interactiveSequences": [],
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
        int effectIndex = 2;

        Effect updateEffect = new Effect
        {
            Type = Effect.TypeEnum.Blink,
            TriggerType = Effect.TriggerTypeEnum.WithPrevious
        };

        SlideAnimation slideAnimation = slidesApi.UpdateAnimationEffect(fileName, slideIndex, effectIndex, updateEffect);

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
import com.aspose.slides.model.Effect;
import com.aspose.slides.model.SlideAnimation;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int effectIndex = 2;

        Effect updateEffect = new Effect();
        updateEffect.setType(Effect.TypeEnum.BLINK);
        updateEffect.setTriggerType(Effect.TriggerTypeEnum.WITHPREVIOUS);

        SlideAnimation slideAnimation = slidesApi.updateAnimationEffect(fileName, slideIndex, effectIndex, updateEffect, null, null, null);

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
use Aspose\Slides\Cloud\Sdk\Model\Effect;
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$effectIndex = 2;

$updateEffect = new Effect();
$updateEffect->setType(Effect::TYPE_BLINK);
$updateEffect->setTriggerType(Effect::TRIGGER_TYPE_WITH_PREVIOUS);

$slideAnimation = $slidesApi->updateAnimationEffect($fileName, $slideIndex, $effectIndex, $updateEffect);

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
effect_index = 2

update_effect = Effect.new
update_effect.type = "Blink"
update_effect.trigger_type = "WithPrevious"

slide_animation = slides_api.update_animation_effect(file_name, slide_index, effect_index, update_effect)

animation_effect = slide_animation.main_sequence[effect_index - 1]
puts "Effect type: #{animation_effect.type}" # Blink
puts "Trigger Type: #{animation_effect.trigger_type}" # WithPrevious
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.effect import Effect

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
effect_index = 2

update_effect = Effect()
update_effect.type = "Blink"
update_effect.trigger_type = "WithPrevious"

slide_animation = slides_api.update_animation_effect(file_name, slide_index, effect_index, update_effect)

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
effectIndex = 2;

updateEffect = new cloudSdk.Effect();
updateEffect.type = cloudSdk.Effect.TypeEnum.Blink;
updateEffect.triggerType = cloudSdk.Effect.TriggerTypeEnum.WithPrevious;

slidesApi.updateAnimationEffect(fileName, slideIndex, effectIndex, updateEffect).then(slideAnimation => {
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
    int effectIndex = 2;

    std::shared_ptr<Effect> updateEffect = std::make_shared<Effect>();
    updateEffect->setType(L"Blink");
    updateEffect->setTriggerType(L"WithPrevious");

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->updateAnimationEffect(fileName, slideIndex, effectIndex, updateEffect).get();

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
my $effect_index = 2;

my $update_effect = AsposeSlidesCloud::Object::Effect->new();
$update_effect->{type} = "Blink";
$update_effect->{trigger_type} = "WithPrevious";

my %parameters = (name => $file_name, slide_index => $slide_index, effect_index => $effect_index, effect => $update_effect);
my $slide_animation = $slides_api->update_animation_effect(%parameters);

my $animation_effect = $slide_animation->{main_sequence}[$effect_index - 1];
print("Effect type: ", $animation_effect->{type}, "\n"); # Blink
print("Trigger Type: ", $animation_effect->{trigger_type}); # WithPrevious
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
