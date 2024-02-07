---
title: "Delete a Main Sequence"
type: docs
url: /delete-a-main-sequence/
weight: 33
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, and modify animations in PowerPoint presentations. You can also delete a main animation sequence from a presentation slide using the following method.

## **DeleteAnimationMainSequence**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation/mainSequence|DELETE|Deletes a main animation sequence from a presentation slide.|[DeleteAnimationMainSequence](https://reference.aspose.cloud/slides/#/Animation/DeleteAnimationMainSequence)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the folder is located.|

### **Example**

The document **MyPresentation.pptx** contains a main animation sequence with an animation effect and two interactive sequences on the **first** slide. Delete the **main** animation sequence.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Main Sequence**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation/mainSequence" \
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
          "type": "Fly",
          "subtype": "Bottom",
          "presetClassType": "Entrance",
          "shapeIndex": 4,
          "triggerType": "OnClick",
          "duration": 0.5,
          "triggerDelayTime": 0.0
        }
      ],
      "triggerShapeIndex": 3
    },
    {
      "effects": [
        {
          "type": "Split",
          "subtype": "HorizontalIn",
          "presetClassType": "Entrance",
          "shapeIndex": 5,
          "triggerType": "OnClick",
          "duration": 0.5,
          "triggerDelayTime": 0.0
        }
      ],
      "triggerShapeIndex": 3
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

        SlideAnimation slideAnimation = slidesApi.DeleteAnimationMainSequence(fileName, slideIndex);

        int mainSequenceEffectCount = slideAnimation.MainSequence.Count;
        int interactiveSequenceCount = slideAnimation.InteractiveSequences.Count;

        Console.WriteLine("Number of effects in the main sequence: " + mainSequenceEffectCount); // 0
        Console.WriteLine("Number of interactive sequences: " + interactiveSequenceCount); // 2
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

        SlideAnimation slideAnimation = slidesApi.deleteAnimationMainSequence(fileName, slideIndex, null, null, null);

        int mainSequenceEffectCount = slideAnimation.getMainSequence().size();
        int interactiveSequenceCount = slideAnimation.getInteractiveSequences().size();

        System.out.println("Number of effects in the main sequence: " + mainSequenceEffectCount); // 0
        System.out.println("Number of interactive sequences: " + interactiveSequenceCount); // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;

$slideAnimation = $slidesApi->deleteAnimationMainSequence($fileName, $slideIndex);

$mainSequenceEffectCount = count($slideAnimation->getMainSequence());
$interactiveSequenceCount = count($slideAnimation->getInteractiveSequences());

echo "Number of effects in the main sequence: ", $mainSequenceEffectCount, "\n"; // 0
echo "Number of interactive sequences: ", $interactiveSequenceCount; // 2
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

slide_animation = slides_api.delete_animation_main_sequence(file_name, slide_index)

main_sequence_effect_count = slide_animation.main_sequence.length()
interactive_sequence_count = slide_animation.interactive_sequences.length()

print "Number of effects in the main sequence: ", main_sequence_effect_count, "\n" # 0
print "Number of interactive sequences: ", interactive_sequence_count # 2
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1

slide_animation = slides_api.delete_animation_main_sequence(file_name, slide_index)

main_sequence_effect_count = len(slide_animation.main_sequence)
interactive_sequence_count = len(slide_animation.interactive_sequences)

print("Number of effects in the main sequence:", main_sequence_effect_count)  # 0
print("Number of interactive sequences:", interactive_sequence_count)  # 2
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;

slidesApi.deleteAnimationMainSequence(fileName, slideIndex).then(slideAnimation => {
    mainSequenceEffectCount = slideAnimation.body.mainSequence.length;
    interactiveSequenceCount = slideAnimation.body.interactiveSequences.length;

    console.log("Number of effects in the main sequence:", mainSequenceEffectCount); // 0
    console.log("Number of interactive sequences:", interactiveSequenceCount); // 2
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

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->deleteAnimationMainSequence(fileName, slideIndex).get();

    int mainSequenceEffectCount = slideAnimation->getMainSequence().size();
    int interactiveSequenceCount = slideAnimation->getInteractiveSequences().size();

    std::wcout << L"Number of effects in the main sequence: " << mainSequenceEffectCount << "\r\n"; // 0
    std::wcout << L"Number of interactive sequences: " << interactiveSequenceCount; // 2
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

my %parameters = (name => $file_name, slide_index => $slide_index);
my $slide_animation = $slides_api->delete_animation_main_sequence(%parameters);

my $main_sequence_effect_count = @{$slide_animation->{main_sequence}};
my $interactive_sequence_count = @{$slide_animation->{interactive_sequences}};

print("Number of effects in the main sequence: ", $main_sequence_effect_count, "\n"); # 0
print("Number of interactive sequences: ", $interactive_sequence_count); # 2
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
