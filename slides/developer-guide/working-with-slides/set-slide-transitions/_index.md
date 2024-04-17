---
title: "Set Slide Transitions"
type: docs
url: /set-slide-transitions/
weight: 130
---

## **Introduction**

You can get and set slide transition effects using **Slide.SlideShowTransition** property.

To set a transition effect for a slide, call [UpdateSlide](https://reference.aspose.cloud/slides/#/Slides/UpdateSlide) method. In the slide DTO object, set **SlideShowTransition** property, specify its type and, if you need, some other properties. Note that some transition properties apply to a limited set of transition types.

To remove transition effects from a slide, you need call **UpdateSlide** method with transition type set to **None**. If you set **SlideShowTransition** to null, the **UpdateSlide** method will just leave transition effects unchanged, whether they exist or not.

## **Example**

Set circle transition effect for the fitst slide of **MyPresentation.pptx** document.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Update the slide**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1" \
     -H "authorization: Bearer MyAccessToken" \
     -H "accept: application/json" \
     -H "Content-Type: application/json" \
     -d @slide.json
```

slide.json content:

```json
{
    "slideShowTransition": {
        "type": "Circle",
        "speed": "Medium"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Update the slide**

```json
{
    "width": 960.0,
    "height": 540.0,
    "showMasterShapes": true,
    "slideShowTransition": {
        "type": "Circle",
        "advanceAfter": false,
        "advanceAfterTime": 0,
        "advanceOnClick": true,
        "soundIsBuiltIn": false,
        "soundLoop": false,
        "speed": "Medium"
    },
    "layoutSlide":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/layoutSlides/1?folder=TempSlidesSDK","relation":"self"},
    "shapes":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/slides/1/shapes?folder=TempSlidesSDK","relation":"self","slideIndex":1},
    "theme":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/slides/1/theme?folder=TempSlidesSDK","relation":"self","slideIndex":1},
    "placeholders":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/slides/1/placeholders?folder=TempSlidesSDK","relation":"self","slideIndex":1},
    "images":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/slides/1/images?folder=TempSlidesSDK","relation":"self","slideIndex":1},
    "comments":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/slides/1/comments?folder=TempSlidesSDK","relation":"self","slideIndex":1},
    "background":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/slides/1/background?folder=TempSlidesSDK","relation":"self","slideIndex":1},
    "notesSlide":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/slides/1/notesSlide?folder=TempSlidesSDK","relation":"self","slideIndex":1},
    "selfUri":{"href":"https://api-qa.aspose.cloud/v3.0/slides/test.pptx/slides/1?folder=TempSlidesSDK","relation":"self"},
    "alternateLinks":[ ... ]
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");
Slide dto = new Slide
{
    SlideShowTransition = new SlideShowTransition
    {
        Type = SlideShowTransition.TypeEnum.Circle,
        Speed = SlideShowTransition.SpeedEnum.Medium
    }
};
Slide slide = slidesApi.UpdateSlide("MyPresentation.pptx", 1, dto);
Console.WriteLine("Transition type: " + slide.SlideShowTransition.Type); // Circle
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");
Slide dto = new Slide();
SlideShowTransition transition = new SlideShowTransition();
transition.setType(SlideShowTransition.TypeEnum.CIRCLE);
transition.setSpeed(SlideShowTransition.SpeedEnum.MEDIUM);
dto.setSlideShowTransition(transition);
Slide slide = slidesApi.updateSlide("MyPresentation.pptx", 1, dto, null, null, null);
System.out.println("Transition type: " + slide.getSlideShowTransition().getType()); // Circle
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Slide;
use Aspose\Slides\Cloud\Sdk\Model\SlideShowTransition;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$dto = new Slide();
$transition = new SlideShowTransition();
$transition->setType('Circle');
$transition->setSpeed('Medium');
$dto->setSlideShowTransition($transition);

$slide = $slidesApi->updateSlide("MyPresentation.pptx", 1, $dto);
echo "Transition type: ", $slide->getSlideShowTransition()->getType(); // Circle
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

dto = Slide.new
transition = SlideShowTransition.new
transition.type = 'Circle'
transition.speed = 'Medium'
dto.slide_show_transition = transition

slide = slides_api.update_slide("MyPresentation.pptx", 1, dto)

print "Transition type: ", slide.slide_show_transition.type, "\n" # Circle
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models import Slide
from asposeslidescloud.models import SlideShowTransition

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

dto = Slide()
transition = SlideShowTransition()
transition.type = 'Circle'
transition.speed = 'Medium'
dto.slide_show_transition = transition

slide = slides_api.update_slide("MyPresentation.pptx", 1, dto)
print("Transition type: ", slide.slide_show_transition.type) # Circle
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";

const dto = new cloud.Slide();
const transition = new cloud.SlideShowTransition();
transition.type = "Circle";
transition.speed = "Medium";
dto.slideShowTransition = transition;

slidesApi.updateSlide("MyPresentation.pptx", 1, dto).then(result => {
    console.log("Transition type: ", result.body.slideShowTransition.type); // Circle
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");
    auto dto = std::make_shared<Slide>();
    auto transition = std::make_shared<SlideShowTransition>();
    transition->setType(L"Circle");
    transition->setSpeed(L"Medium");
    dto->setSlideShowTransition(transition);
    auto slide = slidesApi->updateSlide(L"MyPresentation.pptx", 1, dto).get();
    std::wcout << L"Transition type: " << slide->getSlideShowTransition()->getType() << L"\r\n"; // Circle
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Slide;
use AsposeSlidesCloud::Object::SlideShowTransition;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# The settings for all slides.
my $dto = AsposeSlidesCloud::Object::Slide->new();
my $transition = AsposeSlidesCloud::Object::SlideShowTransition->new();
$transition->{type} = "Circle";
$transition->{speed} = "Medium";
$dto->{slide_show_transition} = $transition;

my %params = (name => "MyPresentation.pptx", slide_index => 1, dto => $dto);
my $slide = $slides_api->update_slide(%params);

print("Transition type: " . $slide->{slide_show_transition}->{type} . "\n"); # Circle
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
