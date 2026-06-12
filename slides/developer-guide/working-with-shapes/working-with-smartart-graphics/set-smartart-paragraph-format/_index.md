---
title: "Set SmartArt Paragraph Format"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- SmartArt
- paragraph format
- default paragraph format
- SmartArt node
- text formatting
type: docs
url: /set-smartart-paragraph-format/
weight: 50
---

## **Introduction**

Aspose.Slides Cloud API allows you to set the default paragraph formatting for SmartArt graphics and individual SmartArt nodes. The `DefaultParagraphFormat` property can be specified on the `SmartArt` object to apply uniform paragraph styling to all nodes, or on individual `SmartArtNode` objects to override the format for specific nodes. For an introduction to adding SmartArt graphics, see [Add a SmartArt Graphic to a Slide](/slides/add-a-smartart-graphic-to-a-slide/).

{{% alert color="primary" %}}
`DefaultParagraphFormat` is a write-only property. It is applied when creating or updating a SmartArt shape and is not returned in read responses.
{{% /alert %}}

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes|POST|Adds a SmartArt shape with paragraph formatting to a slide.|[CreateShape](https://apireference.aspose.cloud/slides/#/Shapes/CreateShape)|
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}|PUT|Updates an existing SmartArt shape and its paragraph formatting.|[UpdateShape](https://apireference.aspose.cloud/slides/#/Shapes/UpdateShape)|

## **Example**

Add a SmartArt **BasicProcess** graphic to the **first** slide in **MyFolder/MyPresentation.pptx**. Set the default paragraph format to use **bold** text with a font size of **14** for all nodes.

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
     -d @SmartArtProcess.json
```

SmartArtProcess.json content:

```json
{
    "Type": "SmartArt",
    "X": 20,
    "Y": 20,
    "Width": 400,
    "Height": 200,
    "Layout": "BasicProcess",
    "QuickStyle": "SimpleFill",
    "ColorStyle": "ColoredFillAccent1",
    "DefaultParagraphFormat": {
        "DefaultPortionFormat": {
            "FontBold": "True",
            "FontHeight": 14
        }
    },
    "Nodes": [
        { "Text": "Step 1" },
        { "Text": "Step 2" },
        { "Text": "Step 3" }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "type": "SmartArt",
    "layout": "BasicProcess",
    "quickStyle": "SimpleFill",
    "colorStyle": "ColoredFillAccent1",
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
            "text": "Step 1",
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
            "text": "Step 2",
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
            "text": "Step 3",
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
    "width": 400.0,
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

**SDK Solutions**

{{< tabs tabTotal="8" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-.NET

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;
using System.Collections.Generic;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Define default paragraph formatting (bold, 14pt).
        var defaultPortionFormat = new Portion
        {
            FontBold = Portion.FontBoldEnum.True,
            FontHeight = 14
        };
        var defaultParagraphFormat = new Paragraph
        {
            DefaultPortionFormat = defaultPortionFormat
        };

        // Prepare the SmartArt shape with default paragraph format.
        var graphicData = new SmartArt
        {
            X = 20,
            Y = 20,
            Width = 400,
            Height = 200,
            Layout = SmartArt.LayoutEnum.BasicProcess,
            QuickStyle = SmartArt.QuickStyleEnum.SimpleFill,
            ColorStyle = SmartArt.ColorStyleEnum.ColoredFillAccent1,
            DefaultParagraphFormat = defaultParagraphFormat,
            Nodes = new List<SmartArtNode>
            {
                new SmartArtNode { Text = "Step 1" },
                new SmartArtNode { Text = "Step 2" },
                new SmartArtNode { Text = "Step 3" }
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
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Define default paragraph formatting (bold, 14pt).
        Portion defaultPortionFormat = new Portion();
        defaultPortionFormat.setFontBold(Portion.FontBoldEnum.TRUE);
        defaultPortionFormat.setFontHeight(14.0);
        Paragraph defaultParagraphFormat = new Paragraph();
        defaultParagraphFormat.setDefaultPortionFormat(defaultPortionFormat);

        // Prepare the SmartArt shape with default paragraph format.
        SmartArt graphicData = new SmartArt();
        graphicData.setX(20.0);
        graphicData.setY(20.0);
        graphicData.setWidth(400.0);
        graphicData.setHeight(200.0);
        graphicData.setLayout(SmartArt.LayoutEnum.BASICPROCESS);
        graphicData.setQuickStyle(SmartArt.QuickStyleEnum.SIMPLEFILL);
        graphicData.setColorStyle(SmartArt.ColorStyleEnum.COLOREDFILLACCENT1);
        graphicData.setDefaultParagraphFormat(defaultParagraphFormat);
        SmartArtNode node1 = new SmartArtNode();
        node1.setText("Step 1");
        SmartArtNode node2 = new SmartArtNode();
        node2.setText("Step 2");
        SmartArtNode node3 = new SmartArtNode();
        node3.setText("Step 3");
        graphicData.setNodes(Arrays.asList(node1, node2, node3));

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
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-PHP

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SmartArt;
use Aspose\Slides\Cloud\Sdk\Model\SmartArtNode;
use Aspose\Slides\Cloud\Sdk\Model\Paragraph;
use Aspose\Slides\Cloud\Sdk\Model\Portion;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $config);

// Define default paragraph formatting (bold, 14pt).
$defaultPortionFormat = new Portion();
$defaultPortionFormat->setFontBold("True");
$defaultPortionFormat->setFontHeight(14);
$defaultParagraphFormat = new Paragraph();
$defaultParagraphFormat->setDefaultPortionFormat($defaultPortionFormat);

// Prepare the SmartArt shape with default paragraph format.
$graphicData = new SmartArt();
$graphicData->setX(20);
$graphicData->setY(20);
$graphicData->setWidth(400);
$graphicData->setHeight(200);
$graphicData->setLayout("BasicProcess");
$graphicData->setQuickStyle("SimpleFill");
$graphicData->setColorStyle("ColoredFillAccent1");
$graphicData->setDefaultParagraphFormat($defaultParagraphFormat);
$node1 = new SmartArtNode();
$node1->setText("Step 1");
$node2 = new SmartArtNode();
$node2->setText("Step 2");
$node3 = new SmartArtNode();
$node3->setText("Step 3");
$graphicData->setNodes([$node1, $node2, $node3]);

// Create the SmartArt shape.
$shape = $slidesApi->createShape("MyPresentation.pptx", 1, $graphicData, null, null, null, "MyFolder");

// Print a resource reference to the shape.
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

# Define default paragraph formatting (bold, 14pt).
default_portion_format = AsposeSlidesCloud::Portion.new
default_portion_format.font_bold = "True"
default_portion_format.font_height = 14
default_paragraph_format = AsposeSlidesCloud::Paragraph.new
default_paragraph_format.default_portion_format = default_portion_format

# Prepare the SmartArt shape with default paragraph format.
graphic_data = AsposeSlidesCloud::SmartArt.new
graphic_data.x = 20
graphic_data.y = 20
graphic_data.width = 400
graphic_data.height = 200
graphic_data.layout = "BasicProcess"
graphic_data.quick_style = "SimpleFill"
graphic_data.color_style = "ColoredFillAccent1"
graphic_data.default_paragraph_format = default_paragraph_format
node1 = AsposeSlidesCloud::SmartArtNode.new
node1.text = "Step 1"
node2 = AsposeSlidesCloud::SmartArtNode.new
node2.text = "Step 2"
node3 = AsposeSlidesCloud::SmartArtNode.new
node3.text = "Step 3"
graphic_data.nodes = [node1, node2, node3]

# Create the SmartArt shape.
shape = slides_api.create_shape("MyPresentation.pptx", 1, graphic_data, nil, nil, nil, "MyFolder")

# Print a resource reference to the shape.
print shape.self_uri.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.smart_art import SmartArt
from asposeslidescloud.models.smart_art_node import SmartArtNode
from asposeslidescloud.models.paragraph import Paragraph
from asposeslidescloud.models.portion import Portion

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Define default paragraph formatting (bold, 14pt).
default_portion_format = Portion()
default_portion_format.font_bold = "True"
default_portion_format.font_height = 14
default_paragraph_format = Paragraph()
default_paragraph_format.default_portion_format = default_portion_format

# Prepare the SmartArt shape with default paragraph format.
graphic_data = SmartArt()
graphic_data.x = 20
graphic_data.y = 20
graphic_data.width = 400
graphic_data.height = 200
graphic_data.layout = "BasicProcess"
graphic_data.quick_style = "SimpleFill"
graphic_data.color_style = "ColoredFillAccent1"
graphic_data.default_paragraph_format = default_paragraph_format
node1 = SmartArtNode()
node1.text = "Step 1"
node2 = SmartArtNode()
node2.text = "Step 2"
node3 = SmartArtNode()
node3.text = "Step 3"
graphic_data.nodes = [node1, node2, node3]

# Create the SmartArt shape.
shape = slides_api.create_shape("MyPresentation.pptx", 1, graphic_data, None, None, None, "MyFolder")

# Print a resource reference to the shape.
print(shape.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Node.js

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Define default paragraph formatting (bold, 14pt).
const defaultPortionFormat = new cloud.Portion();
defaultPortionFormat.fontBold = "True";
defaultPortionFormat.fontHeight = 14;
const defaultParagraphFormat = new cloud.Paragraph();
defaultParagraphFormat.defaultPortionFormat = defaultPortionFormat;

// Prepare the SmartArt shape with default paragraph format.
const graphicData = new cloud.SmartArt();
graphicData.x = 20;
graphicData.y = 20;
graphicData.width = 400;
graphicData.height = 200;
graphicData.layout = "BasicProcess";
graphicData.quickStyle = "SimpleFill";
graphicData.colorStyle = "ColoredFillAccent1";
graphicData.defaultParagraphFormat = defaultParagraphFormat;
const node1 = new cloud.SmartArtNode();
node1.text = "Step 1";
const node2 = new cloud.SmartArtNode();
node2.text = "Step 2";
const node3 = new cloud.SmartArtNode();
node3.text = "Step 3";
graphicData.nodes = [node1, node2, node3];

// Create the SmartArt shape.
slidesApi.createShape("MyPresentation.pptx", 1, graphicData, null, null, null, "MyFolder").then(shape => {
    // Print a resource reference to the shape.
    console.log(shape.body.selfUri.href);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/SmartArt.h"
#include "asposeslidescloud/model/SmartArtNode.h"
#include "asposeslidescloud/model/Paragraph.h"
#include "asposeslidescloud/model/Portion.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Define default paragraph formatting (bold, 14pt).
    auto defaultPortionFormat = std::make_shared<Portion>();
    defaultPortionFormat->setFontBold(L"True");
    defaultPortionFormat->setFontHeight(14);
    auto defaultParagraphFormat = std::make_shared<Paragraph>();
    defaultParagraphFormat->setDefaultPortionFormat(defaultPortionFormat);

    // Prepare the SmartArt shape with default paragraph format.
    auto graphicData = std::make_shared<SmartArt>();
    graphicData->setX(20);
    graphicData->setY(20);
    graphicData->setWidth(400);
    graphicData->setHeight(200);
    graphicData->setLayout(L"BasicProcess");
    graphicData->setQuickStyle(L"SimpleFill");
    graphicData->setColorStyle(L"ColoredFillAccent1");
    graphicData->setDefaultParagraphFormat(defaultParagraphFormat);
    auto node1 = std::make_shared<SmartArtNode>();
    node1->setText(L"Step 1");
    auto node2 = std::make_shared<SmartArtNode>();
    node2->setText(L"Step 2");
    auto node3 = std::make_shared<SmartArtNode>();
    node3->setText(L"Step 3");
    graphicData->setNodes({ node1, node2, node3 });

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
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SmartArt;
use AsposeSlidesCloud::Object::SmartArtNode;
use AsposeSlidesCloud::Object::Paragraph;
use AsposeSlidesCloud::Object::Portion;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Define default paragraph formatting (bold, 14pt).
my $default_portion_format = AsposeSlidesCloud::Object::Portion->new();
$default_portion_format->{font_bold} = "True";
$default_portion_format->{font_height} = 14;
my $default_paragraph_format = AsposeSlidesCloud::Object::Paragraph->new();
$default_paragraph_format->{default_portion_format} = $default_portion_format;

# Prepare the SmartArt shape with default paragraph format.
my $graphic_data = AsposeSlidesCloud::Object::SmartArt->new();
$graphic_data->{x} = 20;
$graphic_data->{y} = 20;
$graphic_data->{width} = 400;
$graphic_data->{height} = 200;
$graphic_data->{layout} = "BasicProcess";
$graphic_data->{quick_style} = "SimpleFill";
$graphic_data->{color_style} = "ColoredFillAccent1";
$graphic_data->{default_paragraph_format} = $default_paragraph_format;
my $node1 = AsposeSlidesCloud::Object::SmartArtNode->new();
$node1->{text} = "Step 1";
my $node2 = AsposeSlidesCloud::Object::SmartArtNode->new();
$node2->{text} = "Step 2";
my $node3 = AsposeSlidesCloud::Object::SmartArtNode->new();
$node3->{text} = "Step 3";
$graphic_data->{nodes} = [$node1, $node2, $node3];

# Create the SmartArt shape.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, dto => $graphic_data, folder => "MyFolder");
my $shape = $slides_api->create_shape(%parameters);

# Print a resource reference to the shape.
print $shape->{self_uri}->{href};
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
