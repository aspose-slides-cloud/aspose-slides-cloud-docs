---
title: "Working with SmartArt Text"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- SmartArt
- text
- SmartArt text
type: docs
url: /working-with-smart-art-text/
weight: 40
---
## **Introduction**
You can manage text within a SmartArt node the same way as it works for sub-shapes. Instead of the path to the sub-shape, the path to the sub-node must be specified. The sub-node path is a string that contains node index (e.g., "1") or a path in case of more than one level of grouping( e.g. "1/nodes/1").

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs|GET|Read shape paragraphs info| [GetParagraphs](https://apireference.aspose.cloud/slides/#/Shapes/GetParagraphs)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs|POST|Creates new paragraph|[CreateParagraph](https://apireference.aspose.cloud/slides/#/Shapes/CreateParagraph)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs|DELETE|Remove a range of paragraps|[DeleteParagraphs](https://apireference.aspose.cloud/slides/#/Shapes/DeleteParagraphs)|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|GET|Read shape paragraph info|[GetParagraph](https://apireference.aspose.cloud/slides/#/Shapes/GetParagraph)|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|PUT|Update paragraph properties|[UpdateParagraph](https://apireference.aspose.cloud/slides/#/Shapes/UpdateParagraph)|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|DELETE|Remove a paragraph|[DeleteParagraph](https://apireference.aspose.cloud/slides/#/Shapes/DeleteParagraph)|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|GET|Read paragraph portions info|[GetPortions](https://apireference.aspose.cloud/slides/#/Shapes/GetPortions)|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|POST|Creates new portion|[CreatePortion](https://apireference.aspose.cloud/slides/#/Shapes/CreatePortion)|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|DELETE| Remove a range of portions|[DeletePortions](https://apireference.aspose.cloud/slides/#/Shapes/DeletePortions)|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|GET|Read paragraph portion info|[GetPortion](https://apireference.aspose.cloud/slides/#/Shapes/GetPortion)|
​/slides​/{name}​/slides​/{slideIndex}​/shapes​/{shapeIndex}​/paragraphs​/{paragraphIndex}​/portions​/{portionIndex}|PUT|Update portion properties|[UpdatePortion](https://apireference.aspose.cloud/slides/#/Shapes/UpdatePortion)|
​/slides​/{name}​/slides​/{slideIndex}​/shapes​/{shapeIndex}​/paragraphs​/{paragraphIndex}​/portions​/{portionIndex}|DELETE|Remove a portion|[DeletePortion](https://apireference.aspose.cloud/slides/#/Shapes/DeletePortion)|
### **cURL Example**
The code example below shows how to update a text portion in an existing SmartArt object. 
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Update the portion**
```sh
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs/1/portions/1?subshape=1/nodes/1" -d @"portion.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
```

portion.json
```json
{
	"Text":"New Shape Text",
	"FontBold":true,
	"Spacing":3,
	"FontColor":"#FFFF0000",
	"FontHeight":24
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns portion info.

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Portion portion = new Portion()
{
    Text = "New text",
    FontHeight = 24,
    FontBold = Portion.FontBoldEnum.True,
    Spacing = 3,
    FillFormat = new SolidFill() { Color = "#FFFFFF00" }
};

string subNodePath = "1/nodes/2";
int slideIndex = 7;
int nodeIndex = 1;
int paragraphIndex = 1;
int portionIndex = 1;

Portion response = api.UpdatePortion("MyPresentation.pptx", slideIndex, nodeIndex, paragraphIndex, portionIndex, portion, subShape: subNodePath);

Console.WriteLine($"The portion with text \"{response.Text}\" has been updated");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Portion portion = new Portion();
portion.setText("New text");
portion.setFontHeight(24.0);
portion.setFontBold(Portion.FontBoldEnum.TRUE);
portion.spacing(3.0);
SolidFill fillFormat = new SolidFill();
fillFormat.setColor("#FFFFFF00");
portion.setFillFormat(fillFormat);

String subNodePath = "1/nodes/2";
int slideIndex = 7;
int nodeIndex = 1;
int paragraphIndex = 1;
int portionIndex = 1;

Portion response = api.updatePortion("MyPresentation.pptx", slideIndex, 1, 1, 1, portion, null, null, null, subNodePath);

System.out.println("The portion with text \"" + response.getText() + "\" has been updated");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Portion;
use Aspose\Slides\Cloud\Sdk\Model\SolidFill;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $configuration);

$portion = new Portion();
$portion->setText("New text");
$portion->setFontHeight(24);
$portion->setFontBold("True");
$portion->setSpacing(3);
$fillFormat = new SolidFill();
$fillFormat->setColor("#FFFFFF00");
$portion->setFillFormat($fillFormat);

$subNodePath = "1/nodes/2";
$slideIndex = 7;
$response = $api->updatePortion("MyPresentation.pptx", $slideIndex, 1, 1, 1, $portion, null, null, null, $subNodePath);
print("The portion with text \"" . $response->getText() . "\" has been updated");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

#Code example will be added soon.
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.portion import Portion
from asposeslidescloud.models.solid_fill import SolidFill

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

portion = Portion()
portion.text = "New text"
portion.font_height = 24
portion.font_bold = "True"
portion.spacing = 3
fill_format = SolidFill()
fill_format.color = "#FFFFFF00"
portion.fill_format = fill_format

sub_node = "1/nodes/2"
slide_index = 7
response = api.update_portion("MyPresentation.pptx", slide_index, 1, 1, 1, portion, None, None, None, sub_node)
print("The portion with text \"" + response.text + "\" has been updated")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const portion = new CloudSdk.Portion();
portion.text = "New text";
portion.fontHeight = 24;
portion.fontBold = CloudSdk.Portion.FontBoldEnum.True;
portion.spacing = 3;
const fillFormat = new CloudSdk.SolidFill();
fillFormat.color = "#FFFFFF00";
portion.fillFormat = fillFormat;

const subNodePath = "1/nodes/2";
const slideIndex = 7;

const response = await api.updatePortion("MyPresentation.pptx", slideIndex, 1, 1, 1, portion, null, null, null, subNodePath);
console.log("The portion with text \"" + response.body.text + "\" has been updated");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

portion := asposeslidescloud.NewPortion()
portion.Text = "New text"
portion.FontHeight = 24
portion.FontBold = "True"
portion.Spacing = 3
fillFormat := asposeslidescloud.NewSolidFill()
fillFormat.Color = "#FFFFFF00"
portion.FillFormat = fillFormat

subNodePath := "1/nodes/2"
var slideIndex int32 = 7

response, _, e := api.SlidesApi.UpdatePortion("MyPresentation.pptx", slideIndex, 1, 1, 1, portion, "", "", "", subNodePath)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}            
fmt.Printf("The portion with text \"%v\" has been updated", response.GetText())
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

#Code example will be added soon.
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
