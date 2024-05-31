---
title: "Delete Animations"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- animation
- remove animation
- shape animation
- text animation
type: docs
url: /delete-animations-from-a-special-slide/
weight: 30
---

## **Introduction**

Aspose.Slides Cloud API enables the manipulation of animations within PowerPoint presentations, offering functionality to read, add, and modify them. Use the following method to delete animations from special slides (Master, Layout, or Notes) in presentations.

## **DeleteSpecialSlideAnimation**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/animation|DELETE|Deletes animations from a special slide in a presentation saved in a storage.|[DeleteSpecialSlideAnimation](https://reference.aspose.cloud/slides/#/SpecialSlideAnimation/DeleteSpecialSlideAnimation)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the folder is located.|

### **Example**

Delete animations from the **Layout** of the **first** regular slide in the document **MyPresentation.pptx** saved in the **default** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Animations**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/LayoutSlide/animation" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "mainSequence": [],
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

        SlideAnimation slideAnimation = slidesApi.DeleteSpecialSlideAnimation(fileName, slideIndex, slideType);

        int mainSequenceEffectCount = slideAnimation.MainSequence.Count;
        int interactiveSequenceCount = slideAnimation.InteractiveSequences.Count;

        Console.WriteLine("Number of effects in the main sequence: " + mainSequenceEffectCount); // 0
        Console.WriteLine("Number of interactive sequences: " + interactiveSequenceCount); // 0
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

        SlideAnimation slideAnimation = slidesApi.deleteSpecialSlideAnimation(fileName, slideIndex, slideType, null, null, null);

        int mainSequenceEffectCount = slideAnimation.getMainSequence().size();
        int interactiveSequenceCount = slideAnimation.getInteractiveSequences().size();

        System.out.println("Number of effects in the main sequence: " + mainSequenceEffectCount); // 0
        System.out.println("Number of interactive sequences: " + interactiveSequenceCount); // 0
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideAnimation;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;

$slideAnimation = $slidesApi->deleteSpecialSlideAnimation($fileName, $slideIndex, $slideType);

$mainSequenceEffectCount = count($slideAnimation->getMainSequence());
$interactiveSequenceCount = count($slideAnimation->getInteractiveSequences());

echo "Number of effects in the main sequence: ", $mainSequenceEffectCount, "\n"; // 0
echo "Number of interactive sequences: ", $interactiveSequenceCount; // 0
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

slide_animation = slides_api.delete_special_slide_animation(file_name, slide_index, slide_type)

main_sequence_effect_count = slide_animation.main_sequence.length()
interactive_sequence_count = slide_animation.interactive_sequences.length()

print "Number of effects in the main sequence: ", main_sequence_effect_count, "\n" # 0
print "Number of interactive sequences: ", interactive_sequence_count # 0
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

slide_animation = slides_api.delete_special_slide_animation(file_name, slide_index, slide_type)

main_sequence_effect_count = len(slide_animation.main_sequence)
interactive_sequence_count = len(slide_animation.interactive_sequences)

print("Number of effects in the main sequence:", main_sequence_effect_count)  # 0
print("Number of interactive sequences:", interactive_sequence_count)  # 0
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
slideType = cloudSdk.SpecialSlideType.LayoutSlide;

slidesApi.deleteSpecialSlideAnimation(fileName, slideIndex, slideType).then(slideAnimation => {
    mainSequenceEffectCount = slideAnimation.body.mainSequence.length;
    interactiveSequenceCount = slideAnimation.body.interactiveSequences.length;

    console.log("Number of effects in the main sequence:", mainSequenceEffectCount); // 0
    console.log("Number of interactive sequences:", interactiveSequenceCount); // 0
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

    std::shared_ptr<SlideAnimation> slideAnimation = slidesApi->deleteSpecialSlideAnimation(fileName, slideIndex, slideType).get();

    int mainSequenceEffectCount = slideAnimation->getMainSequence().size();
    int interactiveSequenceCount = slideAnimation->getInteractiveSequences().size();

    std::wcout << L"Number of effects in the main sequence: " << mainSequenceEffectCount << "\r\n"; // 0
    std::wcout << L"Number of interactive sequences: " << interactiveSequenceCount; // 0
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
my $slide_type = "LayoutSlide";

my $slide_animation = $slides_api->delete_special_slide_animation(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type);

my $main_sequence_effect_count = @{$slide_animation->{main_sequence}};
my $interactive_sequence_count = @{$slide_animation->{interactive_sequences}};

print("Number of effects in the main sequence: ", $main_sequence_effect_count, "\n"); # 0
print("Number of interactive sequences: ", $interactive_sequence_count); # 0
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

	slideAnimation, _, _ := slidesApi.DeleteSpecialSlideAnimation(fileName, slideIndex, slideType, "", "", "")

	mainSequenceEffectCount := len(slideAnimation.GetMainSequence())
	interactiveSequenceCount := len(slideAnimation.GetInteractiveSequences())

	fmt.Println("Number of effects in the main sequence:", mainSequenceEffectCount) // 0
	fmt.Println("Number of interactive sequences:", interactiveSequenceCount) // 0
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
