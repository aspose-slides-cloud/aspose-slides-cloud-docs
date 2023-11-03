---
title: "Get Paragraphs"
type: docs
url: /get-paragraphs-from-a-table-cell/
weight: 10
---
## **Introduction**
Aspose.Slides.Cloud API allows retrieving table cell paragraphs info.
## **GetTableCellParagraphs**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/paragraphs|GET|Returns paragraph info|[GetTableCellParagraphs](#)
### **Examples**
**cURL Example**

The code example below shows how to retrieve table cell paragraphs info. Assume that the target cell is located in the first row at index 1.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/1/cells/1/paragraphs" -H "Authorization: Bearer [Access Token]"
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
Paragraphs response = api.GetTableCellParagraphs("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex);

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

Paragraphs response = api.getTableCellParagraphs("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, null, null, null);
System.out.println("Paragraphs count: " + response.getParagraphLinks().size());
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

$result = $api->getTableCellParagraphs("MyPresentation.pptx", $slideIndex, $shapeIndex, $rowIndex, $cellIndex);

print("Paragraphs count: " . count($result->getParagraphLinks()));
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

result = api.get_table_cell_paragraphs("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index)
puts "Paragraphs count: #{result.paragraph_links.length}"
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

response = api.get_table_cell_paragraphs("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index)

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

const result = await api.getTableCellParagraphs("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex);
            
console.log("Paragraphs count: " + result.body.paragraphLinks.length);
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

result, _, e := api.SlidesApi.GetTableCellParagraphs(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, "", "", "")

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
'slide_index' => 9,
'shape_index' => 1,
'row_index' => 1,
'cell_index' => 1);

my $response = $api->get_table_cell_paragraphs(%params);
print "Paragraphs count: scalar @{$response->{paragraph_links}} \n";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
