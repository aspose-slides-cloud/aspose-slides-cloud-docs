---
title: "Extract Shapes from a Slide"
type: docs
url: /extract-shapes-from-a-slide/
weight: 10
---

## **Introduction**

The following API method allows you to retrieve all shapes or shapes of a specified type from a slide in a PowerPoint presentation saved to a storage.

## **GetShapes**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{slideIndex}/shapes|GET|Reads information about shapes from the slide.|[GetShapes](https://apireference.aspose.cloud/slides/#/Shapes/GetShapes)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
|shapeType|string|query|false|The type of shapes to retrieve. Available values: Shape, Chart, Table, PictureFrame, VideoFrame, AudioFrame, SmartArt, OleObjectFrame, GroupShape, GraphicalObject, Connector, SmartArtShape, ZoomFrame, SectionZoomFrame, SummaryZoomFrame, SummaryZoomSection.|
|subShape|string|query|false|Sub-shape path (e.g. "3", "3/shapes/2)

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read information about **all shapes** and **charts** placed on the **first** slide from **MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get All Shapes**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes" \
     -H "authorization: Bearer MyAccessToken"
```

**Get All Charts**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?shapeType=Chart" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Examples**

All shapes:

```json
{
    "shapesLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1",
            "relation": "self",
            "slideIndex": 1,
            "shapeIndex": 1
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2",
            "relation": "self",
            "slideIndex": 1,
            "shapeIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/3",
            "relation": "self",
            "slideIndex": 1,
            "shapeIndex": 3
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes",
        "relation": "self",
        "slideIndex": 1
    }
}
```

The charts:

```json
{
    "shapesLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2",
            "relation": "self",
            "slideIndex": 1,
            "shapeIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/3",
            "relation": "self",
            "slideIndex": 1,
            "shapeIndex": 3
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes",
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

        // Get all shapes from the first slide.
        var allShapes = slidesApi.GetShapes("MyPresentation.pptx", 1);

        // Get all charts from the first slide.
        var charts = slidesApi.GetShapes("MyPresentation.pptx", 1, shapeType: ShapeType.Chart);

        // Print information about the shapes and charts.
        var shapeCount = allShapes.ShapesLinks.Count;
        var chartCount = charts.ShapesLinks.Count;
        Console.WriteLine($"The slide contains {shapeCount} shapes, including {chartCount} charts.");
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ShapeType;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all shapes from the first slide.
        Shapes allShapes = slidesApi.getShapes("MyPresentation.pptx", 1, null, null, null, null, null);

        // Get all charts from the first slide.
        Shapes charts = slidesApi.getShapes("MyPresentation.pptx", 1, null, null, null, ShapeType.CHART);

        // Print information about the shapes and charts.
        int shapeCount = allShapes.getShapesLinks().size();
        int chartCount = charts.getShapesLinks().size();
        System.out.println("The slide contains " +shapeCount + " shapes, including " + chartCount + " charts.");
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ShapeType;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Get all shapes from the first slide.
$allShapes = $slidesApi->GetShapes("MyPresentation.pptx", 1);

// Get all charts from the first slide.
$charts = $slidesApi->GetShapes("MyPresentation.pptx", 1, null, null, null, ShapeType::CHART);

// Print information about the shapes and charts.
$shapeCount = count($allShapes->getShapesLinks());
$chartCount = count($charts->getShapesLinks());
print("The slide contains " . $shapeCount . " shapes, including " . $chartCount . " charts.");
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

# Get all shapes from the first slide.
all_shapes = slides_api.get_shapes("MyPresentation.pptx", 1)

# Get all charts from the first slide.
charts = slides_api.get_shapes("MyPresentation.pptx", 1, nil, nil, nil, ShapeType::CHART)

# Print information about the shapes and charts.
shape_count = all_shapes.shapes_links.length
chart_count = charts.shapes_links.length
print "The slide contains #{shape_count} shapes, including #{chart_count} charts."
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.shape_type import ShapeType

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get all shapes from the first slide.
all_shapes = slides_api.get_shapes("MyPresentation.pptx", 1)

# Get all charts from the first slide.
charts = slides_api.get_shapes("MyPresentation.pptx", 1, None, None, None, ShapeType.CHART)

# Print information about the shapes and charts.
shape_count = len(all_shapes.shapes_links)
chart_count = len(charts.shapes_links)
print(f"The slide contains {shape_count} shapes, including {chart_count} charts.")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Get all shapes from the first slide.
slidesApi.getShapes("MyPresentation.pptx", 1).then((allShapes) => {
    // Get all charts from the first slide.
    slidesApi.getShapes("MyPresentation.pptx", 1, null, null, null, "Chart").then((charts) => {
        // Print information about the shapes and charts.
        shapeCount = allShapes.body.shapesLinks.length
        chartCount = charts.body.shapesLinks.length
        console.log("The slide contains " + shapeCount + " shapes, including " + chartCount + " charts.")
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

    // Get all shapes from the first slide.
    auto allShapes = slidesApi->getShapes(L"MyPresentation.pptx", 1).get();

    // Get all charts from the first slide.
    auto charts = slidesApi->getShapes(L"MyPresentation.pptx", 1, L"", L"", L"", L"Chart").get();

    // Print information about the shapes and charts.
    auto shapeCount = allShapes->getShapesLinks().size();
    auto chartCount = charts->getShapesLinks().size();
    std::wcout << "The slide contains " << shapeCount << " shapes, including " << chartCount << " charts.";

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

# Get all shapes from the first slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1);
my $all_shapes = $slides_api->get_shapes(%parameters);

# Get all charts from the first slide.
$parameters{shape_type} = "Chart";
my $charts = $slides_api->get_shapes(%parameters);

# Print information about the shapes and charts.
my $shape_count = scalar @{$all_shapes->{shapes_links}};
my $chart_count = scalar @{$charts->{shapes_links}};
print "The slide contains " . $shape_count . " shapes, including " . $chart_count . " charts.";
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

// Get all shapes from the first slide.
allShapes, _, e := c.SlidesApi.GetShapes("MyPresentation.pptx", 1, "", "", "", nil)
if e != nil {
    fmt.Printf("Error: %v.", e)
}

// Get all charts from the first slide.
var shapeType string = "Chart"
charts, _, e := c.SlidesApi.GetShapes("MyPresentation.pptx", 1, "", "", "", &shapeType)
if e != nil {
    fmt.Printf("Error: %v.", e)
}

// Print information about the shapes and charts.
shapeCount = len(allShapes.getShapesLinks())
chartCount = len(charts.getShapesLinks())
fmt.Printf("The slide contains %v shapes, including %v charts", shapeCount, chartCount)
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
