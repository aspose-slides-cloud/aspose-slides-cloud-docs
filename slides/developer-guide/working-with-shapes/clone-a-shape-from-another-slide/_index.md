---
title: "Clone a Shape from Another Slide"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- shape
- clone a shape
- copy a shape
- clone from slide
- cross-slide clone
type: docs
url: /clone-a-shape-from-another-slide/
weight: 230
---

## **Introduction**

Aspose.Slides Cloud API allows you to clone (copy) a shape from one slide to another within the same presentation. The `CreateShape` method — described in detail in [Add a Shape to a Slide](/slides/add-a-shape-to-a-slide/) — accepts a `cloneFromSlide` query parameter that, when combined with `shapeToClone`, identifies the source slide. The shape at position `shapeToClone` on slide `cloneFromSlide` is copied to the target slide. Without `cloneFromSlide`, `shapeToClone` clones from the same slide.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes|POST|Adds a shape to a presentation slide, optionally cloning it from a different slide.|[CreateShape](https://apireference.aspose.cloud/slides/#/Shapes/CreateShape)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the target slide.|
|shapeToClone|integer|query|false|The 1-based index of the shape to be cloned.|
|cloneFromSlide|integer|query|false|The 1-based index of the slide that contains the shape to clone. When omitted, the shape is cloned from the slide specified by `slideIndex`.|
|position|integer|query|false|The 1-based index of the position for the new shape. By default, the shape is added to the end.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage containing the `folder`.|

## **Example**

Clone the **second** shape from slide **3** and add it to slide **1** in **MyFolder/MyPresentation.pptx** stored in the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Clone the Shape**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?shapeToClone=2&cloneFromSlide=3&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "type": "Shape",
    "name": "Rectangle 2",
    "width": 200.0,
    "height": 100.0,
    "alternativeText": "",
    "alternativeTextTitle": "",
    "hidden": false,
    "x": 100.0,
    "y": 150.0,
    "zOrderPosition": 1,
    "fillFormat": {
        "type": "Solid",
        "color": "#FF4472C4"
    },
    "lineFormat": {
        "alignment": "Center",
        "capStyle": "Flat",
        "dashStyle": "Solid",
        "joinStyle": "Round",
        "style": "Single",
        "beginArrowHead": {
            "length": "Medium",
            "style": "None",
            "width": "Medium"
        },
        "endArrowHead": {
            "length": "Medium",
            "style": "None",
            "width": "Medium"
        },
        "fillFormat": {
            "type": "NoFill"
        },
        "miterLimit": 10.0,
        "width": 0.75
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1,
        "shapeIndex": 2
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="8" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-.NET

using Aspose.Slides.Cloud.Sdk;
using System;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Clone shape 2 from slide 3 to slide 1.
        var shape = slidesApi.CreateShape("MyPresentation.pptx", 1, null, shapeToClone: 2, cloneFromSlide: 3, folder: "MyFolder");

        // Print a resource reference to the new shape.
        Console.WriteLine(shape.SelfUri.Href);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ShapeBase;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Clone shape 2 from slide 3 to slide 1.
        ShapeBase shape = slidesApi.createShape("MyPresentation.pptx", 1, null, 2, 3, null, null, "MyFolder", null, null);

        // Print a resource reference to the new shape.
        System.out.println(shape.getSelfUri().getHref());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-PHP

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $config);

// Clone shape 2 from slide 3 to slide 1.
$shape = $slidesApi->createShape("MyPresentation.pptx", 1, null, 2, 3, null, null, "MyFolder");

// Print a resource reference to the new shape.
echo $shape->getSelfUri()->getHref();
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Clone shape 2 from slide 3 to slide 1.
shape = slides_api.create_shape("MyPresentation.pptx", 1, nil, 2, 3, nil, nil, "MyFolder")

# Print a resource reference to the new shape.
print shape.self_uri.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Clone shape 2 from slide 3 to slide 1.
shape = slides_api.create_shape("MyPresentation.pptx", 1, None, 2, 3, None, None, "MyFolder")

# Print a resource reference to the new shape.
print(shape.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Node.js

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Clone shape 2 from slide 3 to slide 1.
slidesApi.createShape("MyPresentation.pptx", 1, null, 2, 3, null, null, "MyFolder").then(shape => {
    // Print a resource reference to the new shape.
    console.log(shape.body.selfUri.href);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Clone shape 2 from slide 3 to slide 1.
    auto shape = slidesApi->createShape(L"MyPresentation.pptx", 1, nullptr, 2, 3, boost::none, L"", L"MyFolder").get();

    // Print a resource reference to the new shape.
    std::wcout << shape->getSelfUri()->getHref();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Clone shape 2 from slide 3 to slide 1.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, shape_to_clone => 2, clone_from_slide => 3, folder => "MyFolder");
my $shape = $slides_api->create_shape(%parameters);

# Print a resource reference to the new shape.
print $shape->{self_uri}->{href};
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
