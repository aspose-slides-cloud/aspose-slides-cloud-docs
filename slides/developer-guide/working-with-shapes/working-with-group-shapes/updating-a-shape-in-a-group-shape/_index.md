---
title: "Updating a Shape in a Group Shape"
type: docs
url: /updating-a-shape-in-a-group-shape/
weight: 30
---


## **Introduction**

This article shows you how to update shape properties inside a group shape using Aspose.Slides Cloud API in your applications. The following method allows you to specify a path to a shape group, a shape index, and transfer shape properties to update. The shape properties that need to be updated depend on the shape type.

## **UpdateSubshape**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}|PUT|Updates shape properties inside a shape group.|[UpdateSubshape](https://apireference.aspose.cloud/slides/#/Shapes/UpdateSubshape)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide containing the group shape.|
|path|string|path|true|The path to the shape group, relative to the slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape to update.|
|dto|object|body|true|The transfer object with new data for the shape.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{% alert color="primary" %}} 

For more information about the `path` parameter, see [Extracting Shapes from a Group Shape](/slides/extracting-shapes-from-a-group-shape/).

{{% /alert %}}

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
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/4/shapes/2?folder=MyFolder" \
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

The code examples below also use the `GetSubshape` method described in [Extracting Shapes from a Group Shape](/slides/extracting-shapes-from-a-group-shape/).

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
        var shapesPath = "4/shapes";
        var shapeIndex = 2;
        var folderPath = "MyFolder";

        // Get the shape from the group shape.
        var shape = slidesApi.GetSubshape(fileName, slideIndex, shapesPath, shapeIndex, null, folderPath);

        // Change the shape properties.
        shape.Hidden = true;

        // Update the shape properties.
        var updatedShape = slidesApi.UpdateSubshape(fileName, slideIndex, shapesPath, shapeIndex, shape, null, folderPath);

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
        String shapesPath = "4/shapes";
        int shapeIndex = 2;
        String folderPath = "MyFolder";

        // Get the shape from the group shape.
        ShapeBase shape = slidesApi.getSubshape(fileName, slideIndex, shapesPath, shapeIndex, null, folderPath, null);

        // Change the shape properties.
        shape.setHidden(true);

        // Update the shape properties.
        ShapeBase updatedShape = slidesApi.updateSubshape(fileName, slideIndex, shapesPath, shapeIndex, shape, null, folderPath, null);

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
$shapesPath = "4/shapes";
$shapeIndex = 2;
$folderPath = "MyFolder";

// Get the shape from the group shape.
$shape = $slidesApi->getSubshape($fileName, $slideIndex, $shapesPath, $shapeIndex, null, $folderPath);

// Change the shape properties.
$shape->setHidden(true);

// Update the shape properties.
$updatedShape = $slidesApi->updateSubshape($fileName, $slideIndex, $shapesPath, $shapeIndex, $shape, null, $folderPath);

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
shapes_path = "4/shapes"
shape_index = 2
folder_path = "MyFolder"

# Get the shape from the group shape.
shape = slides_api.get_subshape(file_name, slide_index, shapes_path, shape_index, nil, folder_path)

# Change the shape properties.
shape.hidden = true

# Update the shape properties.
updated_shape = slides_api.update_subshape(file_name, slide_index, shapes_path, shape_index, shape, nil, folder_path)

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
shapes_path = "4/shapes"
shape_index = 2
folder_path = "MyFolder"

# Get the shape from the group shape.
shape = slides_api.get_subshape(file_name, slide_index, shapes_path, shape_index, None, folder_path)

# Change the shape properties.
shape.hidden = True

# Update the shape properties.
updated_shape = slides_api.update_subshape(file_name, slide_index, shapes_path, shape_index, shape, None, folder_path)

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
const shapesPath = "4/shapes"
const shapeIndex = 2
const folderPath = "MyFolder"

// Get the shape from the group shape.
slidesApi.getSubshape(fileName, slideIndex, shapesPath, shapeIndex, null, folderPath).then((shape) => {
    // Change the shape properties.
    shape.body.hidden = true

    // Update the shape properties.
    slidesApi.updateSubshape(fileName, slideIndex, shapesPath, shapeIndex, shape.body, null, folderPath).then((updatedShape) => {
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
    auto shapesPath = L"4/shapes";
    auto shapeIndex = 2;
    auto folderPath = L"MyFolder";

    // Get the shape from the group shape.
    auto shape = slidesApi->getSubshape(fileName, slideIndex, shapesPath, shapeIndex, L"", folderPath).get();

    // Change the shape properties.
    shape->setHidden(true);

    // Update the shape properties.
    auto updatedShape = slidesApi->updateSubshape(fileName, slideIndex, shapesPath, shapeIndex, shape, L"", folderPath).get();

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

my %parameters = (name => "MyPresentation.pptx", slide_index => 1, path => "4/shapes", shape_index => 2, folder => "MyFolder");

# Get the shape from the group shape.
my $shape = $slides_api->get_subshape(%parameters);

# Change the shape properties.
$shape->{hidden} = 1;

# Update the shape properties.
$parameters{dto} = $shape;
my $updated_shape = $slides_api->update_subshape(%parameters);

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
