---
title: "Delete Table Row"
type: docs
url: /delete-table-row/
weight: 30
---
## **Introduction**
Aspose.Slides.Cloud API allows deleting table rows. If the "withAttachedRows" parameter is set, rows that have common merged cells with the target row will be deleted either. 
## **DeleteTableRow**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}|DELETE|Returns table info|[DeleteTableRow](#)
### **Examples**
**cURL Example**

Assume that we have a table with four rows and intend to delete the second row. The second and the third row have a common merged cell.  Since the "withAttachedRows" parameter is set, the third row will be removed as well.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/2" -H "Authorization: Bearer [Access Token]"
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
int rowIndex = 2;
bool withAttachedRows = true;
Table response = api.DeleteTableRow("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, withAttachedRows);

Console.WriteLine("Table rows count: " + response.Rows.Count);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
int rowIndex = 2;
Boolean withAttachedRows = true;

Table response = api.deleteTableRow("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, withAttachedRows, null, null, null);
System.out.println("Table rows count: " + response.getRows().size());
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Table;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 9;
$shapeIndex = 1;
$rowIndex = 2;
$withAttachedRows = true;
        

$result = $api->deleteTableRow("MyPresentation.pptx", $slideIndex, $shapeIndex, $rowIndex, $withAttachedRows);

print("Table rows count: " . count($response->getRows()));
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
with_attached_rows = true

result = api.delete_table_row("MyPresentation.pptx", slide_index, shape_index, row_index, with_attached_rows)
print "Table rows count: " + result.rows.length

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
with_attached_table_rows = True

response = api.delete_table_row("MyPresentation.pptx", slide_index, shape_index, row_index, with_attached_table_rows)
print(f"Table rows count: " {len(response.rows)}")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let slideIndex = 9;
let shapeIndex = 1;
let rowIndex = 2;
let withAttachedRows = true;

const result = await api.deleteTableRow("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, withAttachedRows);         
console.log("Table rows count: " + (result.body as model.Table).rows.length;
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
var withAttachedRows bool = true

result, _, e := api.DeleteTableRow(fileName, slideIndex, shapeIndex, rowIndex, &withAttachedRows, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Table rows count: %v", len(result.GetRows()))
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Table;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %params = (
'name' => "MyPresentation.pptx", 
'folder' => "TempSlidesSDK", 
'slide_index' => 9,
'shape_index' => 1,
'row_index' => 2,
'with_attached_rows' => 'true');

my $response = $api->delete_table_row(%params);
print "Table rows count: scalar @{$response->{rows}} \n"
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
