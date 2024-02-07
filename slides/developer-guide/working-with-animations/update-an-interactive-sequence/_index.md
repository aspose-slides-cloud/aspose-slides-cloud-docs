---
title: "Update an Interactive Sequence"
type: docs
url: /update-an-interactive-sequence/
weight: 20
---

## **Introduction**

The interactive animation sequence represents animations that are triggered by click a specified shape. The following method allows you to update the interactive sequence in a PowerPoint presentation.

## **CreateAnimationInteractiveSequence**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation/interactiveSequences|POST|Updates the interactive sequence of a presentation slide.|[CreateAnimationInteractiveSequence](https://apireference.aspose.cloud/slides/#/Animation/CreateAnimationInteractiveSequence)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|sequence|object|body|true|The collection of shape effects.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

**MyFolder/MyPresentation.pptx** document contains four shapes. Add the **fly** effect from **below** for the **fourth** shape by clicking on the **first** shape.

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
curl POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/interactiveSequences?folder=MyFolder" \
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
  "TriggerShapeIndex": 1
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
            "triggerShapeIndex": 1
        }
    ],
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
using System.Collections.Generic;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the shape effect.
        var newSequence = new InteractiveSequence
        {
            TriggerShapeIndex = 1,
            Effects = new List<Effect>
            {
                new Effect
                {
                    Type = Effect.TypeEnum.Fly,
                    Subtype = Effect.SubtypeEnum.Bottom,
                    PresetClassType = Effect.PresetClassTypeEnum.Entrance,
                    ShapeIndex = 4,
                    TriggerType = Effect.TriggerTypeEnum.OnClick
                }
            }
        };

        // Add the shape effect into the interactive sequence for the first slide.
        var slideAnimation = slidesApi.CreateAnimationInteractiveSequence("MyPresentation.pptx", 1, newSequence, null, "MyFolder");

        // Print indices of trigger shapes.
        foreach (var sequence in slideAnimation.InteractiveSequences)
        {
            Console.WriteLine(sequence.TriggerShapeIndex);
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
import com.aspose.slides.model.InteractiveSequence;

import java.util.ArrayList;
import java.util.List;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the shape effect.
        Effect effect = new Effect();
        effect.setType(Effect.TypeEnum.FLY);
        effect.setSubtype(Effect.SubtypeEnum.BOTTOM);
        effect.setPresetClassType(Effect.PresetClassTypeEnum.ENTRANCE);
        effect.setShapeIndex(4);
        effect.setTriggerType(Effect.TriggerTypeEnum.ONCLICK);

        List<Effect> effects = new ArrayList<Effect>();
        effects.add(effect);

        InteractiveSequence newSequence = new InteractiveSequence();
        newSequence.setTriggerShapeIndex(1);
        newSequence.setEffects(effects);

        // Add the shape effect into the interactive sequence for the first slide.
        SlideAnimation slideAnimation = slidesApi.createAnimationInteractiveSequence("MyPresentation.pptx", 1, newSequence, null, "MyFolder", null);

        // Print indices of trigger shapes.
        for (InteractiveSequence sequence : slideAnimation.getInteractiveSequences()) {
            System.out.println(sequence.getTriggerShapeIndex());
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
use Aspose\Slides\Cloud\Sdk\Model\InteractiveSequence;
use Aspose\Slides\Cloud\Sdk\Model\Effect;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare the shape effect.
$effect = new Effect();
$effect->setType("Fly");
$effect->setSubtype("Bottom");
$effect->setPresetClassType("Entrance");
$effect->setShapeIndex(4);
$effect->setTriggerType("OnClick");

$newSequence = new InteractiveSequence();
$newSequence->setTriggerShapeIndex(1);
$newSequence->setEffects([ $effect ]);

// Add the shape effect into the interactive sequence for the first slide.
$slideAnimation = $slidesApi->createAnimationInteractiveSequence("MyPresentation.pptx", 1, $newSequence, null, "MyFolder");

// Print indices of trigger shapes.
foreach ($slideAnimation->getInteractiveSequences() as $sequence) {
    print($sequence->getTriggerShapeIndex());
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

# Prepare the shape effect.
effect = Effect.new
effect.type = "Fly"
effect.subtype = "Bottom"
effect.preset_class_type = "Entrance"
effect.shape_index = 4
effect.trigger_type = "OnClick"

new_sequence = InteractiveSequence.new
new_sequence.trigger_shape_index = 1
new_sequence.effects = [effect]

# Add the shape effect into the interactive sequence for the first slide.
slide_animation = slides_api.create_animation_interactive_sequence("MyPresentation.pptx", 1, new_sequence, nil, "MyFolder")

# Print indices of trigger shapes.
for sequence in slide_animation.interactive_sequences
    puts sequence.trigger_shape_index
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.effect import Effect
from asposeslidescloud.models.interactive_sequence import InteractiveSequence

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare the shape effect.
effect = Effect()
effect.type = "Fly"
effect.subtype = "Bottom"
effect.preset_class_type = "Entrance"
effect.shape_index = 4
effect.trigger_type = "OnClick"

new_sequence = InteractiveSequence()
new_sequence.trigger_shape_index = 1
new_sequence.effects = [effect]

# Add the shape effect into the interactive sequence for the first slide.
slide_animation = slides_api.create_animation_interactive_sequence("MyPresentation.pptx", 1, new_sequence, None, "MyFolder")

# Print indices of trigger shapes.
for sequence in slide_animation.interactive_sequences:
    print(sequence.trigger_shape_index)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Prepare the shape effect.
const effect = new cloud.Effect();
effect.type = cloud.Effect.TypeEnum.Fly;
effect.subtype = cloud.Effect.SubtypeEnum.Bottom;
effect.presetClassType = cloud.Effect.PresetClassTypeEnum.Entrance;
effect.shapeIndex = 4;
effect.triggerType = cloud.Effect.TriggerTypeEnum.OnClick;

const newSequence = new cloud.InteractiveSequence();
newSequence.triggerShapeIndex = 1;
newSequence.effects = [effect];

// Add the shape effect into the interactive sequence for the first slide.
slidesApi.createAnimationInteractiveSequence("MyPresentation.pptx", 1, newSequence, null, "MyFolder").then(slideAnimation => {
    // Print indices of trigger shapes.
    slideAnimation.body.interactiveSequences.forEach(sequence => {
        console.log(sequence.triggerShapeIndex);
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

    // Prepare the shape effect.
    auto effect = std::make_shared<Effect>();
    effect->setType(L"Fly");
    effect->setSubtype(L"Bottom");
    effect->setPresetClassType(L"Entrance");
    effect->setShapeIndex(4);
    effect->setTriggerType(L"OnClick");

    auto newSequence = std::make_shared<InteractiveSequence>();
    newSequence->setTriggerShapeIndex(1);
    newSequence->setEffects({ effect });

    // Add the shape effect into the interactive sequence for the first slide.
    auto slideAnimation = slidesApi->createAnimationInteractiveSequence(L"MyPresentation.pptx", 1, newSequence, L"", L"MyFolder").get();

    // Print indices of trigger shapes.
    for (auto sequence : slideAnimation->getInteractiveSequences()) {
        std::wcout << sequence->getTriggerShapeIndex() << std::endl;
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
use AsposeSlidesCloud::Object::InteractiveSequence;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare the shape effect.
my $effect = AsposeSlidesCloud::Object::Effect->new();
$effect->{type} = "Fly";
$effect->{subtype} = "Bottom";
$effect->{preset_class_type} = "Entrance";
$effect->{shape_index} = 4;
$effect->{trigger_type} = "OnClick";

my @effects = ($effect);

my $new_sequence = AsposeSlidesCloud::Object::InteractiveSequence->new();
$new_sequence->{trigger_shape_index} = 1;
$new_sequence->{effects} = \@effects;

# Add the shape effect into the interactive sequence for the first slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, sequence => $new_sequence, folder => "MyFolder");
my $slide_animation = $slides_api->create_animation_interactive_sequence(%parameters);

# Print indices of trigger shapes.
for my $sequence (@{$slide_animation->{interactive_sequences}}) {
    print($sequence->{trigger_shape_index}. "\n");
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

dto := asposeslidescloud.NewInteractiveSequence()
dto.TriggerShapeIndex = 1

effect := asposeslidescloud.NewEffect()
effect.Type_ = "Fly"
effect.Subtype = "Bottom"
effect.PresetClassType = "Entrance"
effect.ShapeIndex = 4
effect.TriggerType = "OnClick"
dto.Effects = []asposeslidescloud.IEffect { effect }

animation, _, e := api.SlidesApi.CreateAnimationInteractiveSequence("MyPresentation.pptx", 1, dto, "", "MyStorageFolder", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    for i, sequence := range animation.GetInteractiveSequences() {
        fmt.Printf("Sequence %v, trigger shape index: %v.", i + 1, sequence.GetTriggerShapeIndex())

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
