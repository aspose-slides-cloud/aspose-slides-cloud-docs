---
title: "Add a Shape to a Group Shape"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- shape
- group shape
- change a group shape
type: docs
url: /add-a-shape-to-a-group-shape/
weight: 20
---

## **Introduction**

This article shows you how to create a shape and immediately add it to a shape group in a PowerPoint presentation using Aspose.Slides for Cloud API in your applications. **CreateShape** method has an optional **subShape** parameter that allows to specify path to the shape that will be the parent for the new shape. The sub-shape path is a string that contains shape index (e.g., "1") or a path in case of more than one level of grouping (e.g. "1/shapes/1").
You should pass a data transfer object for the new shape to the method parameters or specify an index of the shape that you want to clone.

### **Examples**

The **first** slide in **MyFolder/MyPresentation.pptx** document contains **three** shapes. The last shape is a shape group containing five shapes. Add a square with default style at coordinates (20, 20) and size 100x100 to the shape group.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the Shape to the Group**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?folder=MyFolder&subshape=4" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @RequestData.json
```

RequestData.json content:

```json
{
    "ShapeType": "Rectangle",
    "X": 20,
    "Y": 20,
    "Width": 100,
    "Height": 100
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "type": "Shape",
    "text": "",
    "paragraphs": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/3/shapes/6/paragraphs?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1,
        "shapeIndex": 6
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
    "name": "New shape",
    "width": 100.0,
    "height": 100.0,
    "alternativeText": "",
    "alternativeTextTitle": "",
    "hidden": false,
    "x": 19.99997,
    "y": 20.0,
    "zOrderPosition": 5,
    "fillFormat": {
        "type": "Solid",
        "color": "#FF4472C4"
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
        "joinStyle": "Miter",
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
            "type": "Solid",
            "color": "#FF2F528F"
        },
        "miterLimit": 8.0,
        "width": 1.0
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/3/shapes/6?folder=MyFolder",
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

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare data for the new shape.
        var square = new Shape
        {
            ShapeType = GeometryShape.ShapeTypeEnum.Rectangle,
            X = 20,
            Y = 20,
            Width = 100,
            Height = 100
        };

        // Create the shape and add it to the shape group that has an index of 4.
        var shape = slidesApi.CreateShape("MyPresentation.pptx", 1, square, folder: "MyFolder", subShape: "4");

        // Print the resource reference to the shape.
        Console.WriteLine(shape.SelfUri.Href);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare data for the new shape.
        Shape square = new Shape();
        square.setShapeType(GeometryShape.ShapeTypeEnum.RECTANGLE);
        square.setX(20.0);
        square.setY(20.0);
        square.setWidth(100.0);
        square.setHeight(100.0);

        // Create the shape and add it to the shape group that has an index of 4.
        ShapeBase shape = slidesApi.createShape("MyPresentation.pptx", 1, square, null, null, null, "MyFolder", null, "4");

        // Print the resource reference to the shape.
        System.out.println(shape.getSelfUri().getHref());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Shape;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare data for the new shape.
$square = new Shape();
$square->setShapeType("Rectangle");
$square->setX(20);
$square->setY(20);
$square->setWidth(100);
$square->setHeight(100);

// Create the shape and add it to the shape group that has an index of 4.
$shape = $slidesApi->createShape("MyPresentation.pptx", 1, $square, null, null, null, "MyFolder", null, "4");

// Print the resource reference to the shape.
print($shape->getSelfUri()->getHref());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Prepare data for the new shape.
square = AsposeSlidesCloud::Shape.new
square.shape_type = "Rectangle"
square.x = 20
square.y = 20
square.width = 100
square.height = 100

# Create the shape and add it to the shape group that has an index of 4.
shape = slides_api.create_shape("MyPresentation.pptx", 1, square, nil, nil, nil, "MyFolder", nil, "4")

# Print the resource reference to the shape.
print shape.self_uri.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.shape import Shape

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare data for the new shape.
square = Shape()
square.shape_type = "Rectangle"
square.x = 20
square.y = 20
square.width = 100
square.height = 100

# Create the shape and add it to the shape group that has an index of 4.
shape = slides_api.create_shape("MyPresentation.pptx", 1, square, None, None, None, "MyFolder", None, "4")

# Print the resource reference to the shape.
print(shape.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Prepare data for the new shape.
const square = new cloud.Shape();
square.shapeType = "Rectangle";
square.x = 20;
square.y = 20;
square.width = 100;
square.height = 100;

// Create the shape and add it to the shape group that has an index of 4.
slidesApi.createShape("MyPresentation.pptx", 1, square, null, null, null, "MyFolder", null, "4").then(shape => {
    // Print the resource reference to the shape.
    console.log(shape.body.selfUri.href);
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
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Prepare data for the new shape.
    auto square = std::make_shared<Shape>();
    square->setShapeType(L"Rectangle");
    square->setX(20);
    square->setY(20);
    square->setWidth(100);
    square->setHeight(100);

    // Create the shape and add it to the shape group that has an index of 4.
    auto shape = slidesApi->createShape(L"MyPresentation.pptx", 1, square, boost::none, boost::none, L"", L"MyFolder", L"", L"4").get();

    // Print the resource reference to the shape.
    std::wcout << shape->getSelfUri()->getHref();

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
use AsposeSlidesCloud::Object::Shape;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare data for the new shape.
my $square = AsposeSlidesCloud::Object::Shape->new();
$square->{shape_type} = "Rectangle";
$square->{x} = 20;
$square->{y} = 20;
$square->{width} = 100;
$square->{height} = 100;

# Create the shape and add it to the shape group that has an index of 4.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, dto => $square, folder => "MyFolder", sub_shape=>"4");
my $shape = $slides_api->create_shape(%parameters);

# Print the resource reference to the shape.
print($shape->{self_uri}->{href});
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
