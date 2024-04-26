---
title: "Merge Table Cells"
keywords: "PowerPoint, presentation, REST API, Cloud API, table, merge cells"
type: docs
url: /merge-table-cells/
weight: 40
---
## **Introduction**
Aspose.Slides.Cloud API allows merging table cells.
## **MergeTableCells**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/mergeCells|POST|Returns table info|[MergeTableCells](#)
### **Examples**
**cURL Example**

The code example below shows how to merge four cells {1,1} {1,2} {2,1} {2,2} into one cell.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/mergeCells" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json" -F @"tableCellMergeOptions.json" 
```

tableCellMergeOptions.json
```json
{
    "firstRowIndex": 1,
    "firstCellIndex": 1,
    "lastRowIndex": 2,
    "lastCellIndex": 2,
    "allowSplitting" : true
}
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
var dto = new TableCellMergeOptions()
{
    FirstRowIndex = 1,
    FirstCellIndex = 1,
    LastRowIndex = 2,
    LastCellIndex = 2,
    AllowSplitting = true
};
Table response = api.MergeTableCells("MyPresentation.pptx", slideIndex, shapeIndex, dto);

Console.WriteLine("Cell col span is: " + response.Rows[0].Cells[0].ColSpan);
Console.WriteLine("Cell row span is: " + response.Rows[0].Cells[0].RowSpan);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
TableCellMergeOptions dto = new TableCellMergeOptions();
dto.setFirstRowIndex(1);
dto.setFirstCellIndex(1);
dto.lastRowIndex(2);
dto.lastCellIndex(2);
dto.setAllowSplitting(true);

Table response = api.mergeTableCells("MyPresentation.pptx", slideIndex, shapeIndex, dto, null, null, null);

System.out.println("Cell col span is: " + response.getRows().get(0).getCells().get(0).getColSpan());
System.out.println("Cell row span is: " + response.getRows().get(0).getCells().get(0).getRowSpan());
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\TableCellMergeOptions;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 9;
$shapeIndex = 1;
$dto = new TableCellMergeOptions();
$dto->setFirstRowIndex(1);
$dto->setFirstCellIndex(1);
$dto->setLastRowIndex(2);
$dto->setLastCellIndex(2);
$dto->setAllowSplitting(true);

$result = $api->mergeTableCells("MyPresentation.pptx", $slideIndex, $shapeIndex, $dto);

print("Cell col span is: " . $result->getRows()[0]->getCells()[0]->getColSpan());
print("Cell row span is: " . $result->getRows()[0]->getCells()[0]->getRowSpan());
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
dto = AsposeSlidesCloud::TableCellMergeOptions.new
dto.first_row_index = 1
dto.first_cell_index = 1
dto.last_row_index = 2
dto.last_cell_index = 2
dto.allow_splitting = true

result = api.merge_table_cells("MyPresentation.pptx", slide_index, shape_index, dto)
puts "Cell col span is: #{result.rows[0].cells[0].col_span}"
puts "Cell row span is: #{result.rows[0].cells[0].row_span}"
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.table_cell_merge_options import TableCellMergeOptions

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

slide_index = 9
shape_index = 1
dto = TableCellMergeOptions()
dto.first_row_index = 1
dto.first_cell_index = 1
dto.last_row_index = 2
dto.last_cell_index = 2

response = api.merge_table_cells("MyPresentation.pptx", slide_index, shape_index, dto)

print(f"Cell col span is: { response.rows[0].cells[0].col_span }")
print(f"Cell row span is: { response.rows[0].cells[0].row_span }")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let slideIndex = 9;
let shapeIndex = 1;
let dto = new CloudSdk.TableCellMergeOptions();
dto.firstRowIndex = 1;
dto.firstCellIndex = 1;
dto.lastRowIndex = 2;
dto.lastCellIndex = 2;
dto.allowSplitting = true;

const result = await api.mergeTableCells("MyPresentation.pptx", slideIndex, shapeIndex, dto);
            
console.log("Cell col span is: " + result.body.rows[0].cells[0].colSpan);
console.log("Cell row span is: " + result.body.rows[0].cells[0].rowSpan);
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

dto := asposeslidescloud.NewTableCellMergeOptions()
dto.FirstRowIndex = 1
dto.FirstCellIndex = 1
dto.LastRowIndex = 2
dto.LastCellIndex = 2

result, _, e := api.SlidesApi.MergeTableCells(fileName, slideIndex, shapeIndex, dto, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Cell col span is: %v", result.GetRows()[0].GetCells()[0].GetColSpan())
fmt.Printf("Cell row span is: %v", result.GetRows()[0].GetCells()[0].GetRowSpan())
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::TableCellMergeOptions;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $dto = AsposeSlidesCloud::Object::TableCellMergeOptions->new();
$dto->{first_row_index} = 1;
$dto->{first_cell_index} = 1;
$dto->{last_row_index} = 2;
$dto->{last_cell_index} = 2;
$dto->{allow_splitting} = 'true';

my %params = (
'name' => "MyPresentation.pptx", 
'slide_index' => 9,
'shape_index' => 1, 
'table_cell_merge_options' => $dto);

my $response = $api->merge_table_cells(%params);

print "Cell col span is: $response->{rows}[0]{cells}[0]->col_span \n";
print "Cell row span is: $response->{rows}[0]{cells}[0]->row_span \n";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)