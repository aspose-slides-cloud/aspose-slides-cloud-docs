---
title: "Set a Chart Wall"
type: docs
url: /set-a-chart-wall/
weight: 70
---
## **Introduction**
Aspose.Slides Cloud API allows setting wall properties of a 3D chart.
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/backWall|PUT|Updates back wall properties|[SetChartWall]()|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/sideWall|PUT|Updates side wall properties|[SetChartWall]()|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/floor|PUT|Updates properties of the chart floor|[SetChartWall]()|
### **cURL Example**

The code example below shows how to update the color of the back wall of the chart.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Update back wall of the 3D chart**
```sh
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/8/shapes/2/backWall" -d @"wall.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
```

wall.json
```json
{
    "FillFormat":{
        "Type": "Solid",
        "Color": "#77CEF9"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns chart wall info.

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

int slideIndex = 8;
int shapeIndex = 2;

ChartWall wallDto = new ChartWall();
wallDto.FillFormat = new SolidFill() { Color = "#77CEF9" };
ChartWall response = api.SetChartWall("MyPresentation.pptx", slideIndex, shapeIndex,
                ChartWallType.BackWall, wallDto);

Console.WriteLine("The color of the back wall has been updated.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 8;
int shapeIndex = 2;

ChartWall wall = new ChartWall();
SolidFill fillFormat = new SolidFill();
fillFormat.setColor("#77CEF9");
wall.setFillFormat(fillFormat);

ChartWall response = api.setChartWall("MyPresentation.pptx", slideIndex, shapeIndex, ChartWallType.BACKWALL , wall, null, null, null);

System.out.println("The color of the back wall has been updated.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ChartWall;
use Aspose\Slides\Cloud\Sdk\Model\SolidFill;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 8;
$shapeIndex = 2;

$wall = new ChartWall();
$fillFormat = new SolidFill();
$fillFormat->setColor("#77CEF9"); 
$wall->setFillFormat($fillFormat);

$result = $api->setChartWall("MyPresentation.pptx", $slideIndex, $shapeIndex, "BackWall", $wall);

print("The color of the back wall has been updated.");
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
from asposeslidescloud.models.chart_wall import ChartWall
from asposeslidescloud.models.solid_fill import SolidFill

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

slide_index = 8
shape_index = 2

wall = ChartWall()
fill_format = SolidFill()
fill_format.color = "#77CEF9"
wall.fill_format = fill_format

response = api.set_chart_wall("MyPresentation.pptx", slide_index, shape_index, "Backwall", wall)

print("The color of the back wall has been updated.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const slideIndex = 8;
const shapeIndex = 2;

const fillFormat = new CloudSdk.SolidFill();
fillFormat.color = "#77CEF9";
const wall = new CloudSdk.ChartWall();
wall.fillFormat = fillFormat;

let result = await api.setChartWall("MyPresentation.pptx", slideIndex, shapeIndex, CloudSdk.ChartWallType.BackWall, wall);
            
console.log("The color of the back wall has been updated.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

var slideIndex int32 = 8
var shapeIndex int32 = 2

fillFormat := asposeslidescloud.NewSolidFill()
fillFormat.Color = "#77CEF9"
wall := asposeslidescloud.NewChartWall()
wall.FillFormat = fillFormat

_, _, e := api.SlidesApi.SetChartWall("MyPresentation.pptx", slideIndex, shapeIndex, "BackWall", wall, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}            
fmt.Printf("The color of the back wall has been updated.")
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

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