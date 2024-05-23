---
title: "Delete Effects from a Main Sequence"
type: docs
url: /delete-effects-from-a-main-sequence-on-a-special-slide/
weight: 90
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, and modify animations in PowerPoint presentations. You can also delete effects from main animation sequences on special slides (Master, Layout, or Notes) in presentations using the following method.

## **DeleteSpecialSlideAnimationEffect**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/animation/mainSequence/{effectIndex}|DELETE|Deletes an effect from a main animation sequence on a special slide in a presentation saved in a storage.|[DeleteSpecialSlideAnimationEffect](https://reference.aspose.cloud/slides/#/SpecialSlideAnimation/DeleteSpecialSlideAnimationEffect)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|effectIndex|integer|path|true|The 1-based index of an effect to be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Example**

The document **MyPresentation.pptx** saved in the **default** storage contains two effects in the **main** animation sequence on the **Layout** of the **first** slide. Delete the **second** effect.

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
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/LayoutSlide/animation/mainSequence/2" \
     -H "authorization: Bearer MyAccessToken"
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

        SlideAnimation slideAnimation = slidesApi.DeleteSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex);

        int effectCount = slideAnimation.MainSequence.Count;
        Console.WriteLine("Number of effects in the main sequence: " + effectCount); // 1
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;
        int effectIndex = 1;

        SlideAnimation slideAnimation = slidesApi.deleteSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex, null, null, null);

        int effectCount = slideAnimation.getMainSequence().size();
        System.out.println("Number of effects in the main sequence: " + effectCount); // 1
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;
$effectIndex = 1;

$slideAnimation = $slidesApi->deleteSpecialSlideAnimationEffect($fileName, $slideIndex, $slideType, $effectIndex);

$effectCount = count($slideAnimation->getMainSequence());
echo "Number of effects in the main sequence: ", $effectCount; // 1
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

slide_animation = slides_api.delete_special_slide_animation_effect(file_name, slide_index, slide_type, effect_index)

effect_count = slide_animation.main_sequence.length()
puts "Number of effects in the main sequence: #{effect_count}" # 1
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import SpecialSlideType

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = SpecialSlideType.LAYOUTSLIDE
effect_index = 1

slide_animation = slides_api.delete_special_slide_animation_effect(file_name, slide_index, slide_type, effect_index)

effect_count = len(slide_animation.main_sequence)
print("Number of effects in the main sequence:", effect_count)  # 1
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

slidesApi.deleteSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex).then(slideAnimation => {
    effectCount = slideAnimation.body.mainSequence.length;
    console.log("Number of effects in the main sequence:", effectCount); // 1
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

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->deleteSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex).get();

    int effectCount = slideAnimation->getMainSequence().size();
    std::wcout << L"Number of effects in the main sequence: " << effectCount; // 1
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

my $slide_animation = $slides_api->delete_special_slide_animation_effect(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, effect_index => $effect_index);

my $effect_count = @{$slide_animation->{main_sequence}};
print("Number of effects in the main sequence: ", $effect_count); # 1
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

	slideAnimation, _, _ := slidesApi.DeleteSpecialSlideAnimationEffect(fileName, slideIndex, slideType, effectIndex, "", "", "")

	effectCount := len(slideAnimation.GetMainSequence())
	fmt.Println("Number of effects in the main sequence:", effectCount) // 1
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
