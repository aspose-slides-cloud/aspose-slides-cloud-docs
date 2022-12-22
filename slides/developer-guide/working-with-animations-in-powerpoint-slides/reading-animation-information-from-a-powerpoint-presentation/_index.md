---
title: "Reading Animation Information from a PowerPoint Presentation"
type: docs
url: /reading-animation-information-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**

Text, images, shapes, tables, SmartArt graphics, and other objects can be animated in PowerPoint presentations. With Aspose.Slides Cloud, you can read their animation information. Effects can make an object appear, disappear, or move. The following method allows you to specify a slide, shape, or text paragraph to get their animation data. 

## **GetAnimation**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation|GET|Reads animation information from a PowerPoint object.|[GetAnimation](https://apireference.aspose.cloud/slides/#/Animation/GetAnimation)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|shapeIndex|integer|query|false|The 1-based index of a shape. If specified, only effects related to that shape are returned.|
|paragraphIndex|integer|query|false|The 1-based index of a text paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read animations from the **first** slide contained in **MyFolder/MyPresentation.pptx** document saved in the default storage.

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
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/animation?folder=MyFolder" \
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
using System;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all animations from the first slide.
        var slideAnimation = slidesApi.GetAnimation("MyPresentation.pptx", 1, null, null, null, "MyFolder");

        // Print effect types of the animations.
        foreach (var effect in slideAnimation.MainSequence)
        {
            Console.WriteLine(effect.Type);
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all animations from the first slide.
        SlideAnimation slideAnimation = slidesApi.getAnimation("MyPresentation.pptx", 1, null, null, null, "MyFolder", null);

        // Print effect types of the animations.
        for (Effect effect : slideAnimation.getMainSequence()) {
            System.out.println(effect.getType());
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

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Get all animations from the first slide.
$slideAnimation = $slidesApi->getAnimation("MyPresentation.pptx", 1, null, null, null, "MyFolder");

// Print effect types of the animations.
foreach ($slideAnimation->getMainSequence() as $effect) {
    echo $effect->getType(), PHP_EOL;
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

# Get all animations from the first slide.
slide_animation = slides_api.get_animation("MyPresentation.pptx", 1, nil, nil, nil, "MyFolder")

# Print effect types of the animations.
for effect in slide_animation.main_sequence
    puts effect.type
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get all animations from the first slide.
slide_animation = slides_api.get_animation("MyPresentation.pptx", 1, None, None, None, "MyFolder")

# Print effect types of the animations.
for effect in slide_animation.main_sequence:
    print(effect.type)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Get all animations from the first slide.
slidesApi.getAnimation("MyPresentation.pptx", 1, null, null, null, "MyFolder").then(slideAnimation => {
    // Print effect types of the animations.
    slideAnimation.body.mainSequence.forEach(effect => {
        console.log(effect.type);
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

    // Get all animations from the first slide.
    auto slideAnimation = slidesApi->getAnimation(L"MyPresentation.pptx", 1, boost::none, boost::none, L"", L"MyFolder").get();

    // Print effect types of the animations.
    for (auto effect : slideAnimation->getMainSequence()) {
        std::wcout << effect->getType() << std::endl;
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

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Get all animations from the first slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, folder => "MyFolder");
my $slide_animation = $slides_api->get_animation(%parameters);

# Print effect types of the animations.
for my $effect (@{$slide_animation->{main_sequence}}) {
    print($effect->{type} . "\n");
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

// Get all animations from the first slide.
animation, _, e := api.SlidesApi.GetAnimation("MyPresentation.pptx", 1, nil, nil, "", "MyFolder", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    // Print effect types of the animations.
    for _, effect := range animation.GetMainSequence() {
        fmt.Println(effect.GetType())
    }
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
