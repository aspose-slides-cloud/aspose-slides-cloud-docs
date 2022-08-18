---
title: "Create Scattered Chart"
type: docs
url: /create-scattered-chart/
weight: 40
---

## **Introduction**
The example below shows how to create a scattered chart using Aspose.Slides Cloud. A chart is a kind of shape, so you should use [CreateShape](https://apireference.aspose.cloud/slides/#/Shapes/CreateShape) method for this action.
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
    "chartType": "ScatterWithSmoothLines",
    "x": 100,
    "y": 100,
    "width": 400,
    "height": 400,
    "title": { "hasTitle": true, "text": "Scattered Chart" },
    "series": [
        {
            "name": "Series1",
            "dataPointType": "Scatter",
            "dataPoints": [
                { "xvalue": 1, "yvalue": 3 },
                { "xvalue": 2, "yvalue": 10 }
            ]
        },
        {
            "name": "Series2",
            "dataPointType": "Scatter",
            "dataPoints": [
                { "xvalue": 5, "yvalue": 2 },
                { "xvalue": 3, "yvalue": 1 },
                { "xvalue": 2, "yvalue": 2 },
                { "xvalue": 5, "yvalue": 1 }
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
    "chartType": "ScatterWithSmoothLines",
    "showDataLabelsOverMaximum": true,
    "series": [
        {
            "dataPointType": "Scatter",
            "dataPoints": [
                { "xValue": 1.0, "yValue": 3.0 },
                { "xValue": 2.0, "yValue": 10.0 }
            ],
            "name": "Series1",
            "smooth": true,
            "order": 0,
            "invertIfNegative": true
        },
        {
            "dataPointType": "Scatter",
            "dataPoints": [
                { "xValue": 5.0, "yValue": 2.0 },
                { "xValue": 3.0, "yValue": 1.0 },
                { "xValue": 2.0, "yValue": 2.0 },
                { "xValue": 5.0, "yValue": 1.0 }
            ],
            "name": "Series2",
            "smooth": true,
            "order": 1,
            "invertIfNegative": true
        }
    ],
    "title": { "text": "Scattered Chart", "hasTitle": true},
    "name": "ChartObject",
    "width": 400.0,
    "height": 400.0,
    "x": 100.0,
    "y":100.0,
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
dto.ChartType = Chart.ChartTypeEnum.ScatterWithSmoothLines;
dto.X = 100;
dto.Y = 100;
dto.Width = 400;
dto.Height = 400;
dto.Title = new ChartTitle { HasTitle = true, Text = "Scattered Chart" };

dto.Series = new System.Collections.Generic.List<Series>();
ScatterSeries series1 = new ScatterSeries();
series1.DataPoints = new System.Collections.Generic.List<ScatterChartDataPoint>();
series1.DataPoints.Add(new ScatterChartDataPoint { XValue = 1, YValue = 3 });
series1.DataPoints.Add(new ScatterChartDataPoint { XValue = 2, YValue = 10 });
dto.Series.Add(series1);

ScatterSeries series2 = new ScatterSeries();
series2.DataPoints = new System.Collections.Generic.List<ScatterChartDataPoint>();
series2.DataPoints.Add(new ScatterChartDataPoint { XValue = 5, YValue = 2 });
series2.DataPoints.Add(new ScatterChartDataPoint { XValue = 3, YValue = 1 });
series2.DataPoints.Add(new ScatterChartDataPoint { XValue = 2, YValue = 2 });
series2.DataPoints.Add(new ScatterChartDataPoint { XValue = 5, YValue = 1 });
dto.Series.Add(series2);

Chart chart = (Chart)api.CreateShape("MyPresentation.pptx", 1, dto);
Console.WriteLine(chart.Series.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Chart dto = new Chart();
dto.setChartType(Chart.ChartTypeEnum.SCATTERWITHSMOOTHLINES;
dto.setX(100);
dto.setY(100);
dto.setWidth(400);
dto.setHeight(400);

ChartTitle title = new ChartTitle();
title.setHasTitle(true);
title.setText("Scattered Chart");
dto.setTitle(title);

List<Series> seriesList = new ArrayList<Series>();
ScatterSeries series1 = new ScatterSeries();
List<ScatterChartDataPoint> dataPoints1 = new ArrayList<ScatterChartDataPoint>();
ScatterChartDataPoint dataPoint11 = new ScatterChartDataPoint();
dataPoint11.setXvalue(1);
dataPoint11.setYvalue(3);
dataPoints1.add(dataPoint11);

ScatterChartDataPoint dataPoint12 = new ScatterChartDataPoint();
dataPoint12.setXvalue(2);
dataPoint12.setYvalue(10);
dataPoints1.add(dataPoint12);
series1.setDataPoints(dataPoints1);
seriesList.add(series1);

ScatterSeries series2 = new ScatterSeries();
List<ScatterChartDataPoint> dataPoints2 = new ArrayList<ScatterChartDataPoint>();
ScatterChartDataPoint dataPoint21 = new ScatterChartDataPoint();
dataPoint21.setXvalue(5);
dataPoint21.setYvalue(2);
dataPoints2.add(dataPoint21);

ScatterChartDataPoint dataPoint22 = new ScatterChartDataPoint();
dataPoint22.setXvalue(3);
dataPoint22.setYvalue(1);
dataPoints2.add(dataPoint22);

ScatterChartDataPoint dataPoint23 = new ScatterChartDataPoint();
dataPoint23.setXvalue(2);
dataPoint23.setYvalue(2);
dataPoints2.add(dataPoint23);

ScatterChartDataPoint dataPoint24 = new ScatterChartDataPoint();
dataPoint24.setXvalue(5);
dataPoint24.setYvalue(1);
dataPoints2.add(dataPoint24);
series2.setDataPoints(dataPoints2);
seriesList.add(series2);
dto.setSeries(seriesList);

Chart chart = (Chart)api.createShape("MyPresentation.pptx", 1, dto, null, null, null, null, null);
System.out.println(chart.getSeries().get(0).size());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Chart;
use Aspose\Slides\Cloud\Sdk\Model\ChartTitle;
use Aspose\Slides\Cloud\Sdk\Model\ScatterSeries;
use Aspose\Slides\Cloud\Sdk\Model\ScatterChartDataPoint;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new Chart();
$dto->setChartType("ScatterWithSmoothLines");
$dto->setX(100);
$dto->setY(100);
$dto->setWidth(400);
$dto->setHeight(400);

$title = new ChartTitle();
$title->setHasTitle(true);
$title->setText("Scattered Chart");
$dto->setTitle($title);

$series1 = new ScatterSeries();
$dataPoint11 = new ScatterChartDataPoint();
$dataPoint11->setXValue(1);
$dataPoint11->setYValue(3);
$dataPoint12 = new ScatterChartDataPoint();
$dataPoint12->setXValue(2);
$dataPoint12->setYValue(10);
$series1->setDataPoints([$dataPoint11, $dataPoint12]);

$series2 = new ScatterSeries();
$dataPoint21 = new ScatterChartDataPoint();
$dataPoint21->setXValue(5);
$dataPoint21->setXValue(2);
$dataPoint22 = new ScatterChartDataPoint();
$dataPoint22->setXValue(3);
$dataPoint22->setXValue(1);
$dataPoint23 = new ScatterChartDataPoint();
$dataPoint23->setXValue(2);
$dataPoint23->setXValue(2);
$dataPoint24 = new ScatterChartDataPoint();
$dataPoint24->setXValue(5);
$dataPoint24->setXValue(1);
$series1->setDataPoints([$dataPoint21, $dataPoint22, $dataPoint23, $dataPoint24]);
$dto->setSeries([ $series1, $series2 ]);

$result = $api->CreateShape("MyPresentation.pptx", 1, $dto);
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
from asposeslidescloud.models.chart import Chart
from asposeslidescloud.models.chart_title import ChartTitle
from asposeslidescloud.models.scatter_series import ScatterSeries
from asposeslidescloud.models.scatter_chart_data_point import ScatterChartDataPoint

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = Chart()
dto.chart_type = 'ScatterWithSmoothLines'
dto.x = 100
dto.y = 100
dto.width = 400
dto.height = 400

title = ChartTitle()
title.hasTitle = True
title.text = 'Scattered Chart'
dto.title = title

series1 = ScatterSeries()
data_point11 = ScatterChartDataPoint()
data_point11.x_value = 1
data_point11.y_value = 3
data_point12 = ScatterChartDataPoint()
data_point12.x_value = 2
data_point12.y_value = 10
series1.data_points = [ data_point11, data_point12 ])

series2 = ScatterSeries()
data_point21 = ScatterChartDataPoint()
data_point21.x_value = 5
data_point21.y_value = 2
data_point22 = ScatterChartDataPoint()
data_point22.x_value = 3
data_point22.y_value = 1
data_point23 = ScatterChartDataPoint()
data_point23.x_value = 2
data_point23.y_value = 2
data_point24 = ScatterChartDataPoint()
data_point24.x_value = 5
data_point24.y_value = 1
series2.data_points = [ data_point21, data_point22, data_point23, data_point24 ])
dto.series = [ series1, series2 ]

result = api.create_shape("MyPresentation.pptx", 1, dto)
print(len(result.series[0]))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const chart = new CloudSdk.Chart();
chart.chartType = CloudSdk.Chart.ChartTypeEnum.ScatterWithSmoothLines;
chart.x = 100;
chart.y = 100;
chart.width = 400;
chart.height = 400;

title = new CloudSdk.ChartTitle();
title.hasTitle = true;
title.text = 'Scattered Chart';
chart.title = title;

const series1 = new CloudSdk.ScatterSeries();
series1.dataPoints = [{ xValue: 1, yValue: 3 }, { xValue: 2, yValue: 10 }];
const series2 = new CloudSdk.ScatterSeries();
series2.dataPoints = [{ xValue: 5, yValue: 2 }, { xValue: 3, yValue: 1 }, { xValue: 2, yValue: 2 }, { xValue: 5, yValue: 1 }];
chart.series = [ series1, series2 ];
api.createShape("MyPresentation.pptx", 1, chart).then((result) => {
    console.log(result.body.series[0].length);
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
dto.ChartType = "ScatterWithSmoothLines"
dto.X = 100
dto.Y = 100
dto.Width = 400
dto.Height = 400

title := NewChartTitle()
title.HasTitle = true
title.Text = "Scattered Chart"
dto.Title = title

series1 := NewScatterSeries()
dataPoint11 := NewScatterChartDataPoint()
dataPoint11.XValue = 1
dataPoint11.YValue = 3

dataPoint12 := NewScatterChartDataPoint()
dataPoint12.XValue = 2
dataPoint12.YValue = 10
series1.DataPoints = []IScatterChartDataPoint { dataPoint11, dataPoint12 }

series2 := NewScatterSeries()
dataPoint21 := NewScatterChartDataPoint()
dataPoint21.XValue = 5
dataPoint21.YValue = 2

dataPoint22 := NewScatterChartDataPoint()
dataPoint22.XValue = 3
dataPoint22.YValue = 1

dataPoint23 := NewScatterChartDataPoint()
dataPoint23.XValue = 2
dataPoint23.YValue = 2

dataPoint24 := NewScatterChartDataPoint()
dataPoint24.XValue = 5
dataPoint24.YValue = 1
series2.DataPoints = []IScatterChartDataPoint { dataPoint21, dataPoint22, dataPoint23, dataPoint24 }
dto.Series = []ISeries { series1, series2 }
result, _, e := c.SlidesApi.CreateShape("MyPresentation.pptx", 1, dto, nil, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v points in the 1st series.", len(result.(IChart).getSeries()[0].(IScatterSeries).getDataPoints())) //2
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
