---
title: "Import a Chart from an Excel Workbook"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- chart
- import chart
- Excel
- workbook
- worksheet
- import from Excel
type: docs
url: /import-chart-from-workbook/
weight: 90
---

## **Introduction**

Aspose.Slides Cloud API allows you to import a chart from an Excel workbook and insert it as a shape on a presentation slide. You can identify the chart by name or by its 1-based index within the worksheet. The workbook can be uploaded as a file or referenced by its path in the storage. To build charts programmatically from scratch instead, see the [Create Charts](/slides/create-charts/) section.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/fromExcelChart|POST|Imports a chart from an Excel workbook and adds it to a slide.|[ImportChartFromWorkbook](https://apireference.aspose.cloud/slides/#/Shapes/ImportChartFromWorkbook)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the target slide.|
|document|file|form|false|The Excel workbook to upload. Either `document` or `workbookPath` must be provided.|
|worksheetName|string|query|true|The name of the worksheet that contains the chart.|
|chartName|string|query|false|The name of the chart to import. Use either `chartName` or `chartIndex`.|
|chartIndex|integer|query|false|The 1-based index of the chart in the worksheet. Use either `chartName` or `chartIndex`.|
|x|number|query|false|The X coordinate of the chart shape on the slide, in points.|
|y|number|query|false|The Y coordinate of the chart shape on the slide, in points.|
|embedAllWorkbook|boolean|query|false|When `true` (default), the entire workbook is embedded in the shape. When `false`, only the chart data is embedded.|
|workbookPath|string|query|false|The path to the workbook file in the storage. Used instead of `document` when the file is already stored.|
|workbookStorage|string|query|false|The name of the storage containing `workbookPath`.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage containing the `folder`.|

## **Example**

Import the chart named **"Sales Chart"** from the **"Revenue"** worksheet in **MyWorkbook.xlsx** and add it to the **first** slide of **MyPresentation.pptx** at position **(100, 100)**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Import the Chart**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/fromExcelChart?worksheetName=Revenue&chartName=Sales%20Chart&x=100&y=100" \
     -H "authorization: Bearer MyAccessToken" \
     -F "document=@MyWorkbook.xlsx"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "type": "Chart",
    "chartType": "ClusteredColumn",
    "showDataLabelsOverMaximum": true,
    "series": [
        {
            "dataPointType": "OneValue",
            "dataPoints": [
                { "value": 15.0 },
                { "value": 30.0 },
                { "value": 45.0 }
            ],
            "name": "Series 1",
            "order": 0,
            "invertIfNegative": false
        }
    ],
    "categories": [
        { "value": "Q1" },
        { "value": "Q2" },
        { "value": "Q3" }
    ],
    "hasTitle": true,
    "title": { "text": "Sales Chart" },
    "name": "ChartObject",
    "width": 400.0,
    "height": 300.0,
    "alternativeText": "",
    "alternativeTextTitle": "",
    "hidden": false,
    "x": 100.0,
    "y": 100.0,
    "zOrderPosition": 1,
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
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2",
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
using System.IO;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        using var workbookStream = File.OpenRead("MyWorkbook.xlsx");

        // Import the chart named "Sales Chart" from the "Revenue" worksheet.
        var shape = slidesApi.ImportChartFromWorkbook("MyPresentation.pptx", 1, workbookStream, "Revenue", chartName: "Sales Chart", x: 100, y: 100);

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

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        byte[] workbookData = Files.readAllBytes(Paths.get("MyWorkbook.xlsx"));

        // Import the chart named "Sales Chart" from the "Revenue" worksheet.
        ShapeBase shape = slidesApi.importChartFromWorkbook("MyPresentation.pptx", 1, workbookData, "Revenue", "Sales Chart", null, 100.0, 100.0, null, null, null, null);

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

$workbookFile = fopen("MyWorkbook.xlsx", "r");

// Import the chart named "Sales Chart" from the "Revenue" worksheet.
$shape = $slidesApi->importChartFromWorkbook("MyPresentation.pptx", 1, $workbookFile, "Revenue", "Sales Chart", null, 100, 100);

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

workbook_data = File.binread("MyWorkbook.xlsx")

# Import the chart named "Sales Chart" from the "Revenue" worksheet.
shape = slides_api.import_chart_from_workbook("MyPresentation.pptx", 1, workbook_data, "Revenue", chart_name: "Sales Chart", x: 100, y: 100)

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

with open("MyWorkbook.xlsx", "rb") as workbook_stream:
    workbook_data = workbook_stream.read()

# Import the chart named "Sales Chart" from the "Revenue" worksheet.
shape = slides_api.import_chart_from_workbook("MyPresentation.pptx", 1, workbook_data, "Revenue", chart_name="Sales Chart", x=100, y=100)

# Print a resource reference to the new shape.
print(shape.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Node.js

const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const workbookData = fs.readFileSync("MyWorkbook.xlsx");

// Import the chart named "Sales Chart" from the "Revenue" worksheet.
slidesApi.importChartFromWorkbook("MyPresentation.pptx", 1, workbookData, "Revenue", "Sales Chart", null, 100, 100).then(shape => {
    // Print a resource reference to the new shape.
    console.log(shape.body.selfUri.href);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Perl

use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $workbook_data = read_file("MyWorkbook.xlsx", { binmode => ":raw" });

# Import the chart named "Sales Chart" from the "Revenue" worksheet.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, document => $workbook_data, worksheet_name => "Revenue", chart_name => "Sales Chart", x => 100, y => 100);
my $shape = $slides_api->import_chart_from_workbook(%parameters);

# Print a resource reference to the new shape.
print $shape->{self_uri}->{href};
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
