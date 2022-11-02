---
title: "Update Chart Datapoint"
type: docs
url: /update-chart-data-point/
weight: 30
---

## **Introduction**
Aspose.Slides Cloud allows you to update chart datapoints from a PowerPoint Presentation. 
### **API Information**
Aspose.Slides Cloud provides resources to achieve this. You can update a chart categories in the Presentation

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/series/{seriesIndex}/dataPoints/{dataPointIndex}|PUT|Update the chart datapoint|[UpdateDataPoint](https://apireference.aspose.cloud/slides/#/Chart/UpdateDataPoint)|
### **cURL Example**
{{% alert color="primary" %}}

The referenced shape must be a chart, otherwise the operation will fail.

{{% /alert %}}

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/shapes/2/series/2/dataPoints/2" -d @"datapoint.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```

datapoint.json file:
```json
{
    "xValue": 25,
    "yValue": 9,
    "fillFormat {
        "type": "Solid",
        "color": "#77CEF9"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Body: Chart JSON

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
ScatterChartDataPoint dto = new ScatterChartDataPoint();
dto.XValue = 25;
dto.YValue = 9;
dto.FillFormat = new SolidFill(){ Color = "#77CEF9" };
Chart chart = api.UpdateChartDataPoint("myPresentaion.pptx", 3, 2, 1, 3, dto);
Console.WriteLine(((ScatterSeries)chart.Series[0]).DataPoints.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
ScatterChartDataPoint dto = new ScatterChartDataPoint();
dto.setXvalue(25.0);
dto.setYvalue(9.0);
SolidFill fillFormat = new SolidFill();
fillFormat.setColor("#77CEF9");
dto.setFillFormat(fillFormat);

Chart chart = (Chart)api.updateChartDataPoint("MyPresentation.pptx", 3, 2, 1, 3, dto, null, null, null);
System.out.println(((ScatterSeries)chart.getSeries().get(0)).getDataPoints().size());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ScatterChartDataPoint;
use Aspose\Slides\Cloud\Sdk\Model\SolidFill;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new ScatterChartDataPoint();
$dto->setXValue(25);
$dto->setYValue(9);
$fillFormat = new SolidFill();
$fillFormat->setColor("#77CEF9");
$dto->setFillFormat($fillFormat);
        
$result = $api->UpdateChartDataPoint("MyPresentation.pptx", 3, 2, 1, 3, $dto);
print(count($result->getSeries()[0]->getDataPoints()));
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.scatter_chart_data_point import ScatterChartDataPoint
from asposeslidescloud.models.solid_fill import SolidFill

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = ScatterChartDataPoint()
fill_format = SolidFill()
fill_format.color = "#77CEF9"
dto.fill_format = fill_format
dto.x_value = 25
dto.x_value = 9
result = api.update_chart_data_point("MyPresentation.pptx", 3, 2, 1, 3, dto)
print(len(result.series[0].data_points))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new CloudSdk.ScatterChartDataPoint();
dto.xValue = 25;
dto.yValue = 9;
const fillFormat = new CloudSdk.SolidFill();
fillFormat.color = "#77CEF9";
dto.fillFormat = fillFormat;
api.updateChartDataPoint("MyPresentation.pptx", 3, 2, 1, 3, dto).then((result) => {
    console.log(result.body.series[0].dataPoints.length);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

dto := NewScatterChartDataPoint()
dto.XValue = 25
dto.YValue = 9
fillFormat := slidescloud.NewSolidFill()
fillFormat.SetColor("#77CEF9")
dto.SetFillFormat(fillFormat)
result, _, e := c.SlidesApi.UpdateChartDataPoint("MyPresentation.pptx", 3, 2, 1, dto, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v series.", len(result.(IChart).getSeries()[0].(IScatterSeries).getDataPoints()))
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
