---
title: "Update a Shape"
type: docs
url: /update-a-shape-in-a-group-shape/
weight: 30
---

## **Introduction**

This article shows you how to update shape properties inside a group shape using Aspose.Slides Cloud API in your applications. **UpdateShape** method has an optional **subShape** parameter that allows to specify path to the sub-shape to be updated. The sub-shape path is a string that contains shape index (e.g., "1") or a path in case of more than one level of grouping (e.g. "1/shapes/1"). The shape properties that need to be updated depend on the shape type.

### **Examples**

**MyFolder/MyPresentation.pptx** document is containing three shapes on the **first** slide. The **third** shape is a group shape. Hide the **second** shape inside the group shape.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Hide the Shape**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/4?subShape=2&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @ShapeProperties.json
```

ShapeProperties.json content:

```json
{
    "Hidden": "true"
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
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/4/shapes/2/paragraphs?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1,
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
    "name": "Rectangle 2",
    "width": 72.0,
    "height": 72.0,
    "alternativeText": "",
    "hidden": true,
    "x": 276.2474,
    "y": 205.36087,
    "zOrderPosition": 1,
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
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/3/shapes/2?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1
    }
}
```

{{< /tab >}}

{{< /tabs >}}

{{% alert color="primary" %}} 

The code examples below also use the `GetShape` method described in [Extracting Shapes from a Group Shape](/slides/extract-shapes-from-a-group-shape/).

{{% /alert %}}

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

        var fileName = "MyPresentation.pptx";
        var slideIndex = 1;
        var subShape = "2";
        var shapeIndex = 4;
        var folderPath = "MyFolder";

        // Get the shape from the group shape.
        var shape = slidesApi.GetShape(fileName, slideIndex, shapeIndex, null, folderPath, null, subShape);

        // Change the shape properties.
        shape.Hidden = true;

        // Update the shape properties.
        var updatedShape = slidesApi.UpdateShape(fileName, slideIndex, shapeIndex, shape, null, folderPath, null, subShape);

        // Check if the shape is hidden.
        Console.WriteLine("The shape is hidden: " + updatedShape.Hidden);
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

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        String subShape = "2";
        int shapeIndex = 4;
        String folderPath = "MyFolder";

        // Get the shape from the group shape.
        ShapeBase shape = slidesApi.getShape(fileName, slideIndex, shapeIndex, null, folderPath, null, subShape);

        // Change the shape properties.
        shape.setHidden(true);

        // Update the shape properties.
        ShapeBase updatedShape = slidesApi.updateShape(fileName, slideIndex, shapeIndex, shape, null, folderPath, null, subShape);

        // Check if the shape is hidden.
        System.out.println("The shape is hidden: " + updatedShape.isHidden());
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

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$subShape = "2";
$shapeIndex = 4;
$folderPath = "MyFolder";

// Get the shape from the group shape.
$shape = $slidesApi->getShape($fileName, $slideIndex, $shapeIndex, null, $folderPath, null, $subShape);

// Change the shape properties.
$shape->setHidden(true);

// Update the shape properties.
$updatedShape = $slidesApi->updateShape($fileName, $slideIndex, $shapeIndex, $shape, null, $folderPath, null, $subShape);

// Check if the shape is hidden.
echo "The shape is hidden: ", $updatedShape->getHidden();
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

file_name = "MyPresentation.pptx"
slide_index = 1
sub_shape = "2"
shape_index = 4
folder_path = "MyFolder"

# Get the shape from the group shape.
shape = slides_api.get_shape(file_name, slide_index, shape_index, nil, folder_path, nil, sub_shape)

# Change the shape properties.
shape.hidden = true

# Update the shape properties.
updated_shape = slides_api.update_shape(file_name, slide_index, shape_index, shape, nil, folder_path, nil, sub_shape)

# Check if the shape is hidden.
print "The shape is hidden: #{updated_shape.hidden}"
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
sub_shape = "2"
shape_index = 4
folder_path = "MyFolder"

# Get the shape from the group shape.
shape = slides_api.get_shape(file_name, slide_index, shape_index, None, folder_path, None, sub_shape)

# Change the shape properties.
shape.hidden = True

# Update the shape properties.
updated_shape = slides_api.update_shape(file_name, slide_index, shape_index, shape, None, folder_path, None, sub_shape)

# Check if the shape is hidden.
print(f"The shape is hidden: {updated_shape.hidden}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

const fileName = "MyPresentation.pptx"
const slideIndex = 1
const subShape = "2"
const shapeIndex = 4
const folderPath = "MyFolder"

// Get the shape from the group shape.
slidesApi.getShape(fileName, slideIndex, shapeIndex, null, folderPath, null, subShape).then((shape) => {
    // Change the shape properties.
    shape.body.hidden = true

    // Update the shape properties.
    slidesApi.updateShape(fileName, slideIndex, shapeIndex, shape.body, null, folderPath, null, subShape).then((updatedShape) => {
        // Check if the shape is hidden.
        console.log("The shape is hidden: " + updatedShape.body.hidden)
    })
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

    auto fileName = L"MyPresentation.pptx";
    auto slideIndex = 1;
    auto subShape = L"2";
    auto shapeIndex = 4;
    auto folderPath = L"MyFolder";

    // Get the shape from the group shape.
    auto shape = slidesApi->getShape(fileName, slideIndex, shapeIndex, L"", folderPath, L"", subShape).get();

    // Change the shape properties.
    shape->setHidden(true);

    // Update the shape properties.
    auto updatedShape = slidesApi->updateShape(fileName, slideIndex, shapeIndex, shape, L"", folderPath, L"", sibShape).get();

    // Check if the shape is hidden.
    std::wcout << "The shape is hidden: " << updatedShape->getHidden();

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

my %parameters = (name => "MyPresentation.pptx", slide_index => 1, shape_index => 4, folder => "MyFolder", sub_shape => "2");

# Get the shape from the group shape.
my $shape = $slides_api->get_shape(%parameters);

# Change the shape properties.
$shape->{hidden} = 1;

# Update the shape properties.
$parameters{dto} = $shape;
my $updated_shape = $slides_api->update_shape(%parameters);

# Check if the shape is hidden.
print "The shape is hidden: " . $updated_shape->{hidden};
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
