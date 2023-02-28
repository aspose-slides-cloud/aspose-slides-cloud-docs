---
title: "Download Shape From a Data Transfer Object"
type: docs
url: /download-shape-from-a-data-transfer-object/
weight: 180
---
Aspose.Slides.Cloud RestAPI allows you to create a shape from a data transfer object and get an image of that shape.
The shape can be a chart, a table, a SmartArt figure or any other shape type supported by PowerPoint.
You don't have to explicitly create a presentation to perform this action.

## **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/shape/{format}|POST|Creates the shape from the DTO and returns the result in the specified format.|[DownloadShapeFromDto]()|

### **Examples**
**cURL Example**

The code examples below show how to generate an image from the shape model.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl  -v "https://api.aspose.cloud/v3.0/slides/shape/png" -d @"shape.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token] -o shape.png

```
shape.json file:
```javascript
{
    shapeType: "Rectangle",
    width: 400,
    height: 200,
    text: "Shape text"
}
```
{{< /tab >}}
{{< tab tabNum="2" >}}

```sh

File data

```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**
{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}
```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
var dto = new Shape
{
    ShapeType = GeometryShape.ShapeTypeEnum.Rectangle,
    Width = 400,
    Height = 200,
    Text = "New shape"
};
using Stream stream = api.DownloadShapeFromDto(ShapeExportFormat.Png, dto);
// Save the PNG document to a file.
using var pngStream = File.Create("output.png");
responseStream.CopyTo(pngStream);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java

SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Shape dto = new Shape();
dto.setShapeType(GeometryShape.ShapeTypeEnum.RECTANGLE);
dto.setWidth(400.0);
dto.setHeight(200.0);
dto.setText("New shape");
File result = api.downloadShapeFromDto(ShapeExportFormat.PNG, dto);
System.out.println("The PNG file was saved to " + result.getPath());

```
{{< /tab >}}
{{< tab tabNum="3" >}}
```php
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Api\Shape;
$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$dto = new Shape();
$dto->setShapeType("Rectangle");
$dto->setWidth(400);
$dto->setHeight(200);
$dto->setText("Shape text");

$api = new SlidesApi(null, $config);

$result = $api->downloadShapeFromDto("png", $dto);
print("The PNG file was saved to " . $result->getPathname());
```
{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

shape = AsposeSlidesCloud::Shape.new
shape.shape_type = "Rectangle"
shape.width = 400
shape.height = 200
shape.text = "Shape text"

api = AsposeSlidesCloud::SlidesApi.new(configuration)
response = AsposeSlidesCloud::SpecUtils.api.download_shape_from_dto(AsposeSlidesCloud::ShapeExportFormat::PNG, shape)
# Save the PNG document to a file.
File.binwrite("output.png", response)
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

dto = Shape()
dto.width = 400
dto.height = 200
dto.shape_type = "Rectangle"
dto.text = "Shape text"

with open("output.png", "w") as f:
    result = api.download_shape_from_dto("png", dto)
print("The PNG file was saved to " + result)
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');

const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
const dto = new model.Shape();
dto.shapeType = ShapeTypeEnum.Rectangle;
dto.width = 400;
dto.height = 200;
dto.text = "Shape text";

const response = await api.downloadShapeFromDto(ShapeExportFormat.Png, dto);
fs.writeFile("shape.png", response.body, (error) => {
                if (error) throw error
            });
```
{{< /tab >}}
{{< tab tabNum="7" >}}
```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

shape := slidescloud.NewShape()
shape.SetShapeType("Rectangle")
shape.SetWidth(400)
shape.SetHeight(200)
shape.SetText("Shape text")

result, _, e := api.DownloadShapeFromDto("png", shape)
if e != nil {
    t.Errorf("Error: %v.", e)
    return
}
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

my $dto = AsposeSlidesCloud::Object::Shape->new();
$dto->{shape_type} = "Rectangle";
$dto->{width} = 400;
$dto->{height} = 200;
my %params = ('format' => "png", 'dto' => $dto);
my $response = $api->download_shape_from_dto(%params);
```

{{< /tab >}}
{{< tab tabNum="10" >}}

{{< /tab >}}
{{< /tabs >}}