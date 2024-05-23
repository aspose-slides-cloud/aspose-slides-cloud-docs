---
title: "Delete Effects from an Interactive Sequence"
type: docs
url: /delete-effects-from-an-interactive-sequence/
weight: 55
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, and modify animations in PowerPoint presentations. You can also delete effects from an interactive animation sequence on a presentation slide using the following method.

## **DeleteAnimationInteractiveSequenceEffect**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation/interactiveSequences/{sequenceIndex}/{effectIndex}|DELETE|Deletes an effect from an interactive animation sequence on a slide.|[DeleteAnimationInteractiveSequenceEffect](https://reference.aspose.cloud/slides/#/Animation/DeleteAnimationInteractiveSequenceEffect)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|sequenceIndex|integer|path|true|The 1-based index of an interactive sequence.|
|effectIndex|integer|path|true|The 1-based index of an effect to be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Example**

The document **MyPresentation.pptx** contains **one** interactive animation sequence with two effects on the **first** slide. Delete the **first** effect.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Effect**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/interactiveSequences/1/1" \
     -H "authorization: Bearer MyAccessToken"
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

        SlideAnimation slideAnimation = slidesApi.DeleteAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, effectIndex);

        int effectCount = slideAnimation.InteractiveSequences[sequenceIndex - 1].Effects.Count;
        Console.WriteLine("Effect count: " + effectCount); // 1
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SlideAnimation;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int sequenceIndex = 1;
        int effectIndex = 1;

        SlideAnimation slideAnimation = slidesApi.deleteAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, effectIndex, null, null, null);

        int effectCount = slideAnimation.getInteractiveSequences().get(sequenceIndex - 1).getEffects().size();
        System.out.println("Effect count: " + effectCount); // 1
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$sequenceIndex = 1;
$effectIndex = 1;

$slideAnimation = $slidesApi->deleteAnimationInteractiveSequenceEffect($fileName, $slideIndex, $sequenceIndex, $effectIndex);

$effectCount = count($slideAnimation->getInteractiveSequences()[$sequenceIndex - 1]->getEffects());
echo "Effect count: ", $effectCount; // 1
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

slide_animation = slides_api.delete_animation_interactive_sequence_effect(file_name, slide_index, sequence_index, effect_index)

effect_count = slide_animation.interactive_sequences[sequence_index - 1].effects.length()
print "Effect count: ", effect_count # 1
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
sequence_index = 1
effect_index = 1

slide_animation = slides_api.delete_animation_interactive_sequence_effect(file_name, slide_index, sequence_index, effect_index)

effect_count = len(slide_animation.interactive_sequences[sequence_index - 1].effects)
print("Effect count:", effect_count)  # 1
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

slidesApi.deleteAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, effectIndex).then(slideAnimation => {
    effectCount = slideAnimation.body.interactiveSequences[sequenceIndex - 1].effects.length;
    console.log("Effect count:", effectCount); // 1
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

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->deleteAnimationInteractiveSequenceEffect(fileName, slideIndex, sequenceIndex, effectIndex).get();

    int effectCount = slideAnimation->getInteractiveSequences()[sequenceIndex - 1]->getEffects().size();
    std::wcout << L"Effect count: " << effectCount; // 1
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $sequence_index = 1;
my $effect_index = 1;

my %parameters = (name => $file_name, slide_index => $slide_index, sequence_index => $sequence_index, effect_index => $effect_index);
my $slide_animation = $slides_api->delete_animation_interactive_sequence_effect(%parameters);

my $effect_count = @{$slide_animation->{interactive_sequences}[$sequence_index - 1]->{effects}};
print("Effect count: ", $effect_count); # 1
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
