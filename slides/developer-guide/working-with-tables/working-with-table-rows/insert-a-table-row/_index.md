---
title: "Insert a Table Row"
type: docs
url: /insert-a-table-row/
weight: 10
---
## **Introduction**
Aspose.Slides.Cloud API allows adding new rows to a table. You can insert a row at the specified position, or append it to the end of the table.
## **InsertTableRow**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows|POST|Returns table row info|[InsertTableRow](#)
### **Examples**
**cURL Example**

The code example below shows how to append a new row to the table.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json" -F @"tableRow.json" 
```

tableRow.json
```json
{
    "minimalHeight": 30,
    "cells":[
        {
            "text": "Cell 1"
        },
        {
            "text": "Cell 2"
        },
        {
            "text": "Cell 3",
        },
        {
            "text": "Cell 4"
        }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}
```sh

Code: 200
Returns table row info.

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
TableRow dto = new TableRow()
{
    MinimalHeight = 30,
    Cells = new List<TableCell>
    {
        new TableCell {Text = "Cell 1"},
        new TableCell {Text = "Cell 2"},
        new TableCell {Text = "Cell 3"},
        new TableCell {Text = "Cell 4"}
    }
};

TableRow response = api.CreateTableRow("MyPresentation.pptx", slideIndex, shapeIndex, dto);

Console.WriteLine("The row has been added");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
TableCell cell0 = new TableCell();
cell0.setText("Cell 1");
TableCell cell1 = new TableCell();
cell0.setText("Cell 2");
TableCell cell2 = new TableCell();
cell0.setText("Cell 3");
TableCell cell3 = new TableCell();
cell0.setText("Cell 4");

TableRow dto = new TableRow();
dto.setMinimalHeight(30.0);
dto.setCells(new ArrayList(Arrays.asList(cell0, cell1, cell2, cell3)));

TableRow response = api.createTableRow("MyPresentation.pptx", slideIndex, shapeIndex, dto, null, null, null, null);

System.out.println("The row has been added");
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\TableRow;
use Aspose\Slides\Cloud\Sdk\Model\TableCell;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 9;
$shapeIndex = 1;
$cell0 = new TableCell();
$cell0->setText("Cell 1");
$cell1 = new TableCell();
$cell1->setText("Cell 2");
$cell2 = new TableCell();
$cell2->setText("Cell 3");
$cell3 = new TableCell();
$cell3->setText("Cell 4");

$dto = new TableRow();
$dto->setMinimalHeight(30);
$dto->setCells([$cell0, $cell1, $cell2, $cell3]);

$result = $api->createTableRow("MyPresentation.pptx", $slideIndex, $shapeIndex, $dto);

print("The row has been added");
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
cell0 = AsposeSlidesCloud::TableCell.new
cell0.text = "Cell 1"
cell1 = AsposeSlidesCloud::TableCell.new
cell1.text = "Cell 2"
cell2 = AsposeSlidesCloud::TableCell.new
cell2.text = "Cell 2"
cell3 = AsposeSlidesCloud::TableCell.new
cell3.text = "Cell 3"

dto = AsposeSlidesCloud::TableRow.new
dto.minimal_height = 30
dto.cells = [cell0, cell1, cell2, cell3]

result = api.create_table_row("MyPresentation.pptx", slide_index, shape_index, dto)
print "The row has been added"

```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.table_row import TableRow
from asposeslidescloud.models.table_cell import TableCell

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

slide_index = 9
shape_index = 1
cell_0 = TableCell()
cell_0.text = "Cell 1"
cell_1 = TableCell()
cell_1.text = "Cell 2"
cell_2 = TableCell()
cell_2.text = "Cell 3"
cell_3 = TableCell()
cell_3.text = "Cell 4"
dto = TableRow()
dto.minimal_height = 30
dto.cells = [cell_0, cell_1, cell_2, cell_3]

response = api.create_table_row("MyPresentation.pptx", slide_index, shape_index, dto)

print(f"The row has been added")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let slideIndex = 9;
let shapeIndex = 1;

let cell0 = new CloudSdk.TableCell();
cell0.text = "Cell 1";
let cell1 = new CloudSdk.TableCell();
cell1.text = "Cell 2";
let cell2 = new CloudSdk.TableCell();
cell2.text = "Cell 3";
let cell3 = new CloudSdk.TableCell();
cell3.text = "Cell 4";
            
let dto = new CloudSdk.TableRow();
dto.minimalHeight = 30;
dto.cells = [cell0, cell1, cell2, cell3];

const result = await api.createTableRow("MyPresentation.pptx", slideIndex, shapeIndex, dto);
            
console.log("The row has been added");
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
cell0 := asposeslidescloud.NewTableCell()
cell0.Text = "Cell 1"
cell1 := asposeslidescloud.NewTableCell()
cell1.Text = "Cell 2"
cell2 := asposeslidescloud.NewTableCell()
cell2.Text = "Cell 3"
cell3 := asposeslidescloud.NewTableCell()
cell3.Text = "Cell 4"

dto := asposeslidescloud.NewTableRow()
dto.MinimalHeight = 30
dto.Cells = []asposeslidescloud.ITableCell{cell0, cell1, cell2, cell3}

result, _, e := api.SlidesApi.CreateTableRow(fileName, slideIndex, shapeIndex, dto, nil, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("The row has been added: %v cells.", len(result.GetCells()))
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::TableRow;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $cell0 = AsposeSlidesCloud::Object::TableCell->new();
$cell0->{text} = "Cell 1";
my $cell1 = AsposeSlidesCloud::Object::TableCell->new();
$cell1->{text} = "Cell 2";
my $cell2 = AsposeSlidesCloud::Object::TableCell->new();
$cell2->{text} = "Cell 3";
my $cell3 = AsposeSlidesCloud::Object::TableCell->new();
$cell3->{text} = "Cell 4";
my @cells = ( $cell0, $cell1, $cell2, $cell3 );

my $dto = AsposeSlidesCloud::Object::TableRow->new();
$dto->{minimal_height} = 30;
$dto->{cells} = \@cells;

my %params = (
'name' => "MyPresentation.pptx",
'slide_index' => 9,
'shape_index' => 1,
'dto' => $dto);

my $response = $api->create_table_row(%params);
print "The row has been added \n";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
