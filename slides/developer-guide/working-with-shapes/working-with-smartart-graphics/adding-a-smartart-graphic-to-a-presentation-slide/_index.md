---
title: "Adding a SmartArt Graphic to a Presentation Slide"
type: docs
url: /adding-a-smartart-graphic-to-a-presentation-slide/
weight: 10
---

## **Introduction**

This article shows you how to add a SmartArt graphic to a PowerPoint presentation using Aspose.Slides Cloud in your applications. The code examples in this article use `CreateShape` method described in [Adding Shapes to a PowerPoint Presentation](/slides/adding-shapes-to-a-powerpoint-presentation/) method.

## **Example**

Add a SmartArt **gear** shape that displays a business process consisting of three elements (**Sales**, **Analysis**, **Development**) to the **first** slide in **MyFolder/MyPresentation.pptx** document saved in the default storage. The shape should be placed at coordinates **(20, 20)** with a size of **200x200**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the SmartArt Shape**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @BusinessProcess.json
```

BusinessProcess.json content:

```json
{
    "Type": "SmartArt",
    "X": 20,
    "Y": 20,
    "Width": 200,
    "Height": 200,
    "Layout": "Gear",
    "QuickStyle": "IntenceEffect",
    "ColorStyle": "ColorfulAccentColors",
    "Nodes": [
        {
            "Text": "Development"
        },
        {
            "Text": "Analysis"
        },
        {
            "Text": "Sales"
        }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "type": "SmartArt",
    "layout": "Gear",
    "quickStyle": "IntenceEffect",
    "colorStyle": "ColorfulAccentColors",
    "nodes": [
        {
            "nodes": [],
            "shapes": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/nodes/1/shapes?folder=MyFolder",
                "relation": "self",
                "slideIndex": 1,
                "shapeIndex": 1
            },
            "isAssistant": false,
            "text": "Development",
            "orgChartLayout": "Initial",
            "paragraphs": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/nodes/1/paragraphs?folder=MyFolder",
                "relation": "self",
                "slideIndex": 1,
                "shapeIndex": 1
            }
        },
        {
            "nodes": [],
            "shapes": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/nodes/2/shapes?folder=MyFolder",
                "relation": "self",
                "slideIndex": 1,
                "shapeIndex": 1
            },
            "isAssistant": false,
            "text": "Analysis",
            "orgChartLayout": "Initial",
            "paragraphs": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/nodes/2/paragraphs?folder=MyFolder",
                "relation": "self",
                "slideIndex": 1,
                "shapeIndex": 1
            }
        },
        {
            "nodes": [],
            "shapes": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/nodes/3/shapes?folder=MyFolder",
                "relation": "self",
                "slideIndex": 1,
                "shapeIndex": 1
            },
            "isAssistant": false,
            "text": "Sales",
            "orgChartLayout": "Initial",
            "paragraphs": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/nodes/3/paragraphs?folder=MyFolder",
                "relation": "self",
                "slideIndex": 1,
                "shapeIndex": 1
            }
        }
    ],
    "isReversed": false,
    "name": "New Diagram",
    "width": 200.0,
    "height": 200.0,
    "alternativeText": "",
    "alternativeTextTitle": "",
    "hidden": false,
    "x": 20.0,
    "y": 20.0,
    "zOrderPosition": 0,
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
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1
    }
}
```

{{< /tab >}}

{{< /tabs >}}

The resut:

![SmartArt shape](BusinessProcess.png "SmartArt shape")

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;
using System.Collections.Generic;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare data for the SmartArt shape.
        var graphicData = new SmartArt
        {
            X = 20,
            Y = 20,
            Width = 200,
            Height = 200,
            Layout = SmartArt.LayoutEnum.Gear,
            QuickStyle = SmartArt.QuickStyleEnum.IntenceEffect,
            ColorStyle = SmartArt.ColorStyleEnum.ColorfulAccentColors,
            Nodes = new List<SmartArtNode>
            {
                new SmartArtNode
                {
                    Text = "Development"
                },
                new SmartArtNode
                {
                    Text = "Analysis"
                },
                new SmartArtNode
                {
                    Text = "Sales"
                }
            }
        };

        // Create the SmartArt shape.
        var shape = slidesApi.CreateShape("MyPresentation.pptx", 1, graphicData, folder: "MyFolder");

        // Print a resource reference to the shape.
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

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare data for the SmartArt shape.
        SmartArt graphicData = new SmartArt();
        graphicData.setX(20.0);
        graphicData.setY(20.0);
        graphicData.setWidth(200.0);
        graphicData.setHeight(200.0);
        graphicData.setLayout(SmartArt.LayoutEnum.GEAR);
        graphicData.setQuickStyle(SmartArt.QuickStyleEnum.INTENCEEFFECT);
        graphicData.setColorStyle(SmartArt.ColorStyleEnum.COLORFULACCENTCOLORS);
        SmartArtNode firstNode = new SmartArtNode();
        firstNode.setText("Development");
        SmartArtNode secondNode = new SmartArtNode();
        secondNode.setText("Analysis");
        SmartArtNode thirdNode = new SmartArtNode();
        thirdNode.setText("Sales");
        graphicData.setNodes(Arrays.asList(firstNode, secondNode, thirdNode));

        // Create the SmartArt shape.
        ShapeBase shape = slidesApi.createShape("MyPresentation.pptx", 1, graphicData, null, null, null, "MyFolder", null, null);

        // Print a resource reference to the shape.
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
use Aspose\Slides\Cloud\Sdk\Model\SmartArt;
use Aspose\Slides\Cloud\Sdk\Model\SmartArtNode;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $config);

// Prepare data for the SmartArt shape.
$graphicData = new SmartArt();
$graphicData->setX(20);
$graphicData->setY(20);
$graphicData->setWidth(200);
$graphicData->setHeight(200);
$graphicData->setLayout("Gear");
$graphicData->setQuickStyle("IntenceEffect");
$graphicData->setColorStyle("ColorfulAccentColors");
$firstNode = new SmartArtNode();
$firstNode->setText("Development");
$secondNode = new SmartArtNode();
$secondNode->setText("Analysis");
$thirdNode = new SmartArtNode();
$thirdNode->setText("Sales");
$graphicData->setNodes([$firstNode, $secondNode, $thirdNode]);

// Create the SmartArt shape.
$shape = $slidesApi->createShape("MyPresentation.pptx", 1, $graphicData, null, null, null, "MyFolder");

// Print a resource reference to the shape.
echo $shape->getSelfUri()->getHref();
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

# Prepare data for the SmartArt shape.
graphic_data = SmartArt.new
graphic_data.x = 20
graphic_data.y = 20
graphic_data.width = 200
graphic_data.height = 200
graphic_data.layout = "Gear"
graphic_data.quick_style = "IntenceEffect"
graphic_data.color_style = "ColorfulAccentColors"
first_node = SmartArtNode.new
first_node.text = "Development"
second_node = SmartArtNode.new
second_node.text = "Analysis"
third_node = SmartArtNode.new
third_node.text = "Sales"
graphic_data.nodes = [first_node, second_node, third_node]

# Create the SmartArt shape.
shape = slides_api.create_shape("MyPresentation.pptx", 1, graphic_data, nil, nil, nil, "MyFolder")

# Print a resource reference to the shape.
print shape.self_uri.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.smart_art import SmartArt
from asposeslidescloud.models.smart_art_node import SmartArtNode

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare data for the SmartArt shape.
graphic_data = SmartArt()
graphic_data.x = 20
graphic_data.y = 20
graphic_data.width = 200
graphic_data.height = 200
graphic_data.layout = "Gear"
graphic_data.quick_style = "IntenceEffect"
graphic_data.color_style = "ColorfulAccentColors"
first_node = SmartArtNode()
first_node.text = "Development"
second_node = SmartArtNode()
second_node.text = "Analysis"
third_node = SmartArtNode()
third_node.text = "Sales"
graphic_data.nodes = [first_node, second_node, third_node]

# Create the SmartArt shape.
shape = slides_api.create_shape("MyPresentation.pptx", 1, graphic_data, None, None, None, "MyFolder")

# Print a resource reference to the shape.
print(shape.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Prepare data for the SmartArt shape.
const graphicData = new cloud.SmartArt()
graphicData.x = 20
graphicData.y = 20
graphicData.width = 200
graphicData.height = 200
graphicData.layout = "Gear"
graphicData.quickStyle = "IntenceEffect"
graphicData.colorStyle = "ColorfulAccentColors"
const firstNode = new cloud.SmartArtNode()
firstNode.text = "Development"
const secondNode = new cloud.SmartArtNode()
secondNode.text = "Analysis"
const thirdNode = new cloud.SmartArtNode()
thirdNode.text = "Sales"
graphicData.nodes = [firstNode, secondNode, thirdNode]

// Create the SmartArt shape.
slidesApi.createShape("MyPresentation.pptx", 1, graphicData, null, null, null, "MyFolder").then((shape) => {
    // Print a resource reference to the shape.
    console.log(shape.body.selfUri.href)
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/SmartArt.h"
#include "asposeslidescloud/model/SmartArtNode.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Prepare data for the SmartArt shape.
    auto graphicData = std::make_shared<SmartArt>();
    graphicData->setX(20);
    graphicData->setY(20);
    graphicData->setWidth(200);
    graphicData->setHeight(200);
    graphicData->setLayout(L"Gear");
    graphicData->setQuickStyle(L"IntenceEffect");
    graphicData->setColorStyle(L"ColorfulAccentColors");
    auto firstNode = std::make_shared<SmartArtNode>();
    firstNode->setText(L"Development");
    auto secondNode = std::make_shared<SmartArtNode>();
    secondNode->setText(L"Analysis");
    auto thirdNode = std::make_shared<SmartArtNode>();
    thirdNode->setText(L"Sales");
    graphicData->setNodes({ firstNode, secondNode, thirdNode });

    // Create the SmartArt shape.
    auto shape = slidesApi->createShape(L"MyPresentation.pptx", 1, graphicData, boost::none, boost::none, L"", L"MyFolder").get();

    // Print a resource reference to the shape.
    std::wcout << shape->getSelfUri()->getHref();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SmartArt;
use AsposeSlidesCloud::Object::SmartArtNode;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare data for the SmartArt shape.
my $graphic_data = AsposeSlidesCloud::Object::SmartArt->new();
$graphic_data->{x} = 20;
$graphic_data->{y} = 20;
$graphic_data->{width} = 200;
$graphic_data->{height} = 200;
$graphic_data->{layout} = "Gear";
$graphic_data->{quick_style} = "IntenceEffect";
$graphic_data->{color_style} = "ColorfulAccentColors";
my $first_node = AsposeSlidesCloud::Object::SmartArtNode->new();
$first_node->{text} = "Development";
my $second_node = AsposeSlidesCloud::Object::SmartArtNode->new();
$second_node->{text} = "Analysis";
my $third_node = AsposeSlidesCloud::Object::SmartArtNode->new();
$third_node->{text} = "Sales";
$graphic_data->{nodes} = [$first_node, $second_node, $third_node];

# Create the SmartArt shape.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, dto => $graphic_data, folder => "MyFolder");
my $shape = $slides_api->create_shape(%parameters);

# Print a resource reference to the shape.
print $shape->{self_uri}->{href};
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
