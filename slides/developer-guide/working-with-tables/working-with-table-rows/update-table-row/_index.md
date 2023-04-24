---
title: "Update Table Row"
type: docs
url: /update-table-row/
weight: 20
---
## **Introduction**
Aspose.Slides.Cloud API allows updating table rows.
## **UpdateTableRow**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}|PUT|Returns table row info|[UpdateTableRow](#)
### **Examples**
**cURL Example**

The code example below shows how to update the minimal height property of the first table row.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/1" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json" -F @"tableRow.json" 
```

tableRow.json
```json
{
    "minimalHeight": 30
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
int rowIndex = 1;
TableRow dto = new TableRow()
{
    MinimalHeight = 30
};

TableRow response = api.UpdateTableRow("MyPresentation.pptx", dto, slideIndex, shapeIndex, rowIndex);

Console.WriteLine("The new row's minimal height: " + response.MinimalHeight);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
int rowIndex = 1;

TableRow dto = new TableRow();
dto.setMinimalHeight(30.0);

TableRow response = api.updateTableRow("MyPresentation.pptx", dto, slideIndex, shapeIndex, rowIndex, null, null, null);

System.out.println("The new row's minimal height: " + response.getMinimalHeight());
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\TableRow;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 9;
$shapeIndex = 1;
$rowIndex = 1;

$dto = new TableRow();
$dto->setMinimalHeight(30);

$result = $api->updateTableRow("MyPresentation.pptx", $dto, $slideIndex, $shapeIndex, $rowIndex);

print("The new row's minimal height: " . $result->getMinimalHeight());
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

dto = AsposeSlidesCloud::TableRow.new
dto.minimal_height = 30

result = api.update_table_row("MyPresentation.pptx", dto, slide_index, shape_index, row_index)
print "The new row's minimal height: " + result.minimal_height

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
dto = TableRow()
dto.minimal_height = 30

response = api.update_table_row("MyPresentation.pptx", dto, slide_index, shape_index, row_index)

print(f"The new row's minimal height: {response.minimal_height}")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let slideIndex = 9;
let shapeIndex = 1;
let rowIndex = 1;
            
let dto = new TableRow();
dto.minimalHeight = 30;

const result = await api.updateTableRow("MyPresentation.pptx", dto, slideIndex, shapeIndex, rowIndex);
            
console.log("The new row's minimal height: " + (result.body as model.TableRow).minimalHeight);
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

dto := slidescloud.NewTableRow()
dto.MinimalHeight = 30

result, _, e := api.UpdateTableRow(fileName, dto, slideIndex, shapeIndex, rowIndex, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("The new row's minimal height: %v", result.GetMinimalHeight())
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

my $dto = AsposeSlidesCloud::Object::TableRow->new();
$dto->{minimal_height} = 30;

my %params = (
'name' => "MyPresentation.pptx", 
'folder' => "TempSlidesSDK", 
'slide_index' => 9,
'shape_index' => 1,
'row_index' => 1,
'dto' => $dto);

my $response = $api->update_table_row(%params);
print "The new row's minimal height: $response->{minimal_height} \n"
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)