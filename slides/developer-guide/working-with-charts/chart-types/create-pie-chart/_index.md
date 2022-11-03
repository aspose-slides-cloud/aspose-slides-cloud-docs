---
title: "Create Pie Chart"
type: docs
url: /create-pie-chart/
weight: 20
---

## **Introduction**
The example below shows how to create a pie chart using Aspose.Slides Cloud. A chart is a kind of shape, so you should use [CreateShape](https://apireference.aspose.cloud/slides/#/Shapes/CreateShape) method for this action.
### **cURL Example**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes" -d @"chart.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]


```
chart.json file:
```javascript
{
    "type": "Chart",
    "chartType": "Pie",
    "x": 100,
    "y": 100,
    "width": 400,
    "height": 400,
    "title": { "hasTitle": true, "text": "Pie Chart" },
    "categories": [
        { "Value": "First" },
        { "Value": "Second" },
        { "Value": "Third" }
    ],
    "series": [
        {
            "dataPointType": "OneValue",
            "isColorVaried": true,
            "dataPoints": [
                { "value": 20 },
                { "value": 50 },
                { "value": 30 }
            ]
        }
    ]              
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "type": "Chart",
    "chartType": "Pie",
    "showDataLabelsOverMaximum": true,
    "series": [
        {
            "dataPointType": "OneValue",
            "dataPoints": [
                { "value": 20.0 },
                { "value": 50.0 },
                { "value": 30.0 }
            ],
            "name": "Column02",
            "isColorVaried": true,
            "order": 0,
            "invertIfNegative": true
        }
    ],
    "categories": [
        { "value": "First" },
        { "value": "Second" },
        { "value": "Third" }
    ],
    "title": { "text": "Pie Chart", "hasTitle": true},
    "name": "ChartObject",
    "width": 400.0,
    "height": 400.0,
    "x": 100.0, "y":100.0,
    "lineFormat": {
        "alignment": "Center",
        "capStyle": "Flat",
        "dashStyle": "Solid",
        "joinStyle": "Round",
        "style": "Single",
        "miterLimit": 10.0,
        "width": 0.75
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2",
        "relation": "self"
    }
}
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
Chart dto = new Chart();
dto.ChartType = Chart.ChartTypeEnum.Pie;
dto.X = 100;
dto.Y = 100;
dto.Width = 400;
dto.Height = 400;
dto.Title = new ChartTitle { HasTitle = true, Text = "Pie Chart" };

dto.Categories = new System.Collections.Generic.List<ChartCategory>();
dto.Categories.Add(new ChartCategory { Value = "First" });
dto.Categories.Add(new ChartCategory { Value = "Second" });
dto.Categories.Add(new ChartCategory { Value = "Third" });

OneValueSeries series = new OneValueSeries();
series.IsColorVaried = true;
series.DataPoints = new System.Collections.Generic.List<OneValueChartDataPoint>();
series.DataPoints.Add(new OneValueChartDataPoint { Value = 20 });
series.DataPoints.Add(new OneValueChartDataPoint { Value = 50 });
series.DataPoints.Add(new OneValueChartDataPoint { Value = 30 });
dto.Series = new System.Collections.Generic.List<Series>();
dto.Series.Add(series);

Chart chart = (Chart)api.CreateShape("MyPresentation.pptx", 1, dto);
Console.WriteLine(chart.Categories.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Chart dto = new Chart();
dto.setChartType(Chart.ChartTypeEnum.PIE);
dto.setX(100.0);
dto.setY(100.0);
dto.setWidth(400.0);
dto.setHeight(400.0);

ChartTitle title = new ChartTitle();
title.setHasTitle(true);
title.setText("Pie Chart");
dto.setTitle(title);

List<ChartCategory> categories = new ArrayList<ChartCategory>();
ChartCategory category1 = new ChartCategory();
category1.setValue("First");
categories.add(category1);
ChartCategory category2 = new ChartCategory();
category2.setValue("Second");
categories.add(category2);
ChartCategory category3 = new ChartCategory();
category3.setValue("Third");
categories.add(category3);
dto.setCategories(categories);

List<Series> seriesList = new ArrayList<Series>();
OneValueSeries series = new OneValueSeries();
series.setIsColorVaried(true);
List<OneValueChartDataPoint> dataPoints = new ArrayList<OneValueChartDataPoint>();
OneValueChartDataPoint dataPoint1 = new OneValueChartDataPoint();
dataPoint1.setValue(20.0);
dataPoints.add(dataPoint1);

OneValueChartDataPoint dataPoint2 = new OneValueChartDataPoint();
dataPoint2.setValue(50.0);
dataPoints.add(dataPoint2);

OneValueChartDataPoint dataPoint3 = new OneValueChartDataPoint();
dataPoint3.setValue(30.0);
dataPoints.add(dataPoint3);

series.setDataPoints(dataPoints);
seriesList.add(series);
dto.setSeries(seriesList);
Chart chart = (Chart)api.createShape("MyPresentation.pptx", 1, dto, null, null, null, null, null, null);
System.out.println(chart.getCategories().size());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Chart;
use Aspose\Slides\Cloud\Sdk\Model\ChartTitle;
use Aspose\Slides\Cloud\Sdk\Model\ChartCategory;
use Aspose\Slides\Cloud\Sdk\Model\OneValueSeries;
use Aspose\Slides\Cloud\Sdk\Model\OneValueChartDataPoint;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new Chart();
$dto->setChartType("Pie");
$dto->setX(100);
$dto->setY(100);
$dto->setWidth(400);
$dto->setHeight(400);

$title = new ChartTitle();
$title->setHasTitle(true);
$title->setText("Pie Chart");
$dto->setTitle($title);

$category1 = new ChartCategory();
$category1->setValue("First");
$category2 = new ChartCategory();
$category2->setValue("Second");
$category3 = new ChartCategory();
$category3->setValue("Third");
$dto->setCategories([ $category1, $category2, $category3 ]);

$series = new OneValueSeries();
$series->setIsColorVaried(true);
$dataPoint1 = new OneValueChartDataPoint();
$dataPoint1->setValue(20);
$dataPoint2 = new OneValueChartDataPoint();
$dataPoint2->setValue(50);
$dataPoint3 = new OneValueChartDataPoint();
$dataPoint3->setValue(30);
$series->setDataPoints([$dataPoint1, $dataPoint2, $dataPoint3]);
$dto->setSeries([ $series ]);

$result = $api->CreateShape("MyPresentation.pptx", 1, $dto);
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
from asposeslidescloud.models.chart import Chart
from asposeslidescloud.models.chart_title import ChartTitle
from asposeslidescloud.models.chart_category import ChartCategory
from asposeslidescloud.models.one_value_series import OneValueSeries
from asposeslidescloud.models.one_value_chart_data_point import OneValueChartDataPoint

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = Chart()
dto.chart_type = 'Pie'
dto.x = 100
dto.y = 100
dto.width = 400
dto.height = 400

title = ChartTitle()
title.hasTitle = True
title.text = 'Pie Chart'
dto.title = title

category1 = ChartCategory()
category1.value = 'First'
category2 = ChartCategory()
category2.value = 'Second'
category3 = ChartCategory()
category3.value = 'Third'
dto.categories = [ category1, category2, category3 ]

series = OneValueSeries()
series.is_color_varied = True
data_point1 = OneValueChartDataPoint()
data_point1.value = 20
data_point2 = OneValueChartDataPoint()
data_point2.value = 50
data_point3 = OneValueChartDataPoint()
data_point3.value = 30
series.data_points = [ data_point1, data_point2, data_point3 ]
dto.series = [ series ]

result = api.create_shape("MyPresentation.pptx", 1, dto)
print(len(result.categories))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const chart = new CloudSdk.Chart();
chart.chartType = CloudSdk.Chart.ChartTypeEnum.Pie;
chart.x = 100;
chart.y = 100;
chart.width = 400;
chart.height = 400;

title = new CloudSdk.ChartTitle();
title.hasTitle = true;
title.text = 'Pie Chart';
chart.title = title;

chart.categories = [{ value: "First" }, { value: "Second" }, { value: "Third" }];

const series = new CloudSdk.OneValueSeries();
series.dataPoints = [{ value: 20 }, { value: 50 }, { value: 30 }];
chart.series = [ series ];
api.createShape("MyPresentation.pptx", 1, chart).then((result) => {
    console.log(result.body.categories.length);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

dto := NewChart()
dto.ChartType = "Pie"
dto.X = 100
dto.Y = 100
dto.Width = 400
dto.Height = 400

title := NewChartTitle()
title.HasTitle = true
title.Text = "Pie Chart"
dto.Title = title

category1 := NewChartCategory()
category1.Value = "First"
category2 := NewChartCategory()
category2.Value = "Second"
category3 := NewChartCategory()
category3.Value = "Third"
dto.Categories = []IChartCategory { category1, category2, category3 }

series := NewOneValueSeries()
dataPoint1 := NewOneValueChartDataPoint()
dataPoint1.Value = 20

dataPoint2 := NewOneValueChartDataPoint()
dataPoint2.Value = 50

dataPoint3 := NewOneValueChartDataPoint()
dataPoint3.Value = 30
series.DataPoints = []IOneValueChartDataPoint { dataPoint1, dataPoint2, dataPoint3 }
dto.Series = []ISeries { series }

result, _, e := c.SlidesApi.CreateShape("MyPresentation.pptx", 1, dto, nil, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v categories.", len(result.(IChart).getCategories())) //3
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
