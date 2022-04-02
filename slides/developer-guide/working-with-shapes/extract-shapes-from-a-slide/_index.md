---
title: "Extract Shapes from a Slide"
type: docs
url: /extract-shapes-from-a-slide/
weight: 10
---

## **Introduction**
This article shows how to retrieve all shapes or shapes of the specified type from the slide.
### **API Information**
|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{slideIndex}/shapes|GET|Read slide shapes info|[GetShapes](https://apireference.aspose.cloud/slides/#/Shapes/GetShapes)|

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Header**

```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```
**Get all shapes**
```sh

curl -v "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes" -d "" -H "Authorization: Bearer MyAuthToken"

```
**Get shapes of the specified type**
```sh

curl -v "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?shapeType=chart" -d "" -H "Authorization: Bearer MyAuthToken"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

The shape info.

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Shapes allShapes = api.GetShapes("MyPresentation.pptx", 1);
Shapes charts = api.GetShapes("MyPresentation.pptx", 1, shapeType: ShapeType.Chart);
Console.WriteLine($"The slide contains {allShapes.ShapesLinks.Count} shapes, including {charts.ShapesLinks.Count} charts");
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Shapes allShapes = api.getShapes("MyPresentation.pptx", 1);
Shapes charts = api.getShapes("MyPresentation.pptx", 1, null, null, null, ShapeType.Chart);
System.out.println("The slide contains " + allShapes.getShapesLinks().size() + " shapes, including " + charts.getShapesLinks().size() + " charts");
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ShapeType;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$allShapes = $api->GetShapes("MyPresentation.pptx", 1);
$charts = $api->GetShapes("MyPresentation.pptx", 1, null, null, null, ShapeType::CHART);
print("The slide contains " . count($allShapes->getShapesLinks()) . " shapes, including " . count($charts->getShapesLinks()) . " charts");
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

all_shapes = api.get_shapes("MyPresentation.pptx", 1)
charts = api.get_shapes("MyPresentation.pptx", 1, nil, nil, nil, AsposeSlidesCloud::ShapeType::CHART)
p("The slide contains " + all_shapes.shapes_links.length + " shapes, including " + charts.shapes_links.length + " charts")
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.shape_type import ShapeType

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

all_shapes = api.get_shapes("MyPresentation.pptx", 1)
charts = api.get_shapes("MyPresentation.pptx", 1, None, None, None, ShapeType.CHART)
print("The slide contains " + str(all_shapes.shapes_links.length) + " shapes, including " + str(charts.shapes_links.length) + " charts")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

api.getShapes("MyPresentation.pptx", 1).then((allShapes) => {
    api.getShapes("MyPresentation.pptx", 1, null, null, null, "Chart").then((charts) => {
        console.log("The slide contains " + allShapes.body.shapesLinks.length + " shapes, including " + charts.body.shapesLinks.length + " charts");
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %params = ('name' => 'MyPresentation.pptx', 'slide_index' => 1);
my $all_shapes = $api->get_shapes(%params);

$params{shape_type} = 'Chart';
my $charts = $api->get_shapes(%params);

print "The slide contains " . (scalar @{$all_shapes->{shapes_links}}) . " shapes, including " . (scalar @{$charts->{shapes_links}}) . " charts";
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

allShapes, _, e := c.SlidesApi.GetShapes("MyPresentation.pptx", 1, "", "", "", nil)
if e != nil {
    fmt.Printf("Error: %v.", e)
}

var shapeType string = "Chart"
charts, _, e := c.SlidesApi.GetShapes("MyPresentation.pptx", 1, "", "", "", &shapeType)
if e != nil {
    fmt.Printf("Error: %v.", e)
}
fmt.Printf("The slide contains %v shapes, including %v charts", len(allShapes.getShapesLinks()), len(charts.getShapesLinks()))
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}