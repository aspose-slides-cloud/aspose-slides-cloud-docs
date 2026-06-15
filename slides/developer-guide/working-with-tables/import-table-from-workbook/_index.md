---
title: "Import a Table from an Excel Workbook"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- table
- import table
- Excel
- workbook
- worksheet
- cell range
- import from Excel
type: docs
url: /import-table-from-workbook/
weight: 60
---

## **Introduction**

Aspose.Slides Cloud API allows you to import a table from an Excel workbook and insert it as a shape on a presentation slide. You specify the source worksheet and the cell range that contains the data. The workbook can be uploaded as a file or referenced by its path in the storage. To define and add a table structure programmatically instead, see [Add a Shape to a Slide](/slides/add-a-shape-to-a-slide/).

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/fromExcelTable|POST|Imports a table from an Excel workbook and adds it to a slide.|[ImportTableFromWorkbook](https://apireference.aspose.cloud/slides/#/Shapes/ImportTableFromWorkbook)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the target slide.|
|document|file|form|false|The Excel workbook to upload. Either `document` or `workbookPath` must be provided.|
|worksheetName|string|query|true|The name of the worksheet that contains the data.|
|cellRange|string|query|true|The cell range to import (e.g. `A1:D10`).|
|x|number|query|false|The X coordinate of the table shape on the slide, in points.|
|y|number|query|false|The Y coordinate of the table shape on the slide, in points.|
|workbookPath|string|query|false|The path to the workbook file in the storage. Used instead of `document` when the file is already stored.|
|workbookStorage|string|query|false|The name of the storage containing `workbookPath`.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage containing the `folder`.|

## **Example**

Import the data from the range **"A1:D5"** in the **"Sheet1"** worksheet of **MyWorkbook.xlsx** and add it as a table to the **first** slide of **MyPresentation.pptx** at position **(50, 200)**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Import the Table**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/fromExcelTable?worksheetName=Sheet1&cellRange=A1:D5&x=50&y=200" \
     -H "authorization: Bearer MyAccessToken" \
     -F "document=@MyWorkbook.xlsx"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "type": "Table",
    "columns": [
        { "width": 100.0 },
        { "width": 100.0 },
        { "width": 100.0 },
        { "width": 100.0 }
    ],
    "rows": [
        {
            "cells": [
                { "text": "Name" },
                { "text": "Q1" },
                { "text": "Q2" },
                { "text": "Q3" }
            ],
            "minimalHeight": 20.0
        },
        {
            "cells": [
                { "text": "Product A" },
                { "text": "10" },
                { "text": "20" },
                { "text": "30" }
            ],
            "minimalHeight": 20.0
        }
    ],
    "name": "Table",
    "width": 400.0,
    "height": 100.0,
    "alternativeText": "",
    "alternativeTextTitle": "",
    "hidden": false,
    "x": 50.0,
    "y": 200.0,
    "zOrderPosition": 1,
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

        // Import the range A1:D5 from worksheet "Sheet1" as a table.
        var shape = slidesApi.ImportTableFromWorkbook("MyPresentation.pptx", 1, workbookStream, "Sheet1", "A1:D5", x: 50, y: 200);

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

        // Import the range A1:D5 from worksheet "Sheet1" as a table.
        ShapeBase shape = slidesApi.importTableFromWorkbook("MyPresentation.pptx", 1, workbookData, "Sheet1", "A1:D5", 50.0, 200.0, null, null, null);

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

// Import the range A1:D5 from worksheet "Sheet1" as a table.
$shape = $slidesApi->importTableFromWorkbook("MyPresentation.pptx", 1, $workbookFile, "Sheet1", "A1:D5", 50, 200);

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

# Import the range A1:D5 from worksheet "Sheet1" as a table.
shape = slides_api.import_table_from_workbook("MyPresentation.pptx", 1, workbook_data, "Sheet1", "A1:D5", x: 50, y: 200)

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

# Import the range A1:D5 from worksheet "Sheet1" as a table.
shape = slides_api.import_table_from_workbook("MyPresentation.pptx", 1, workbook_data, "Sheet1", "A1:D5", x=50, y=200)

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

// Import the range A1:D5 from worksheet "Sheet1" as a table.
slidesApi.importTableFromWorkbook("MyPresentation.pptx", 1, workbookData, "Sheet1", "A1:D5", 50, 200).then(shape => {
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

# Import the range A1:D5 from worksheet "Sheet1" as a table.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, document => $workbook_data, worksheet_name => "Sheet1", cell_range => "A1:D5", x => 50, y => 200);
my $shape = $slides_api->import_table_from_workbook(%parameters);

# Print a resource reference to the new shape.
print $shape->{self_uri}->{href};
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
