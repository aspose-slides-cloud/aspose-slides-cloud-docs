---
title: "Create a Bubble Chart"
keywords: "PowerPoint, presentation, REST API, Cloud API, chart, add chart, Bubble chart, add a Bubble chart"
type: docs
url: /create-a-bubble-chart/
weight: 50
---

## **Introduction**
The example below shows how to create a bubble chart using Aspose.Slides Cloud. A chart is a kind of shape, so you should use [CreateShape](https://apireference.aspose.cloud/slides/#/Shapes/CreateShape) method for this action.
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
    "chartType": "Bubble",
    "x": 100,
    "y": 100,
    "width": 400,
    "height": 400,
    "title": { "hasTitle": true, "text": "Bubble Chart" },
    "series": [
        {
            "name": "Series1",
            "dataPointType": "Bubble",
            "dataPoints": [
                { "xValue": 1, "yValue": 3, "bubbleSize": 2 },
                { "xValue": 2, "yValue": 10, "bubbleSize": 12 }
            ]
        },
        {
            "name": "Series2",
            "dataPointType": "Bubble",
            "dataPoints": [
                { "xValue": 5, "yValue": 2, "bubbleSize": 4 },
                { "xValue": 3, "yValue": 1, "bubbleSize": 8 },
                { "xValue": 2, "yValue": 2, "bubbleSize": 1 },
                { "xValue": 5, "yValue": 1, "bubbleSize": 6 }
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
    "chartType": "Bubble",
    "showDataLabelsOverMaximum": true,
    "series": [
        {
            "dataPointType": "Bubble",
            "dataPoints": [
                { "bubbleSize": 2.0, "xValue": 1.0, "yValue": 3.0 },
                { "bubbleSize": 12.0, "xValue": 2.0, "yValue": 10.0 }
            ],
            "name": "Series1",
            "smooth": true,
            "order": 0,
            "invertIfNegative": true
        },
        {
            "dataPointType": "Bubble",
            "dataPoints": [
                { "bubbleSize": 4.0, "xValue": 5.0, "yValue": 2.0 },
                { "bubbleSize": 8.0, "xValue": 3.0, "yValue": 1.0 },
                { "bubbleSize": 1.0, "xValue": 2.0, "yValue": 2.0 },
                { "bubbleSize": 6.0, "xValue": 5.0, "yValue": 1.0 }
            ],
            "name": "Series2",
            "smooth": true,
            "order": 1,
            "invertIfNegative": true
        }
    ],
    "title": { "text": "Bubble Chart", "hasTitle": true},
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
dto.ChartType = Chart.ChartTypeEnum.Bubble;
dto.X = 100;
dto.Y = 100;
dto.Width = 400;
dto.Height = 400;
dto.Title = new ChartTitle { HasTitle = true, Text = "Bubble Chart" };

dto.Series = new System.Collections.Generic.List<Series>();
BubbleSeries series1 = new BubbleSeries();
series1.DataPoints = new System.Collections.Generic.List<BubbleChartDataPoint>();
series1.DataPoints.Add(new BubbleChartDataPoint { XValue = 1, YValue = 3, BubbleSize = 2 });
series1.DataPoints.Add(new BubbleChartDataPoint { XValue = 2, YValue = 10, BubbleSize = 12 });
dto.Series.Add(series1);

BubbleSeries series2 = new BubbleSeries();
series2.DataPoints = new System.Collections.Generic.List<BubbleChartDataPoint>();
series2.DataPoints.Add(new BubbleChartDataPoint { XValue = 5, YValue = 2, BubbleSize = 4 });
series2.DataPoints.Add(new BubbleChartDataPoint { XValue = 3, YValue = 1, BubbleSize = 8 });
series2.DataPoints.Add(new BubbleChartDataPoint { XValue = 2, YValue = 2, BubbleSize = 1 });
series2.DataPoints.Add(new BubbleChartDataPoint { XValue = 5, YValue = 1, BubbleSize = 6 });
dto.Series.Add(series2);

Chart chart = (Chart)api.CreateShape("MyPresentation.pptx", 1, dto);
Console.WriteLine(chart.Series.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Chart dto = new Chart();
dto.setChartType(Chart.ChartTypeEnum.BUBBLE);
dto.setX(100.0);
dto.setY(100.0);
dto.setWidth(400.0);
dto.setHeight(400.0);

ChartTitle title = new ChartTitle();
title.setHasTitle(true);
title.setText("Bubble Chart");
dto.setTitle(title);

List<Series> seriesList = new ArrayList<Series>();
BubbleSeries series1 = new BubbleSeries();
List<BubbleChartDataPoint> dataPoints1 = new ArrayList<BubbleChartDataPoint>();
BubbleChartDataPoint dataPoint11 = new BubbleChartDataPoint();
dataPoint11.setXvalue(1.0);
dataPoint11.setYvalue(3.0);
dataPoint11.setBubbleSize(2.0);
dataPoints1.add(dataPoint11);

BubbleChartDataPoint dataPoint12 = new BubbleChartDataPoint();
dataPoint12.setXvalue(2.0);
dataPoint12.setYvalue(10.0);
dataPoint12.setBubbleSize(12.0);
dataPoints1.add(dataPoint12);
series1.setDataPoints(dataPoints1);
seriesList.add(series1);

BubbleSeries series2 = new BubbleSeries();
List<BubbleChartDataPoint> dataPoints2 = new ArrayList<BubbleChartDataPoint>();
BubbleChartDataPoint dataPoint21 = new BubbleChartDataPoint();
dataPoint21.setXvalue(5.0);
dataPoint21.setYvalue(2.0);
dataPoint21.setBubbleSize(4.0);
dataPoints2.add(dataPoint21);

BubbleChartDataPoint dataPoint22 = new BubbleChartDataPoint();
dataPoint22.setXvalue(3.0);
dataPoint22.setYvalue(1.0);
dataPoint22.setBubbleSize(8.0);
dataPoints2.add(dataPoint22);

BubbleChartDataPoint dataPoint23 = new BubbleChartDataPoint();
dataPoint23.setXvalue(2.0);
dataPoint23.setYvalue(2.0);
dataPoint23.setBubbleSize(1.0);
dataPoints2.add(dataPoint23);

BubbleChartDataPoint dataPoint24 = new BubbleChartDataPoint();
dataPoint24.setXvalue(5.0);
dataPoint24.setYvalue(1.0);
dataPoint24.setBubbleSize(6.0);
dataPoints2.add(dataPoint24);
series2.setDataPoints(dataPoints2);
seriesList.add(series2);
dto.setSeries(seriesList);

Chart chart = (Chart)api.createShape("MyPresentation.pptx", 1, dto, null, null, null, null, null, null);
System.out.println(chart.getSeries().size());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Chart;
use Aspose\Slides\Cloud\Sdk\Model\ChartTitle;
use Aspose\Slides\Cloud\Sdk\Model\BubbleSeries;
use Aspose\Slides\Cloud\Sdk\Model\BubbleChartDataPoint;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new Chart();
$dto->setChartType("Bubble");
$dto->setX(100);
$dto->setY(100);
$dto->setWidth(400);
$dto->setHeight(400);

$title = new ChartTitle();
$title->setHasTitle(true);
$title->setText("Bubble Chart");
$dto->setTitle($title);

$series1 = new BubbleSeries();
$dataPoint11 = new BubbleChartDataPoint();
$dataPoint11->setXValue(1);
$dataPoint11->setYValue(3);
$dataPoint11->setBubbleSize(2);
$dataPoint12 = new BubbleChartDataPoint();
$dataPoint12->setXValue(2);
$dataPoint12->setYValue(10);
$dataPoint12->setBubbleSize(12);
$series1->setDataPoints([$dataPoint11, $dataPoint12]);

$series2 = new BubbleSeries();
$dataPoint21 = new BubbleChartDataPoint();
$dataPoint21->setXValue(5);
$dataPoint21->setXValue(2);
$dataPoint21->setBubbleSize(4);
$dataPoint22 = new BubbleChartDataPoint();
$dataPoint22->setXValue(3);
$dataPoint22->setXValue(1);
$dataPoint22->setBubbleSize(8);
$dataPoint23 = new BubbleChartDataPoint();
$dataPoint23->setXValue(2);
$dataPoint23->setXValue(2);
$dataPoint23->setBubbleSize(1);
$dataPoint24 = new BubbleChartDataPoint();
$dataPoint24->setXValue(5);
$dataPoint24->setXValue(1);
$dataPoint24->setBubbleSize(6);
$series2->setDataPoints([$dataPoint21, $dataPoint22, $dataPoint23, $dataPoint24]);
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
from asposeslidescloud.models.bubble_series import BubbleSeries
from asposeslidescloud.models.bubble_chart_data_point import BubbleChartDataPoint

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = Chart()
dto.chart_type = 'Bubble'
dto.x = 100
dto.y = 100
dto.width = 400
dto.height = 400

title = ChartTitle()
title.hasTitle = True
title.text = 'Bubble Chart'
dto.title = title

series1 = BubbleSeries()
data_point11 = BubbleChartDataPoint()
data_point11.x_value = 1
data_point11.y_value = 3
data_point11.bubble_size = 2
data_point12 = BubbleChartDataPoint()
data_point12.x_value = 2
data_point12.y_value = 10
data_point12.bubble_size = 12
series1.data_points = [ data_point11, data_point12 ]

series2 = BubbleSeries()
data_point21 = BubbleChartDataPoint()
data_point21.x_value = 5
data_point21.y_value = 2
data_point21.bubble_size = 4
data_point22 = BubbleChartDataPoint()
data_point22.x_value = 3
data_point22.y_value = 1
data_point22.bubble_size = 8
data_point23 = BubbleChartDataPoint()
data_point23.x_value = 2
data_point23.y_value = 2
data_point23.bubble_size = 1
data_point24 = BubbleChartDataPoint()
data_point24.x_value = 5
data_point24.y_value = 1
data_point24.bubble_size = 6
series2.data_points = [ data_point21, data_point22, data_point23, data_point24 ]
dto.series = [ series1, series2 ]

result = api.create_shape("MyPresentation.pptx", 1, dto)
print(str(len(result.series)))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const chart = new CloudSdk.Chart();
chart.chartType = CloudSdk.Chart.ChartTypeEnum.Bubble;
chart.x = 100;
chart.y = 100;
chart.width = 400;
chart.height = 400;

title = new CloudSdk.ChartTitle();
title.hasTitle = true;
title.text = 'Bubble Chart';
chart.title = title;

const series1 = new CloudSdk.BubbleSeries();
series1.dataPoints = [{ xValue: 1, yValue: 3, bubbleSize: 2 }, { xValue: 2, yValue: 10, bubbleSize: 12 }];
const series2 = new CloudSdk.BubbleSeries();
series2.dataPoints = [{ xValue: 5, yValue: 2, bubbleSize: 4 }, { xValue: 3, yValue: 1, bubbleSize: 8 }, { xValue: 2, yValue: 2, bubbleSize: 1 }, { xValue: 5, yValue: 1, bubbleSize: 6 }];
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

dto := asposeslidescloud.NewChart()
dto.ChartType = "Bubble"
dto.X = 100
dto.Y = 100
dto.Width = 400
dto.Height = 400

title := asposeslidescloud.NewChartTitle()
title.HasTitle = true
title.Text = "Bubble Chart"
dto.Title = title

series1 := asposeslidescloud.NewBubbleSeries()
dataPoint11 := asposeslidescloud.NewBubbleChartDataPoint()
dataPoint11.XValue = 1
dataPoint11.YValue = 3
dataPoint11.BubbleSize = 2

dataPoint12 := asposeslidescloud.NewBubbleChartDataPoint()
dataPoint12.XValue = 2
dataPoint12.YValue = 10
dataPoint12.BubbleSize = 12
series1.DataPoints = []asposeslidescloud.IBubbleChartDataPoint { dataPoint11, dataPoint12 }

series2 := asposeslidescloud.NewBubbleSeries()
dataPoint21 := asposeslidescloud.NewBubbleChartDataPoint()
dataPoint21.XValue = 5
dataPoint21.YValue = 2
dataPoint21.BubbleSize = 4

dataPoint22 := asposeslidescloud.NewBubbleChartDataPoint()
dataPoint22.XValue = 3
dataPoint22.YValue = 1
dataPoint22.BubbleSize = 8

dataPoint23 := asposeslidescloud.NewBubbleChartDataPoint()
dataPoint23.XValue = 2
dataPoint23.YValue = 2
dataPoint23.BubbleSize = 1

dataPoint24 := asposeslidescloud.NewBubbleChartDataPoint()
dataPoint24.XValue = 5
dataPoint24.YValue = 1
dataPoint24.BubbleSize = 1
series2.DataPoints = []asposeslidescloud.IBubbleChartDataPoint { dataPoint21, dataPoint22, dataPoint23, dataPoint24 }
dto.Series = []asposeslidescloud.ISeries { series1, series2 }
result, _, e := api.SlidesApi.CreateShape("MyPresentation.pptx", 1, dto, nil, nil, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v points in the 1st series.", len(result.(asposeslidescloud.IChart).GetSeries()[0].(asposeslidescloud.IBubbleSeries).GetDataPoints())) //2
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
