---
title: "Get a Text Portion"
type: docs
url: /get-a-text-portion-from-a-table-cell/
weight: 20
---
## **Introduction**
Aspose.Slides.Cloud API allows retrieving portion info within table cell paragraph.
## **GetTableCellPortion**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|GET|Returns portion info|[GetTableCellPortion](#)
### **Examples**
**cURL Example**

The code example below shows how to retrieve a table cell portion info.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/1/cells/1/paragraphs/1/portions/{portionIndex}" -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}
```sh

Code: 200
Returns portion info.

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
int portionIndex = 1;

Portion response = api.GetTableCellPortion("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex);
Console.WriteLine("Portion text: " + response.Text);
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
int portionIndex = 1;

Portion response = api.getTableCellPortion("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex, null, null, null);
System.out.println("Portion text: " + response.getText());
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
$paragraphIndex = 1;
$portionIndex = 1;

$result = $api->getTableCellPortion("MyPresentation.pptx", $slideIndex, $shapeIndex, $rowIndex, $cellIndex, $paragraphIndex, $portionIndex);
print("Portion text: " . $result->getText());
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
portion_index = 1   

result = api.get_table_cell_portion("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index, paragraph_index, portion_index)
print "Portion text: " + result.text

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
portion_index = 1

response = api.get_table_cell_portion("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index, paragraph_index, portion_index)
print(f"Portion text: {response.text}")
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
let portionIndex = 1;

const result = await api.getTableCellPortion("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex);  
console.log("Portion text:" + result.body.text);
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
var portionIndex int32 = 1

result, _, e := api.SlidesApi.GetTableCellPortion(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Portion text: %v", result.GetText())
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
'cell_index' => 1,
'paragraph_index' => 1,
'portion_index' => 1);

my $response = $api->get_table_cell_portion(%params);
print "Portion text: $response->{text} \n";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)