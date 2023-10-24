---
title: "Working with a Paragraph Animation"
type: docs
url: /working-with-a-paragraph-animation/
weight: 50
---

## **Introduction**

With Aspose.Slides Cloud API, you have the capability to access and manipulate animation effects that are associated with a particular paragraph. For instance, you can retrieve the existing animation settings for a specific paragraph to know how it currently appears in your presentation.

Additionally, you can set or adjust these animation effects. For example, you might want to apply a "Fade In" effect to a specific paragraph to make it smoothly appear during your presentation. By doing so, you are able to customize and enhance the visual impact of your slides, ensuring that your message is conveyed in the most engaging and effective manner possible.

{{% alert color="primary" %}} 
The following examples use the Aspose.Slides Cloud API described in [Read an Animation](https://docs.aspose.cloud/slides/read-an-animation/) and [Update a Main Sequence](https://docs.aspose.cloud/slides/update-a-main-sequence/).
{{% /alert %}} 

## **Examples**

Add the **Blink** animation effect to the **1st** paragraph of the **2nd** shape on the **1st** slide in **MyPresentation.pptx** document. Read information about the animation effect.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the Animation Effect**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/mainSequence" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @ParagraphEffect.json
```

ParagraphEffect.json content:

```javascript
{
    "type": "Blink",
    "shapeIndex": 2,
    "paragraphIndex": 1
}
```

**Get the Animation Effect**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation?shapeIndex=2&paragraphIndex=1" \
     -H "authorization: Bearer MyAccessToken"
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
            "paragraphIndex": 1,
            "triggerType": "OnClick",
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

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

var fileName = "MyPresentation.pptx";
var slideIndex = 1;
var shapeIndex = 2;
var paragraphIndex = 1;

var paragraphEffect = new Effect
{
    Type = Effect.TypeEnum.Blink,
    ShapeIndex = shapeIndex,
    ParagraphIndex = paragraphIndex
};

slidesApi.CreateAnimationEffect(fileName, slideIndex, paragraphEffect);

SlideAnimation animation = slidesApi.GetAnimation(fileName, slideIndex, shapeIndex, paragraphIndex);
Console.WriteLine(animation.MainSequence.Count); // 1
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

var fileName = "MyPresentation.pptx";
var slideIndex = 1;
var shapeIndex = 2;
var paragraphIndex = 1;

var paragraphEffect = new Effect();
paragraphEffect.setType(Effect.TypeEnum.BLINK);
paragraphEffect.setShapeIndex(shapeIndex);
paragraphEffect.setParagraphIndex(paragraphIndex);

slidesApi.createAnimationEffect(fileName, slideIndex, paragraphEffect, null, null, null);

SlideAnimation animation = slidesApi.getAnimation(fileName, slideIndex, shapeIndex, paragraphIndex, null, null, null);
System.out.println(animation.getMainSequence().size()); // 1
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;
use Aspose\Slides\Cloud\Sdk\Model\Effect;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$paragraphIndex = 1;

$paragraphEffect = new Effect();
$paragraphEffect->setType("Blink");
$paragraphEffect->setShapeIndex($shapeIndex);
$paragraphEffect->setParagraphIndex($paragraphIndex);

$slidesApi->createAnimationEffect($fileName, $slideIndex, $paragraphEffect);

$animation = $slidesApi->getAnimation($fileName, $slideIndex, $shapeIndex, $paragraphIndex);
print(count($animation->getMainSequence())); // 1
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
shape_index = 2
paragraph_index = 1

paragraph_effect = Effect.new
paragraph_effect.type = "Blink"
paragraph_effect.shape_index = shape_index
paragraph_effect.paragraph_index = paragraph_index

slides_api.create_animation_effect(file_name, slide_index, paragraph_effect)

animation = slides_api.get_animation(file_name, slide_index, shape_index, paragraph_index)
print animation.main_sequence.length # 1
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_animation import SlideAnimation
from asposeslidescloud.models.effect import Effect

configuration = Configuration()
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
paragraph_index = 1

paragraph_effect = Effect()
paragraph_effect.type = "Blink"
paragraph_effect.shape_index = shape_index
paragraph_effect.paragraph_index = paragraph_index

slides_api.create_animation_effect(file_name, slide_index, paragraph_effect)

animation = slides_api.get_animation(file_name, slide_index, shape_index, paragraph_index)
print(f"{ len(animation.main_sequence) }") # 1
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");

const slidesApi = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
const shapeIndex = 2;
const paragraphIndex = 1;

const paragraphEffect = new CloudSdk.SlideAnimation();
paragraphEffect.type = CloudSdk.Effect.TypeEnum.Blink;
paragraphEffect.shapeIndex = shapeIndex;
paragraphEffect.paragraphIndex = paragraphIndex;

slidesApi.createAnimationEffect(fileName, slideIndex, paragraphEffect).then(() => {
    slidesApi.getAnimation(fileName, slideIndex, shapeIndex, paragraphIndex).then((result) => {
        console.log(result.body.mainSequence.length); // 1
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"

api := asposeslidescloud.NewAPIClient(cfg)

paragraphEffect := asposeslidescloud.NewEffect()
paragraphEffect.Type_ = "Blink"
paragraphEffect.ShapeIndex = 2
paragraphEffect.ParagraphIndex = 1

_, _, e := api.SlidesApi.CreateAnimationEffect("MyPresentation.pptx", 1, paragraphEffect, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
}

var shapeIndex int32 = 2
var paragraphIndex int32 = 1

animation, _, e := api.SlidesApi.GetAnimation("MyPresentation.pptx", 1, &shapeIndex, &paragraphIndex, "", "MyStorageFolder", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v effects.", len(animation.GetMainSequence()))
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto fileName = L"MyPresentation.pptx";
    auto slideIndex = 1;
    auto shapeIndex = 2;
    auto paragraphIndex = 1;

    auto paragraphEffect = std::make_shared<Effect>();
    paragraphEffect->setType(L"Blink");
    paragraphEffect->setShapeIndex(shapeIndex);
    paragraphEffect->setParagraphIndex(paragraphIndex);

    slidesApi->createAnimationEffect(fileName, slideIndex, paragraphEffect);

    auto animation = slidesApi->getAnimation(fileName, slideIndex, shapeIndex, paragraphIndex).get();
    std::cout << animation->getMainSequence().size(); // 1
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

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
my $shape_index = 2;
my $paragraph_index = 1;

my $paragraph_effect = AsposeSlidesCloud::Object::Effect->new();
$paragraph_effect->{type} = "Blink";
$paragraph_effect->{shape_index} = $shape_index;
$paragraph_effect->{paragraph_index} = $paragraph_index;

my %effect_params = (name => $file_name, slide_index => $slide_index, effect => $paragraph_effect);
$slides_api->create_animation_effect(%effect_params);

my %animation_params = (name => $file_name, slide_index => $slide_index, shape_index => $shape_index, paragraph_index => $paragraph_index);
$animation = $slides_api->get_animation(%animation_params);
my $effect_count = @{$animation->{main_sequence}};
print($effect_count); # 1
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
