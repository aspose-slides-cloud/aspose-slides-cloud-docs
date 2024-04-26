---
title: "Create a Paragraph"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- table
- cell
- table cell
- text
- paragraph
- create a paragraph
- add a paragraph
type: docs
url: /create-a-paragraph-in-a-table-cell/
weight: 30
---
## **Introduction**
Aspose.Slides.Cloud API allows creating text paragraphs within a table cell.
## **CreateTableCellParagraph**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/paragraphs|POST|Returns paragraph info|[CreateTableCellParagraph](#)
### **Examples**
**cURL Example**

The code example below shows how to create a table cell paragraph with two text portions.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/1/cells/1/paragraphs" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json" -F @"paragraph.json" 
```

paragraph.json
```json
{
    "portionList": [
        {
            "text":"Portion 1"
        },
        {
            "text":"Portion 2"
        }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}
```sh

Code: 200
Returns paragraph info.

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
Paragraph dto = new Paragraph()
{
    PortionList = new List<Portion>
    {
        new Portion {Text = "Portion 1"},
        new Portion {Text = "Portion 2"},
    }
};

Paragraph response = api.CreateTableCellParagraph("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, dto);

Console.WriteLine("The paragraph has been created.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 9;
int shapeIndex = 1;
int rowIndex = 1;
int cellIndex = 1;

Portion portion0 = new Portion();
portion0.setText("Portion 1");
Portion portion1 = new Portion();
portion1.setText("Portion 2");
Paragraph dto = new Paragraph();
dto.setPortionList(new ArrayList(Arrays.asList(portion0, portion1)));

Paragraph response = api.createTableCellParagraph("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, dto, null, null, null);
System.out.println("The paragraph has been created.");
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Paragraph;
use Aspose\Slides\Cloud\Sdk\Model\Portion;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 9;
$shapeIndex = 1;
$rowIndex = 1;
$cellIndex = 1;
$portion0 = new Portion();
$portion0->setText("Portion 1");
$portion1 = new Portion();
$portion1->setText("Portion 2");
$dto = new Paragraph();
$dto->setPortionList([$portion0, $portion1]);

$result = $api->createTableCellParagraph("MyPresentation.pptx", $slideIndex, $shapeIndex, $rowIndex, $cellIndex, $dto);

print("The paragraph has been created.");
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
            
portion0 = AsposeSlidesCloud::Portion.new
portion0.text = "Portion 1"
portion1 = AsposeSlidesCloud::Portion.new
portion1.text = "Portion 2"
dto = AsposeSlidesCloud::Paragraph.new
dto.portion_list = [portion0, portion1]

result = api.create_table_cell_paragraph("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index, dto)
print "The paragraph has been created."

```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.paragraph import Paragraph
from asposeslidescloud.models.portion import Portion

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

slide_index = 9
shape_index = 1
row_index = 1
cell_index = 1
portion_0 = Portion()
portion_0.text = "Portion 1"
portion_1 = Portion()
portion_1.text = "Portion 2"
dto = Paragraph()
dto.portion_list = [portion_0, portion_1]

response = api.create_table_cell_paragraph("MyPresentation.pptx", slide_index, shape_index, row_index, cell_index, dto)

print(f"The paragraph has been created.")
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
            
let portion0 = new CloudSdk.Portion();
portion0.text = "Portion 1";
let portion1 = new CloudSdk.Portion();
portion1.text = "Portion 2";
            
let dto = new CloudSdk.Paragraph();
dto.portionList = [portion0, portion1];

const result = await api.createTableCellParagraph("MyPresentation.pptx", slideIndex, shapeIndex, rowIndex, cellIndex, dto);
            
console.log("The paragraph has been created.");
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
portion0 := asposeslidescloud.NewPortion()
portion0.SetText("Portion 1")
portion1 := asposeslidescloud.NewPortion()
portion1.SetText("Portion 2")
dto := asposeslidescloud.NewParagraph()
dto.SetPortionList([]asposeslidescloud.IPortion{portion0, portion1})

result, _, e := api.SlidesApi.CreateTableCellParagraph(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, dto, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("The paragraph has been created: %v.", len(result.GetPortionList()))
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;        
use AsposeSlidesCloud::Object::Portion;
use AsposeSlidesCloud::Object::Paragraph;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $portion0 = AsposeSlidesCloud::Object::Portion->new();
$portion0->{text} = "Portion 1";
my $portion1 = AsposeSlidesCloud::Object::Portion->new();
$portion1->{text} = "Portion 2";
my @portions = ($portion0, $portion1);
my $dto = AsposeSlidesCloud::Object::Paragraph->new();
$dto->{portion_list} = \@portions;

my %params = (
'name' => "MyPresentation.pptx", 
'slide_index' => 9,
'shape_index' => 1,
'row_index' => 1,
'cell_index' => 1,
'dto' => $dto);

my $response = $api->create_table_cell_paragraph(%params);
print "The paragraph has been created. \n";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
