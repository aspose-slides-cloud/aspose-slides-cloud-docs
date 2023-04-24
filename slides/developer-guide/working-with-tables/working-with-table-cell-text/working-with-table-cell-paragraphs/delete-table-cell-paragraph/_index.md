---
title: "Delete Table Cell Paragraph"
type: docs
url: /delete-table-cell-paragraph/
weight: 50
---
## **Introduction**
Aspose.Slides.Cloud API allows deleting text paragraphs within table cell.
## **DeleteTableCellParagraph**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/paragraphs/{paragraphIndex}|DELETE|Returns paragraphs info|[DeleteTableCellParagraph](#)
### **Examples**
**cURL Example**

The code example below shows how to delete the first table cell paragraph in the first cell of the first row.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/1/cells/1/paragraphs/1" -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}
```sh

Code: 200
Returns paragraphs info.

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
int paragraphIndex = 1;

Paragraphs response = api.DeleteTableCellParagraph("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex);

Console.WriteLine("Paragraphs count: " + response.ParagraphLinks.Count);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
int rowIndex = 1;
int cellIndex = 1;
int paragraphIndex = 1;

Paragraphs response = api.deleteTableCellParagraph("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, null, null, null);
System.out.println("Paragraphs count: " + response.getParagraphLinks().size());
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Paragraphs;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 9;
$shapeIndex = 1;
$rowIndex = 1;
$cellIndex = 1;
$paragraphIndex = 1;

$result = $api->deleteTableCellParagraph("MyPresentation.pptx", $slideIndex, $shapeIndex, $rowIndex, $cellIndex, $paragraphIndex);

print("Paragraphs count: " . count($response->getParagraphLinks()));
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
paragraph_index = 1

result = api.delete_table_cell_paragraph("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index, paragraph_index)
print "Paragraphs count: " + result.paragraph_links.length

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
cell_index = 1
paragraph_index = 1

response = api.delete_table_cell_paragraph("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index, paragraph_index)

print(f"Paragraphs count: {len(response.paragraph_links)}")
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
let paragraphIndex = 1;

const result = await api.deleteTableCellParagraph("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex);
            
console.log("Paragraphs count: " + (result.body as model.Paragraphs).paragraphLinks.length);
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
var paragraphIndex int32 = 1

result, _, e := api.DeleteTableCellParagraph(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Paragraphs count: %v", len(result.GetParagraphLinks()))
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
'folder' => "TempSlidesSDK", 
'slide_index' => 9,
'shape_index' => 1,
'row_index' => 1,
'cell_index' => 1,
'paragraph_index' => 1);

my $response = $api->delete_table_cell_paragraph(%params);
print "Paragraphs count: scalar @{$response->{paragraph_links}} \n"
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)