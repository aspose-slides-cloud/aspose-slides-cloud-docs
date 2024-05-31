---
title: "Add an Effect to a Main Sequence"
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
url: /add-an-effect-to-a-main-sequence/
weight: 70
---

## **Introduction**

Aspose.Slides Cloud API allows you to work with the collection of effects in the main animation sequence of a slide. You can use the following method to add an effect to a main animation sequence. 

## **CreateAnimationEffect**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation/mainSequence|POST|Adds an effect to a main animation sequence on a slide.|[CreateAnimationEffect](https://apireference.aspose.cloud/slides/#/Animation/CreateAnimationEffect)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|effect|`Effect`|body|true|The data transfer object with effect parameters.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Add the **Wipe** effect to the **second** shape on the **first** slide in **MyFolder/MyPresentation.pptx** document. The animation should occur on a **mouse click**.

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
curl POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/mainSequence?folder=MyFolder" \ 
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @MainSequence.json
```

MainSequence.json content:

```json
{
    "type": "Wipe",
    "presetClassType": "Entrance",
    "shapeIndex": 2,
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
            "shapeIndex": 2,
            "triggerType": "OnClick",
            "duration": 0.5,
            "triggerDelayTime": 0.0
        }
    ],
    "interactiveSequences": [],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare parameters for the effect.
        var wipeEffect = new Effect
        {
            Type = Effect.TypeEnum.Wipe,
            PresetClassType = Effect.PresetClassTypeEnum.Entrance,
            ShapeIndex = 2,
            TriggerType = Effect.TriggerTypeEnum.OnClick
        };

        // Add the effect to the main animation sequence.
        var slideAnimation = slidesApi.CreateAnimationEffect("MyPresentation.pptx", 1, wipeEffect, null, "MyFolder");

        // Print all effect types from the main sequence.
        foreach (var effect in slideAnimation.MainSequence)
        {
            Console.WriteLine($"The shape at index {effect.ShapeIndex} has the {effect.Type} effect.");
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Effect;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare parameters for the effect.
        Effect wipeEffect = new Effect();
        wipeEffect.setType(Effect.TypeEnum.WIPE);
        wipeEffect.setPresetClassType(Effect.PresetClassTypeEnum.ENTRANCE);
        wipeEffect.setShapeIndex(2);
        wipeEffect.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);

        // Add the effect to the main animation sequence.
        SlideAnimation slideAnimation = slidesApi.createAnimationEffect("MyPresentation.pptx", 1, wipeEffect, null, "MyFolder", null);

        // Print all effect types from the main sequence.
        for (Effect effect : slideAnimation.getMainSequence()) {
            System.out.println(String.format("The shape at index %d has the %s effect.", effect.getShapeIndex(), effect.getType()));
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Effect;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare parameters for the effect.
$wipeEffect = new Effect();
$wipeEffect->setType("Wipe");
$wipeEffect->setPresetClassType("Entrance");
$wipeEffect->setShapeIndex(2);
$wipeEffect->setTriggerType("OnClick");

// Add the effect to the main animation sequence.
$slideAnimation = $slidesApi->createAnimationEffect("MyPresentation.pptx", 1, $wipeEffect, null, "MyFolder");

// Print all effect types from the main sequence.
foreach ($slideAnimation->getMainSequence() as $effect) {
    echo "The shape at index " . $effect->getShapeIndex() . " has the " . $effect->getType() . " effect." . PHP_EOL;
}
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

# Prepare parameters for the effect.
wipe_effect = Effect.new
wipe_effect.type = "Wipe"
wipe_effect.preset_class_type = "Entrance"
wipe_effect.shape_index = 2
wipe_effect.trigger_type = "OnClick"

# Add the effect to the main animation sequence.
slide_animation = slides_api.create_animation_effect("MyPresentation.pptx", 1, wipe_effect, nil, "MyFolder")

# Print all effect types from the main sequence.
for effect in slide_animation.main_sequence
    puts "The shape at index #{effect.shape_index} has the #{effect.type} effect."
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.effect import Effect

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare parameters for the effect.
wipe_effect = Effect()
wipe_effect.type = "Wipe"
wipe_effect.preset_class_type = "Entrance"
wipe_effect.shape_index = 2
wipe_effect.trigger_type = "OnClick"

# Add the effect to the main animation sequence.
slide_animation = slides_api.create_animation_effect("MyPresentation.pptx", 1, wipe_effect, None, "MyFolder")

# Print all effect types from the main sequence.
for effect in slide_animation.main_sequence:
    print(f"The shape at index {effect.shape_index} has the {effect.type} effect.")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Prepare parameters for the effect.
const wipeEffect = new cloud.Effect();
wipeEffect.type = cloud.Effect.TypeEnum.Wipe;
wipeEffect.presetClassType = cloud.Effect.PresetClassTypeEnum.Entrance;
wipeEffect.shapeIndex = 2;
wipeEffect.triggerType = cloud.Effect.TriggerTypeEnum.OnClick;

// Add the effect to the main animation sequence.
slidesApi.createAnimationEffect("MyPresentation.pptx", 1, wipeEffect, null, "MyFolder").then(slideAnimation => {
    // Print all effect types from the main sequence.
    slideAnimation.body.mainSequence.forEach(effect => {
        console.log("The shape at index", effect.shapeIndex, "has the", effect.type, "effect.");
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Prepare parameters for the effect.
    auto wipeEffect = std::make_shared<Effect>();
    wipeEffect->setType(L"Wipe");
    wipeEffect->setPresetClassType(L"Entrance");
    wipeEffect->setShapeIndex(2);
    wipeEffect->setTriggerType(L"OnClick");

    // Add the effect to the main animation sequence.
    auto slideAnimation = slidesApi->createAnimationEffect(L"MyPresentation.pptx", 1, wipeEffect, L"", L"MyFolder").get();

    // Print all effect types from the main sequence.
    for (auto effect : slideAnimation->getMainSequence()) {
        std::wcout << "The shape at index " << effect->getShapeIndex() << " has the " << effect->getType() << " effect." << std::endl;
    }

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Effect;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare parameters for the effect.
my $wipe_effect = AsposeSlidesCloud::Object::Effect->new();
$wipe_effect->{type} = "Wipe";
$wipe_effect->{preset_class_type} = "Entrance";
$wipe_effect->{shape_index} = 2;
$wipe_effect->{trigger_type} = "OnClick";

# Add the effect to the main animation sequence.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, effect => $wipe_effect, folder => "MyFolder");
my $slide_animation = $slides_api->create_animation_effect(%parameters);

# Print all effect types from the main sequence.
for my $effect (@{$slide_animation->{main_sequence}}) {
    print("The shape at index " . $effect->{shape_index} . " has the " . $effect->{type} . " effect.\n");
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
