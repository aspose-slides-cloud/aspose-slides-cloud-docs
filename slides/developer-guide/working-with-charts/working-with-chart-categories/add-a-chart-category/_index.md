---
title: "Add a Chart Category"
type: docs
url: /add-a-chart-category/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud allows you to add chart categories to a PowerPoint presentation. You provide data points that will be added to respective data series for the category.

### **API Information**
 
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/categories|POST|Add the chart category|[CreateChartCategory](https://apireference.aspose.cloud/slides/#/Chart/CreateChartCategory)|
### **cURL Example**
{{% alert color="primary" %}}

The referenced shape must be a chart that supports categories (e.g. column or pie chart), otherwise the operation will fail.

{{% /alert %}}

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/shapes/2/categories" -d @"categories.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```

series.json file:
```javascript
{
    "value": "NewCategory",
    "dataPoints": [
        { "value": 40 },
        { "value": 50 },
        { "value": 14 }
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
ChartCategory dto = new ChartCategory();
dto.Value = "NewCategory";
dto.DataPoints = new List<OneValueChartDataPoint>();
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 40 });
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 50 });
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 14 });
Chart chart = api.CreateChartCategory("myPresentaion.pptx", 3, 1, dto);
Console.WriteLine(chart.Categories.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
ChartCategory dto = new ChartCategory();
dto.setValue("NewCategory");
List<OneValueChartDataPoint> dataPoints = new ArrayList<OneValueChartDataPoint>();
OneValueChartDataPoint dataPoint1 = new OneValueChartDataPoint();
dataPoint1.setValue(40.0);
dataPoints.add(dataPoint1);

OneValueChartDataPoint dataPoint2 = new OneValueChartDataPoint();
dataPoint2.setValue(50.0);
dataPoints.add(dataPoint2);

OneValueChartDataPoint dataPoint3 = new OneValueChartDataPoint();
dataPoint3.setValue(14.0);
dataPoints.add(dataPoint3);
dto.setDataPoints(dataPoints);

Chart chart = (Chart)api.createChartCategory("MyPresentation.pptx", 3, 1, dto, null, null, null);
System.out.println(chart.getCategories().size());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ChartCategory;
use Aspose\Slides\Cloud\Sdk\Model\OneValueChartDataPoint;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new ChartCategory();
$dto->setValue("NewCategory");
$dataPoint1 = new OneValueChartDataPoint();
$dataPoint1->setValue(5.5);
$dataPoint2 = new OneValueChartDataPoint();
$dataPoint2->setValue(76);
$dataPoint3 = new OneValueChartDataPoint();
$dataPoint3->setValue(27);
$dto->setDataPoints([$dataPoint1, $dataPoint2, $dataPoint3]);

$result = $api->CreateChartCategory("MyPresentation.pptx", 3, 1, $dto);
print(count($result->getCategories()));
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.chart_category import ChartCategory
from asposeslidescloud.models.one_value_chart_data_point import OneValueChartDataPoint

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = ChartCategory()
dto.value = "NewCategory"
data_point1 = OneValueChartDataPoint()
data_point1.value = 5.5
data_point2 = OneValueChartDataPoint()
data_point2.value = 76
data_point3 = OneValueChartDataPoint()
data_point3.value = 27
dto.data_points = [ data_point1, data_point2, data_point3 ]

result = api.create_chart_category("MyPresentation.pptx", 3, 1, dto)
print(len(result.categories))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new CloudSdk.ChartCategory();
dto.value = "NewCategory";
dto.dataPoints = [{ value: 20 }, { value: 50 }, { value: 30 }];
api.createChartCategory("MyPresentation.pptx", 3, 1, dto).then((result) => {
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

dto := asposeslidescloud.NewChartCategory()
dto.Value = "NewCategory"

dataPoint1 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint1.Value = 20

dataPoint2 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint2.Value = 50

dataPoint3 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint3.Value = 30
dto.DataPoints = []asposeslidescloud.IOneValueChartDataPoint { dataPoint1, dataPoint2, dataPoint3 }

result, _, e := api.SlidesApi.CreateChartCategory("MyPresentation.pptx", 3, 1, dto, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v series.", len(result.(asposeslidescloud.IChart).GetSeries())) //3
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
