---
title: "Setting chart legend"
type: docs
url: /setting-chart-legend/
weight: 60
---
## **Introduction**
Aspose.Slides Cloud API allows setting chart legend properties.
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/legend|PUT|Updates chart legend properties|[SetChartLegend]()|
### **cURL Example**

The code example below shows how to update some properties of the chart legend.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Update Vertical Axis**
```sh
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/shapes/1/legend" -d @"legend.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
```

legend.json
```json
{
    "Overlay":true,
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
Returns chart legend info.

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

int slideIndex = 3;
int shapeIndex = 1;

Legend legendDto = new Legend();
legendDto.Overlay = true;
legendDto.FillFormat = new SolidFill()
{
    Color = "#77CEF9"
};

Legend response = api.SetChartLegend("MyPresentation.pptx", slideIndex, shapeIndex, legendDto);

Console.WriteLine("Background color of the chart legend has been changed.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 3;
int shapeIndex = 1;
Legend legend = new Legend();
legend.setOverlay(true);
SolidFill fillFormat = new SolidFill();
fillFormat.setColor("#77CEF9");
legend.setFillFormat(fillFormat);

Legend response = api.setChartLegend("MyPresentation.pptx", slideIndex, shapeIndex, legend, null, null, null);

System.out.println("Background color of the chart legend has been changed.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Legend;
use Aspose\Slides\Cloud\Sdk\Model\SolidFill;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 3;
$shapeIndex = 1;

$legend = new Legend();
$legend->setOverlay(true);
$fillFormat = new SolidFill();
$fillFormat->setColor("#77CEF9"); 
$legend->setFillFormat($fillFormat);

$result = $api->setChartLegend("MyPresentation.pptx", $slideIndex, $shapeIndex, $legend);

print("Background color of the chart legend has been changed.");
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
from asposeslidescloud.models.legend import Legend
from asposeslidescloud.models.solid_fill import SolidFill

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

slide_index = 3
shape_index = 1

legend = Legend()
legend.overlay = True
fill_format = SolidFill()
fill_format.color = "#77CEF9"
legend.fill_format = fill_format
response = api.set_chart_legend("MyPresentation.pptx", slide_index, shape_index, legend)

print("Background color of the chart legend has been changed.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const slideIndex = 3;
const shapeIndex = 1;

const fillFormat = new CloudSdk.SolidFill();
fillFormat.color = "#77CEF9";
const legend = new CloudSdk.Legend();
legend.overlay = true;
legend.fillFormat = fillFormat;

let result = await api.setChartLegend("MyPresentation.pptx", slideIndex, shapeIndex, legend);
            
console.log("Background color of the chart legend has been changed.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

var slideIndex int32 = 3
var shapeIndex int32 = 1

fillFormat := asposeslidescloud.NewSolidFill()
fillFormat.Color = "#77CEF9"
legend := asposeslidescloud.NewLegend()
legend.Overlay = true
legend.FillFormat = fillFormat

_, _, e := api.SlidesApi.SetChartLegend("MyPresentation.pptx", slideIndex, shapeIndex, legend, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}            
fmt.Printf("Background color of the chart legend has been changed.")

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