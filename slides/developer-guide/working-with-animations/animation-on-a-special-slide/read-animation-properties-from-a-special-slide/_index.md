---
title: "Read Animation Properties"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- animation
- shape animation
- text animation
type: docs
url: /read-animation-properties-from-a-special-slide/
weight: 10
---

## **Introduction**

Animations can be applied to various elements such as text, images, shapes, tables, SmartArt graphics, and more within PowerPoint presentations. Aspose.Slides Cloud enables the retrieval of animation details for these objects. Use the following method to extract animations from special slides (Master, Layout, or Notes) in presentations.

## **GetSpecialSlideAnimation**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/animation|GET|Reads animations from a special slide in a presentation saved in a storage.|[GetSpecialSlideAnimation](https://reference.aspose.cloud/slides/#/SpecialSlideAnimation/GetSpecialSlideAnimation)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|shapeIndex|integer|query|false|The 1-based index of a shape. If specified, only effects related to that shape are returned.|
|paragraphIndex|integer|query|false|The 1-based index of a text paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

Read animations from the **Layout** of the **first** regular slide contained in **MyPresentation.pptx** document saved in the **default** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Slide Animations**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/LayoutSlide/animation" \
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
            "shapeIndex": 1,
            "triggerType": "OnClick",
            "duration": 0.5,
            "triggerDelayTime": 0.0
        },
        {
            "type": "Split",
            "subtype": "VerticalIn",
            "presetClassType": "Entrance",
            "shapeIndex": 2,
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

        SlideAnimation slideAnimation = slidesApi.GetSpecialSlideAnimation(fileName, slideIndex, slideType);

        int mainEffectCount = slideAnimation.MainSequence.Count;
        Console.WriteLine("Number of main effects: " + mainEffectCount);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SlideAnimation;
import com.aspose.slides.model.SpecialSlideType;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;

        SlideAnimation slideAnimation = slidesApi.getSpecialSlideAnimation(fileName, slideIndex, slideType, null, null, null, null, null);

        int mainEffectCount = slideAnimation.getMainSequence().size();
        System.out.println("Number of main effects: " + mainEffectCount);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;

$slideAnimation = $slidesApi->getSpecialSlideAnimation($fileName, $slideIndex, $slideType);

$mainEffectCount = count($slideAnimation->getMainSequence());
echo "Number of main effects: ", $mainEffectCount;
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

slide_animation = slides_api.get_special_slide_animation(file_name, slide_index, slide_type)

main_effect_count = slide_animation.main_sequence.length()
print "Number of main effects: ", main_effect_count
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

slide_animation = slides_api.get_special_slide_animation(file_name, slide_index, slide_type)

main_effect_count = len(slide_animation.main_sequence)
print("Number of main effects:", main_effect_count)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
slideType = cloudSdk.SpecialSlideType.LayoutSlide;

slidesApi.getSpecialSlideAnimation(fileName, slideIndex, slideType).then(slideAnimation => {
    mainEffectCount = slideAnimation.body.mainSequence.length;
    console.log("Number of main effects:", mainEffectCount);
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

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->getSpecialSlideAnimation(fileName, slideIndex, slideType).get();

    int mainEffectCount = slideAnimation->getMainSequence().size();
    std::wcout << L"Number of main effects: " << mainEffectCount;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $slide_type = "LayoutSlide";

my $slide_animation = $slides_api->get_special_slide_animation(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type);

my $main_effect_count = @{$slide_animation->{main_sequence}};
print("Number of main effects: ", $main_effect_count);
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

	slideAnimation, _, _ := slidesApi.GetSpecialSlideAnimation(fileName, slideIndex, slideType, nil, nil, "", "", "")

	mainEffectCount := len(slideAnimation.GetMainSequence())
	fmt.Println("Number of main effects:", mainEffectCount)
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
