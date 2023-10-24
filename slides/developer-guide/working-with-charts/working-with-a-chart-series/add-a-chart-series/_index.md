---
title: "Add a Chart Series"
type: docs
url: /add-a-chart-series/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud allows you to add a chart series in a PowerPoint presentation. 

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/series|POST|Add the chart series|[CreateChartSeries](https://apireference.aspose.cloud/slides/#/Chart/CreateChartSeries)|
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

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/shapes/2/series" -d @"series.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```

series.json file:
```javascript
{
    "dataPointType": "OneValue",
    "dataPoints": [
        { "value": 5.5 },
        { "value": 76 },
        { "value": 27 }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 201
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
OneValueSeries dto = new OneValueSeries();
dto.DataPoints = new List<OneValueChartDataPoint>();
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 5.5 });
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 76 });
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 27 });
Chart chart = api.CreateChartSeries("myPresentaion.pptx", 3, 1, dto);
Console.WriteLine(chart.Series.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
OneValueSeries dto = new OneValueSeries();
List<OneValueChartDataPoint> dataPoints = new ArrayList<OneValueChartDataPoint>();
OneValueChartDataPoint dataPoint1 = new OneValueChartDataPoint();
dataPoint1.setValue(5.5);
dataPoints.add(dataPoint1);

OneValueChartDataPoint dataPoint2 = new OneValueChartDataPoint();
dataPoint2.setValue(76.0);
dataPoints.add(dataPoint2);

OneValueChartDataPoint dataPoint3 = new OneValueChartDataPoint();
dataPoint3.setValue(27.0);
dataPoints.add(dataPoint3);
dto.setDataPoints(dataPoints);

Chart chart = (Chart)api.createChartSeries("MyPresentation.pptx", 3, 1, dto, null, null, null);
System.out.println(chart.getSeries().size());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\OneValueSeries;
use Aspose\Slides\Cloud\Sdk\Model\OneValueChartDataPoint;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new OneValueSeries();
$dataPoint1 = new OneValueChartDataPoint();
$dataPoint1->setValue(5.5);
$dataPoint2 = new OneValueChartDataPoint();
$dataPoint2->setValue(76);
$dataPoint3 = new OneValueChartDataPoint();
$dataPoint3->setValue(27);
$dto->setDataPoints([$dataPoint1, $dataPoint2, $dataPoint3]);

$result = $api->CreateChartSeries("MyPresentation.pptx", 3, 1, $dto);
print(count($result->getSeries()));
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.one_value_series import OneValueSeries
from asposeslidescloud.models.one_value_chart_data_point import OneValueChartDataPoint

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = OneValueSeries()
data_point1 = OneValueChartDataPoint()
data_point1.value = 5.5
data_point2 = OneValueChartDataPoint()
data_point2.value = 76
data_point3 = OneValueChartDataPoint()
data_point3.value = 27
dto.data_points = [ data_point1, data_point2, data_point3 ]

result = api.create_chart_series("MyPresentation.pptx", 3, 1, dto)
print(len(result.series))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new CloudSdk.OneValueSeries();
dto.dataPoints = [{ value: 20 }, { value: 50 }, { value: 30 }];
api.createChartSeries("MyPresentation.pptx", 3, 1, dto).then((result) => {
    console.log(result.body.series.length);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

dto := asposeslidescloud.NewOneValueSeries()

dataPoint1 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint1.Value = 20

dataPoint2 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint2.Value = 50

dataPoint3 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint3.Value = 30
dto.DataPoints = []asposeslidescloud.IOneValueChartDataPoint { dataPoint1, dataPoint2, dataPoint3 }

result, _, e := api.SlidesApi.CreateChartSeries("MyPresentation.pptx", 3, 1, dto, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v series.", len(result.(asposeslidescloud.IChart).GetSeries()))
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