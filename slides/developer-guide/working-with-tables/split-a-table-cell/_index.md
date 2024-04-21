---
title: "Split a Table Cell"
keywords: "PowerPoint, presentation, REST API, Cloud API, table, split a cell"
type: docs
url: /split-a-table-cell/
weight: 50
---
## **Introduction**
Aspose.Slides.Cloud API provides different options for splitting table cells. There are four of them: by width, by height, by col span and by row span. Last two options can be applied for merged cells. The methods accept a mandatory **value** argument. In the case of splitting by width or height, you have to specify desired cell width or height accordingly. In the case of splitting by span, the col span or row span value has to be provided.
## **SplitTableCell**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/splitByWidth/{value}|POST|Returns table info|[SplitTableCell](#)
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/splitByHeight/{value}|POST|Returns table info|[SplitTableCell](#)
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/splitByColSpan/{value}|POST|Returns table info|[SplitTableCell](#)
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/splitByRowSpan/{value}|POST|Returns table info|[SplitTableCell](#)
### **Examples**
**cURL Example**

The code example below shows how to split a cell by width. The width of the new cell is 10.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/1/cells/1/splitByWidth/10" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json"
```

{{< /tab >}}

{{< tab tabNum="2" >}}
```sh

Code: 200
Returns table info.

```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
int rowIndex = 1;
int cellIndex = 1;
int cellWidth = 10;

Table response = api.SplitTableCell("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, TableCellSplitType.SplitByWidth, cellWidth);

Console.WriteLine("Cells count in the row: " + response.Rows[0].Cells.Count);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
int rowIndex = 1;
int cellIndex = 1;
double cellWidth = 10.0;

Table response = api.splitTableCell("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, TableCellSplitType.SPLITBYWIDTH, cellWidth, null, null, null);

System.out.println("Cells count in the row: " + response.getRows().get(0).getCells().size());
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 9;
$shapeIndex = 1;
$rowIndex = 1;
$cellIndex = 1;
$cellWidth = 10;

$result = $api->splitTableCell("MyPresentation.pptx", $slideIndex, $shapeIndex, $rowIndex, $cellIndex, 'SplitByWidth', $cellWidth);

print("Cells count in the row: " . count($result->getRows()[0]->getCells()));
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

slide_index = 9
shape_index = 1        
row_index = 1
cell_index = 1
cell_width = 10

result = api.split_table_cell("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index, "SplitByWidth", cell_width)
puts "Cells count in the row: #{result.rows[0].cells.length}"
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

slide_index = 9
shape_index = 1
row_index = 1
slides_index = 1
cell_index = 1
cell_width = 10

response = api.split_table_cell("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index, 'splitByWidth', cell_width)

print(f"Cells count in the row: { len(response.rows[0].cells) }")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let slideIndex = 9;
let shapeIndex = 1;
let rowIndex = 1;
let cellIndex = 1;
let cellWidth = 10;

const result = await api.splitTableCell("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, CloudSdk.TableCellSplitType.SplitByWidth, cellWidth);
            
console.log("Cells count in the row: " + result.body.rows[0].cells.length);
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
var slideIndex int32 = 9
var shapeIndex int32 = 1
var rowIndex int32 = 1
var cellIndex int32 = 1
var cellWidth int32 = 10

result, _, e := api.SlidesApi.SplitTableCell(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, "SplitByWidth", float64(cellWidth), "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Cells count in the row: %v", len(result.GetRows()[0].GetCells()))
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %params = (
'name' => "MyPresentation.pptx", 
'split_type' => 'SplitByWidth',
'value' => 10,
'slide_index' => 9,
'shape_index' => 1, 
'row_index' => 1,
'cell_index' => 1);

my $response = $api->split_table_cell(%params);

print "Cells count in the row: scalar @{$response->{rows}[0]{cells}} \n";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
