---
title: "Create Column Chart"
type: docs
url: /create-column-chart/
weight: 10
---

## **Introduction**
The example below shows how to create an ordinary column chart using Aspose.Slides Cloud. A chart is a kind of shape, so you should use [CreateShape](https://apireference.aspose.cloud/slides/#/Shapes/CreateShape) method for this action.
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
    "chartType": "ClusteredColumn",
    "x": 100,
    "y": 100,
    "width": 400,
    "height": 400,
    "title": { "hasTitle": true, "text": "Column Chart" },
    "categories": [
        { "Value": "Category1" },
        { "Value": "Category2" },
        { "Value": "Category3" }
    ],
    "series": [
        {
            "dataPointType": "OneValue",
            "dataPoints": [
                { "value": 20 },
                { "value": 50 },
                { "value": 30 }
            ]
        },
        {
            "dataPointType": "OneValue",
            "dataPoints": [
                { "value": 30 },
                { "value": 10 },
                { "value": 60 }
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
    "chartType": "ClusteredColumn",
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
            "order": 0,
            "invertIfNegative": true
        },
        {
            "dataPointType": "OneValue",
            "dataPoints": [
                { "value": 30.0 },
                { "value": 10.0 },
                { "value": 60.0 }
            ],
            "name": "Column03",
            "order": 1,
            "invertIfNegative": true
        }
    ],
    "categories": [
        { "value": "Category1" },
        { "value": "Category2" },
        { "value": "Category3" }
    ],
    "title": { "text": "Column Chart", "hasTitle": true},
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
dto.ChartType = Chart.ChartTypeEnum.ClusteredColumn;
dto.X = 100;
dto.Y = 100;
dto.Width = 400;
dto.Height = 400;
dto.Title = new ChartTitle { HasTitle = true, Text = "Column Chart" };

dto.Categories = new System.Collections.Generic.List<ChartCategory>();
dto.Categories.Add(new ChartCategory { Value = "Category1" });
dto.Categories.Add(new ChartCategory { Value = "Category2" });
dto.Categories.Add(new ChartCategory { Value = "Category3" });

dto.Series = new System.Collections.Generic.List<Series>();
OneValueSeries series1 = new OneValueSeries();
series1.DataPoints = new System.Collections.Generic.List<OneValueChartDataPoint>();
series1.DataPoints.Add(new OneValueChartDataPoint { Value = 20 });
series1.DataPoints.Add(new OneValueChartDataPoint { Value = 50 });
series1.DataPoints.Add(new OneValueChartDataPoint { Value = 30 });
dto.Series.Add(series1);

OneValueSeries series2 = new OneValueSeries();
series2.DataPoints = new System.Collections.Generic.List<OneValueChartDataPoint>();
series2.DataPoints.Add(new OneValueChartDataPoint { Value = 30 });
series2.DataPoints.Add(new OneValueChartDataPoint { Value = 10 });
series2.DataPoints.Add(new OneValueChartDataPoint { Value = 60 });
dto.Series.Add(series2);

Chart chart = (Chart)api.CreateShape("MyPresentation.pptx", 1, dto);
Console.WriteLine(chart.Categories.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Chart dto = new Chart();
dto.setChartType(Chart.ChartTypeEnum.CLUSTEREDCOLUMN;
dto.setX(100);
dto.setY(100);
dto.setWidth(400);
dto.setHeight(400);

ChartTitle title = new ChartTitle();
title.setHasTitle(true);
title.setText("Column Chart");
dto.setTitle(title);

List<ChartCategory> categories = new ArrayList<ChartCategory>();
ChartCategory category1 = new ChartCategory();
category1.setValue("Category1");
categories.add(category1);
ChartCategory category2 = new ChartCategory();
category2.setValue("Category2");
categories.add(category2);
ChartCategory category3 = new ChartCategory();
category3.setValue("Category3");
categories.add(category3);
dto.setCategories(categories);

List<Series> seriesList = new ArrayList<Series>();
OneValueSeries series1 = new OneValueSeries();
List<OneValueChartDataPoint> dataPoints1 = new ArrayList<OneValueChartDataPoint>();
OneValueChartDataPoint dataPoint11 = new OneValueChartDataPoint();
dataPoint11.setValue(20);
dataPoints1.add(dataPoint11);

OneValueChartDataPoint dataPoint12 = new OneValueChartDataPoint();
dataPoint12.setValue(50);
dataPoints1.add(dataPoint12);

OneValueChartDataPoint dataPoint13 = new OneValueChartDataPoint();
dataPoint13.setValue(30);
dataPoints1.add(dataPoint13);
series1.setDataPoints(dataPoints1);
seriesList.add(series1);

OneValueSeries series2 = new OneValueSeries();
List<OneValueChartDataPoint> dataPoints2 = new ArrayList<OneValueChartDataPoint>();
OneValueChartDataPoint dataPoint21 = new OneValueChartDataPoint();
dataPoint21.setValue(30);
dataPoints2.add(dataPoint21);

OneValueChartDataPoint dataPoint22 = new OneValueChartDataPoint();
dataPoint22.setValue(10);
dataPoints2.add(dataPoint22);

OneValueChartDataPoint dataPoint23 = new OneValueChartDataPoint();
dataPoint23.setValue(60);
dataPoints2.add(dataPoint23);
series2.setDataPoints(dataPoints2);
seriesList.add(series2);
dto.setSeries(seriesList);

Chart chart = (Chart)api.createShape("MyPresentation.pptx", 1, dto, null, null, null, null, null);
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
$dto->setChartType("ClusteredColumn");
$dto->setX(100);
$dto->setY(100);
$dto->setWidth(400);
$dto->setHeight(400);

$title = new ChartTitle();
$title->setHasTitle(true);
$title->setText("Column Chart");
$dto->setTitle($title);

$category1 = new ChartCategory();
$category1->setValue("Category1");
$category2 = new ChartCategory();
$category2->setValue("Category2");
$category3 = new ChartCategory();
$category3->setValue("Category3");
$dto->setCategories([ $category1, $category2, $category3 ]);

$series1 = new OneValueSeries();
$dataPoint11 = new OneValueChartDataPoint();
$dataPoint11->setValue(20);
$dataPoint12 = new OneValueChartDataPoint();
$dataPoint12->setValue(50);
$dataPoint13 = new OneValueChartDataPoint();
$dataPoint13->setValue(30);
$series1->setDataPoints([$dataPoint11, $dataPoint12, $dataPoint13]);

$series2 = new OneValueSeries();
$dataPoint21 = new OneValueChartDataPoint();
$dataPoint21->setValue(30);
$dataPoint22 = new OneValueChartDataPoint();
$dataPoint22->setValue(10);
$dataPoint23 = new OneValueChartDataPoint();
$dataPoint23->setValue(60);
$series1->setDataPoints([$dataPoint21, $dataPoint22, $dataPoint23]);
$dto->setSeries([ $series1, $series2 ]);

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
dto.chart_type = 'ClusteredColumn'
dto.x = 100
dto.y = 100
dto.width = 400
dto.height = 400

title = ChartTitle()
title.hasTitle = True
title.text = 'Column Chart'
dto.title = title

category1 = ChartCategory()
category1.value = 'Category1'
category2 = ChartCategory()
category2.value = 'Category2'
category3 = ChartCategory()
category3.value = 'Category3'
dto.categories = [ category1, category2, category3 ]

series1 = OneValueSeries()
data_point11 = OneValueChartDataPoint()
data_point11.value = 20
data_point12 = OneValueChartDataPoint()
data_point12.value = 50
data_point13 = OneValueChartDataPoint()
data_point13.value = 30
series1.data_points = [ data_point11, data_point12, data_point13 ])

series2 = OneValueSeries()
data_point21 = OneValueChartDataPoint()
data_point21.value = 30
data_point22 = OneValueChartDataPoint()
data_point22.value = 10
data_point23 = OneValueChartDataPoint()
data_point23.value = 60
series2.data_points = [ data_point21, data_point22, data_point23 ])
dto.series = [ series1, series2 ]

result = api.create_shape("MyPresentation.pptx", 1, dto)
print(len(result.categories))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const chart = new model.Chart();
chart.chartType = model.Chart.ChartTypeEnum.ClusteredColumn;
chart.x = 100;
chart.y = 100;
chart.width = 400;
chart.height = 400;

title = new model.ChartTitle();
title.hasTitle = true;
title.text = 'Column Chart';
chart.title = title;

chart.categories = [{ value: "Category1" }, { value: "Category2" }, { value: "Category3" }];

const series1 = new model.OneValueSeries();
series1.dataPoints = [{ value: 20 }, { value: 50 }, { value: 30 }];
const series2 = new model.OneValueSeries();
series2.dataPoints = [{ value: 30 }, { value: 10 }, { value: 60 }];
chart.series = [ series1, series2 ];
return api.createShape("MyPresentation.pptx", 1, chart).then((result) => {
    console.log((result.body as model.Chart).categories.length);
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
dto.ChartType = "ClusteredColumn"
dto.X = 100
dto.Y = 100
dto.Width = 400
dto.Height = 400

title := NewChartTitle()
title.HasTitle = true
title.Text = "Column Chart"
dto.Title = title

category1 := NewChartCategory()
category1.Value = "Category1"
category2 := NewChartCategory()
category2.Value = "Category2"
category3 := NewChartCategory()
category3.Value = "Category3"
dto.Categories = []IChartCategory { category1, category2, category3 }

series1 := NewOneValueSeries()
dataPoint11 := NewOneValueChartDataPoint()
dataPoint11.Value = 20

dataPoint12 := NewOneValueChartDataPoint()
dataPoint12.Value = 50

dataPoint13 := NewOneValueChartDataPoint()
dataPoint13.Value = 30
series1.DataPoints = []IOneValueChartDataPoint { dataPoint11, dataPoint12, dataPoint13 }

series2 := NewOneValueSeries()
dataPoint21 := NewOneValueChartDataPoint()
dataPoint21.Value = 30

dataPoint22 := NewOneValueChartDataPoint()
dataPoint22.Value = 10

dataPoint23 := NewOneValueChartDataPoint()
dataPoint23.Value = 60
series2.DataPoints = []IOneValueChartDataPoint { dataPoint21, dataPoint22, dataPoint23 }
dto.Series = []ISeries { series1, series2 }

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
