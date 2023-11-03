---
title: "Get a Shape from a Slide"
type: docs
url: /get-a-shape-from-a-slide/
weight: 20
---

## **Introduction**

This article shows you how to get a particular shape from a PowerPoint document using Aspose.Slides Cloud API in your applications. You can use the method below to get all information about the shape placed on a slide in the presentation saved in storage.

## **GetShape**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}|GET|Reads information about a shape.|[GetShape](https://apireference.aspose.cloud/slides/#/Shapes/GetShape)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide where the shape is placed.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
|subShape|string|query|false|Sub-shape path (e.g. "3", "3/shapes/2)

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read information about the **second** shape on the **third** slide from **MyFolder/MyPresentation.pptx** document saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get the Shape**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/shapes/2?folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "type": "Shape",
    "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
    "paragraphs": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/shapes/2/paragraphs?folder=MyFolder",
        "relation": "self",
        "slideIndex": 3,
        "shapeIndex": 2
    },
    "textFrameFormat": {
        "threeDFormat": {
            "contourWidth": 0.0,
            "depth": 0.0,
            "extrusionHeight": 0.0
        },
        "transform": "NotDefined"
    },
    "shapeType": "Rectangle",
    "name": "TextBox 2",
    "width": 482.20346,
    "height": 29.08126,
    "alternativeText": "",
    "hidden": false,
    "x": 217.60826,
    "y": 155.25772,
    "zOrderPosition": 1,
    "fillFormat": {
        "type": "NoFill"
    },
    "threeDFormat": {
        "contourWidth": 0.0,
        "depth": 0.0,
        "extrusionHeight": 0.0
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
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/shapes/2?folder=MyFolder",
        "relation": "self",
        "slideIndex": 3
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
using System.Diagnostics;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get the second shape from the third slide.
        var shape = slidesApi.GetShape("MyPresentation.pptx", 3, 2, null, "MyFolder");

        // Print the resource URI, position and size of the shape.
        Debug.WriteLine($"Resource reference: {shape.SelfUri.Href}");
        Debug.WriteLine($"X: {shape.X}");
        Debug.WriteLine($"Y: {shape.Y}");
        Debug.WriteLine($"Width: {shape.Width}");
        Debug.WriteLine($"Height: {shape.Height}");
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

        // Get the second shape from the third slide.
        ShapeBase shape = slidesApi.getShape("MyPresentation.pptx", 3, 2, null, "MyFolder", null, null);

        // Print the resource URI, position and size of the shape.
        System.out.printf("Resource reference: %s\n", shape.getSelfUri().getHref());
        System.out.printf("X: %s\n", shape.getX());
        System.out.printf("Y: %s\n", shape.getY());
        System.out.printf("Width: %s\n", shape.getWidth());
        System.out.printf("Height: %s\n", shape.getHeight());
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

// Get the second shape from the third slide.
$shape = $slidesApi->getShape("MyPresentation.pptx", 3, 2, null, "MyFolder");

// Print the resource URI, position and size of the shape.
echo "Resource reference: " . $shape->getSelfUri()->getHref() . "\n";
echo "X: " . $shape->getX() . "\n";
echo "Y: " . $shape->getY() . "\n";
echo "Width: " . $shape->getWidth() . "\n";
echo "Height: " . $shape->getHeight() . "\n";
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

# Get the second shape from the third slide.
shape = slides_api.get_shape("MyPresentation.pptx", 3, 2, nil, "MyFolder")

# Print the resource URI, position and size of the shape.
puts "Resource reference: #{shape.self_uri.href}"
puts "X: #{shape.x}"
puts "Y: #{shape.y}"
puts "Width: #{shape.width}"
puts "Height: #{shape.height}"
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get the second shape from the third slide.
shape = slides_api.get_shape("MyPresentation.pptx", 3, 2, None, "MyFolder")

# Print the resource URI, position and size of the shape.
print(f"Resource reference: {shape.self_uri.href}")
print(f"X: {shape.x}")
print(f"Y: {shape.y}")
print(f"Width: {shape.width}")
print(f"Height: {shape.height}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Get the second shape from the third slide.
slidesApi.getShape("MyPresentation.pptx", 3, 2, null, "MyFolder").then((shape) => {
    // Print the resource URI, position and size of the shape.
    console.log("Resource reference: %s", shape.body.selfUri.href)
    console.log("X: %s", shape.body.x)
    console.log("Y: %s", shape.body.y)
    console.log("Width: %s", shape.body.width)
    console.log("Height: %s", shape.body.height)
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Get the second shape from the third slide.
    auto shape = slidesApi->getShape(L"MyPresentation.pptx", 3, 2, L"", L"MyFolder").get();

    // Print the resource URI, position and size of the shape.
    std::wcout << "Resource reference: " << shape->getSelfUri()->getHref() << std::endl;
    std::wcout << "X: " << shape->getX() << std::endl;
    std::wcout << "Y: " << shape->getY() << std::endl;
    std::wcout << "Width: " << shape->getWidth() << std::endl;
    std::wcout << "Height: " << shape->getHeight() << std::endl;

    std::cin.get();

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

# Get the second shape from the third slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 3, shape_index => 2, folder => "MyFolder");
my $shape = $slides_api->get_shape(%parameters);

# Print the resource URI, position and size of the shape.
print("Resource reference: $shape->{self_uri}->{href}\n");
print("X: $shape->{x}\n");
print("Y: $shape->{y}\n");
print("Width: $shape->{width}\n");
print("Height: $shape->{height}\n");
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
