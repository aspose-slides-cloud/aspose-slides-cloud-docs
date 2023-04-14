---
title: "Update Table Cell"
type: docs
url: /update-table-cell/
weight: 30
---
## **Introduction**
Aspose.Slides.Cloud API allows updating various properties of a table cell.
## **UpdateTableCell**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}|PUT|Returns table info|[UpdateTableCell](#)
### **Examples**
**cURL Example**

The code example below shows how to update text within table cell. The first cell in the second row will be updated. If you want to update text properties on paragraph or portion level, use the [appropriate methods](../working-with-table-cell-text/_index.md)


{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/2/cell/1" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json" -F @"tableCell.json" 
```

tableCell.json
```json
{
    "text": "Test text"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}
```sh

Code: 200
Returns table cell info.

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
int rowIndex = 2;
int cellIndex = 1;
TableCell dto = new TableCell(){Text = "Test text"};

TableCell response = api.UpdateTableCell("MyPresentation.pptx", dto, slideIndex, shapeIndex, rowIndex, cellIndex, cellIndex);

Console.WriteLine("Cell text has been updated: " + response.Text);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
int rowIndex = 2;
int cellIndex = 1;

TableCell dto = new TableCell();
dto.setText("Test text");

TableCell response = api.updateTableCell("MyPresentation.pptx", dto, slideIndex, shapeIndex, rowIndex, cellIndex, null, null, null);

System.out.println("Cell text has been updated: " + response.getText());
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\TableCell;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 9;
$shapeIndex = 1;
$rowIndex = 2;
$cellIndex = 1;

$dto = new TableCell();
$dto->setText("Test text");

$result = $api->updateTableCell("MyPresentation.pptx", $dto, $slideIndex, $shapeIndex, $rowIndex, $cellIndex);

print("Cell text has been updated: " . $response->getText());
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
row_index = 2
cell_index = 1

dto = AsposeSlidesCloud::TableCell.new
dto.text = "Test text"

result = api.update_table_cell("MyPresentation.pptx", dto, slide_index, shape_index, row_index, cell_index)
print "Cell text has been updated: " + result.text

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
row_index = 2
cell_index = 1

dto = TableCell()
dto.text = "Test text"

response = api.update_table_cell("MyPresentation.pptx", dto, slide_index, shape_index, row_index, cell_index)

print(f"Cell text has been updated: { response.text }")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let slideIndex = 9;
let shapeIndex = 1;
let rowIndex = 2;
let cellIndex = 1;
let dto = new TableCell();
dto.text = "Test text";

const result = await api.updateTableCell("MyPresentation.pptx", dto, slideIndex, shapeIndex, rowIndex, cellIndex);
            
console.log("Cell text has been updated: " + (result.body as model.TableCell).text);
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
var rowIndex int32 = 2
var cellIndex int32 = 1
dto := slidescloud.NewTableCell()
dto.Text = "Test text"

result, _, e := api.UpdateTableCell(fileName, dto, slideIndex, shapeIndex, rowIndex, cellIndex, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Cell text has been updated: %v", result.GetText())
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::TableCell;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $dto = AsposeSlidesCloud::Object::TableCell->new();
$dto->{text} = "Test text";

my %params = (
'name' => "MyPresentation.pptx", 
'folder' => "TempSlidesSDK", 
'slide_index' => 9,
'shape_index' => 1,
'row_index' => 2,
'cell_index' => 1, 
'dto' => $dto);

my $response = $api->update_table_cell(%params);
print "Cell text has been updated: $response->{text} \n"
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)