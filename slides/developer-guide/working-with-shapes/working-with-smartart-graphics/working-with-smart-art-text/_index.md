---
title: "Working With SmartArt Text"
type: docs
url: /working-with-smart-art-text/
weight: 70
---
## **Introduction**
You can manage text within a SmartArt node the same way as it works for sub-shapes. Instead of the path to the sub-shape, the path to the sub-node must be specified.

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs|GET|Read shape paragraphs info| [GetSubshapeParagraphs](https://apireference.aspose.cloud/slides/#/Shapes/GetSubshapeParagraphs)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs|POST|Creates new paragraph|[CreateSubshapeParagraph](https://apireference.aspose.cloud/slides/#/Shapes/CreateSubshapeParagraph)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs|DELETE|Remove a range of paragraps|[DeleteSubshapeParagraphs](https://apireference.aspose.cloud/slides/#/Shapes/DeleteSubshapeParagraphs)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs/{paragraphIndex}|GET|Read shape paragraph info|[GetSubshapeParagraph](https://apireference.aspose.cloud/slides/#/Shapes/GetSubshapeParagraph)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs/{paragraphIndex}|PUT|Update paragraph properties|[UpdateSubshapeParagraph](https://apireference.aspose.cloud/slides/#/Shapes/UpdateSubshapeParagraph)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs/{paragraphIndex}|DELETE|Remove a paragraph|[DeleteSubshapeParagraph](https://apireference.aspose.cloud/slides/#/Shapes/DeleteSubshapeParagraph)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs/{paragraphIndex}/portions|GET|Read paragraph portions info|[GetSubshapePortions](https://apireference.aspose.cloud/slides/#/Shapes/GetSubshapePortions)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs/{paragraphIndex}/portions|POST|Creates new portion|[CreateSubshapePortion](https://apireference.aspose.cloud/slides/#/Shapes/CreateSubshapePortion)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs/{paragraphIndex}/portions|DELETE| Remove a range of portions|[DeleteSubshapePortions](https://apireference.aspose.cloud/slides/#/Shapes/DeleteSubshapePortions)|
/slides/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|GET|Read paragraph portion info|[GetSubshapePortion](https://apireference.aspose.cloud/slides/#/Shapes/GetSubshapePortion)|
​/slides​/{name}​/slides​/{slideIndex}​/shapes​/{path}​/{shapeIndex}​/paragraphs​/{paragraphIndex}​/portions​/{portionIndex}|PUT|Update portion properties|[UpdateSubshapePortion](https://apireference.aspose.cloud/slides/#/Shapes/UpdateSubshapePortion)|
​/slides​/{name}​/slides​/{slideIndex}​/shapes​/{path}​/{shapeIndex}​/paragraphs​/{paragraphIndex}​/portions​/{portionIndex}|DELETE|Remove a portion|[DeleteSubshapePortion](https://apireference.aspose.cloud/slides/#/Shapes/DeleteSubshapePortion)|
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
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/nodes/1/nodes/1/paragraphs/1/portions/1" -d @"portion.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
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

string targetNodePath = "1/nodes/1/nodes";
int slideIndex = 7;
int nodeIndex = 2;
int paragraphIndex = 1;
int portionIndex = 1;

Portion response = api.UpdateSubshapePortion("MyPresentation.pptx", slideIndex, targetNodePath, nodeIndex, paragraphIndex, portionIndex, portion);

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

String targetNodePath = "1/nodes/1/nodes";
int slideIndex = 7;
int nodeIndex = 2;
int paragraphIndex = 1;
int portionIndex = 1;

Portion response = api.updateSubshapePortion("MyPresentation.pptx", slideIndex, targetNodePath, 2, 1, 1, portion, null, null, null);

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

$targetNodePath = "1/nodes/1/nodes";
$slideIndex = 7;
$response = $api->updateSubshapePortion("MyPresentation.pptx", $slideIndex, $targetNodePath, 2, 1, 1, $portion);
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

target_node_path = "1/nodes/1/nodes"
slide_index = 7
response = api.update_subshape_portion("MyPresentation.pptx", slide_index, target_node_path, 2, 1, 1, portion)
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

const targetNodePath = "1/nodes/1/nodes";
const slideIndex = 7;

const response = await api.updateSubshapePortion("MyPresentation.pptx", slideIndex, targetNodePath, 2, 1, 1, portion);
console.log("The portion with text \"" + response.body.text + "\" has been updated");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

//Code example will be added soon.
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