---
title: "Setting chart axis"
type: docs
url: /setting-chart-axis/
weight: 50
---
## **Introduction**
Aspose.Slides Cloud API allows setting chart axis properties.
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/horizontalAxis|PUT|Updates horizontal axis properties|[SetChartAxis]()|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/verticalAxis|PUT|Updates vertical axis properties|[SetChartAxis]()|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/secondaryHorizontalAxis|PUT|Updates secondary horizontal axis properties|[SetChartAxis]()|
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/secondaryVerticalAxis|PUT|Updates secondary vertical axis properties|[SetChartAxis]()|
### **cURL Example**

The code example below shows how to update some properties of the horizontal axis.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Update Vertical Axis**
```sh
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/shapes/1/verticalAxis" -d @"axis.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
```

portion.json
```json
{
    "HasTitle":true,
    "IsAutomaticMaxValue":false,
    "MaxValue":10
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns chart axis info.

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

Axis axisDto = new Axis();
axisDto.HasTitle = true;
axisDto.IsAutomaticMaxValue = false;
axisDto.MaxValue = 10;

Axis response = api.SetChartAxis("MyPresentation.pptx", slideIndex, shapeIndex, AxisType.VerticalAxis, axisDto);

Console.WriteLine($"The maximum value on the axis equals {response.MaxValue}.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 3;
int shapeIndex = 1;

Axis axis = new Axis();
axis.setHasTitle(true);
axis.setIsAutomaticMaxValue(false);
axis.setMaxValue(10.0);

Axis response = api.setChartAxis("MyPresentation.pptx", slideIndex, shapeIndex, AxisType.VERTICALAXIS, axis, null, null, null);

System.out.println("The maximum value on the axis equals" + response.getMaxValue());
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Axis;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 3;
$shapeIndex = 1;

$axis = new Axis();
$axis->setHasTitle(true);
$axis->setIsAutomaticMaxValue(false);
$axis->setMaxValue(10);

$result = $api->setChartAxis("MyPresentation.pptx", $slideIndex, $shapeIndex, "VerticalAxis", $axis);

print("The maximum value on the axis equals \"" . $result->getMaxValue() . "\".");
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
from asposeslidescloud.models.axis import Axis

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

slide_index = 3
shape_index = 1

axis = Axis()
axis.has_title = True
axis.is_automatic_max_value = False
axis.max_value = 10

response = api.set_chart_axis("MyPresentation.pptx", slide_index, shape_index, "VerticalAxis", axis)

print(f"The maximum value on the axis equals \"{ response.max_value }\".")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const slideIndex = 3;
const shapeIndex = 1;

const axis = new CloudSdk.Axis();
axis.hasTitle = true;
axis.isAutomaticMaxValue = false;
axis.maxValue = 10;
            
let result = await api.setChartAxis("MyPresentation.pptx", slideIndex, shapeIndex, CloudSdk.AxisType.VerticalAxis, axis)
            
console.log("The maximum value on the axis equals \"" + result.body.maxValue + "\".");
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

axis := asposeslidescloud.NewAxis()
axis.HasTitle = true
axis.IsAutomaticMaxValue = false
axis.MaxValue = 10

result, _, e := api.SlidesApi.SetChartAxis("MyPresentation.pptx", slideIndex, shapeIndex, "VerticalAxis", axis, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The maximum value on the axis equals \"%v\".", result.GetMaxValue())
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