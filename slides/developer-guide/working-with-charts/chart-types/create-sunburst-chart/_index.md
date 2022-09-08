---
title: "Create Sunburst Chart"
type: docs
url: /create-sunburst-chart/
weight: 30
---

## **Introduction**
The example below shows how to create a sunburst chart using Aspose.Slides Cloud. A chart is a kind of shape, so you should use [CreateShape](https://apireference.aspose.cloud/slides/#/Shapes/CreateShape) method for this action.
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
    "chartType": "Sunburst",
    "x": 100,
    "y": 100,
    "width": 400,
    "height": 400,
    "title": { "hasTitle": true, "text": "Sunburst Chart" },
    "categories": [
        { "value": "Leaf1", "level": 3, "parentCategories": [ "Branch1", "Stem1" ] },
        { "value": "Leaf2", "level": 3, "parentCategories": [ "Branch1", "Stem1" ] },
        { "value": "Branch2", "level": 2, "parentCategories": [ "Stem1" ] },
        { "value": "Stem2", "level": 1 }
    ],
    "series": [
        {
            "dataPointType": "OneValue",
            "dataPoints": [
                { "value": 40 },
                { "value": 50 },
                { "value": 70 },
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
    "chartType": "Sunburst",
    "showDataLabelsOverMaximum": true,
    "series": [
        {
            "dataPointType": "OneValue",
            "dataPoints": [
                { "value": 40.0 },
                { "value": 50.0 },
                { "value": 70.0 },
                { "value": 60.0 }
            ],
            "order": 0,
            "invertIfNegative": true
        }
    ],
    "categories": [
        {
            "parentCategories": [ "Branch1", "Stem1" ],
            "level": 3,
            "value": "Leaf1"
        },
        {
            "parentCategories": [ "Branch1", "Stem1" ],
            "level": 3,
            "value": "Leaf2"
        },
        {
            "parentCategories": [ "Stem1" ],
            "level": 2,
            "value": "Branch2"
        },
        {
            "level": 1,
            "value": "Stem2"
        },
    ],
    "title": { "text": "Sunburst Chart", "hasTitle": true },
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
dto.ChartType = Chart.ChartTypeEnum.Sunburst;
dto.X = 100;
dto.Y = 100;
dto.Width = 400;
dto.Height = 400;
dto.Title = new ChartTitle { HasTitle = true, Text = "Sunburst Chart" };

dto.Categories = new List<ChartCategory>();
dto.Categories.Add(new ChartCategory { Value = "Leaf1", Level = 3, ParentCategories = new List<string> { "Branch1", "Stem1" } });
dto.Categories.Add(new ChartCategory { Value = "Leaf2", Level = 3, ParentCategories = new List<string> { "Branch1", "Stem1" } });
dto.Categories.Add(new ChartCategory { Value = "Branch2", Level = 2, ParentCategories = new List<string> { "Stem1" } });
dto.Categories.Add(new ChartCategory { Value = "Stem2", Level = 1 });

dto.Series = new System.Collections.Generic.List<Series>();
OneValueSeries series = new OneValueSeries();
series.DataPoints = new System.Collections.Generic.List<OneValueChartDataPoint>();
series.DataPoints.Add(new OneValueChartDataPoint { Value = 40 });
series.DataPoints.Add(new OneValueChartDataPoint { Value = 50 });
series.DataPoints.Add(new OneValueChartDataPoint { Value = 70 });
series.DataPoints.Add(new OneValueChartDataPoint { Value = 60 });
dto.Series.Add(series);

Chart chart = (Chart)api.CreateShape("MyPresentation.pptx", 1, dto);
Console.WriteLine(chart.Series.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Chart dto = new Chart();
dto.setChartType(Chart.ChartTypeEnum.SUNBURST);
dto.setX(100.0);
dto.setY(100.0);
dto.setWidth(400.0);
dto.setHeight(400.0);

ChartTitle title = new ChartTitle();
title.setHasTitle(true);
title.setText("Sunburst Chart");
dto.setTitle(title);

List<ChartCategory> categories = new ArrayList<ChartCategory>();
ChartCategory category1 = new ChartCategory();
category1.setValue("Leaf1");
category1.setLevel(3);
List<String> parentCategories1 = new ArrayList<String>();
parentCategories1.add("Branch1");
parentCategories1.add("Stem1");
category1.setParentCategories(parentCategories1);
categories.add(category1);

ChartCategory category2 = new ChartCategory();
category2.setValue("Leaf2");
category2.setLevel(3);
List<String> parentCategories2 = new ArrayList<String>();
parentCategories2.add("Branch1");
parentCategories2.add("Stem1");
category2.setParentCategories(parentCategories2);
categories.add(category2);

ChartCategory category3 = new ChartCategory();
category3.setValue("Branch2");
category3.setLevel(2);
List<String> parentCategories3 = new ArrayList<String>();
parentCategories3.add("Stem1");
category3.setParentCategories(parentCategories3);
categories.add(category3);

ChartCategory category4 = new ChartCategory();
category4.setValue("Stem2");
category4.setLevel(1);
categories.add(category4);
dto.setCategories(categories);

List<Series> seriesList = new ArrayList<Series>();
OneValueSeries series = new OneValueSeries();
List<OneValueChartDataPoint> dataPoints = new ArrayList<OneValueChartDataPoint>();
OneValueChartDataPoint dataPoint1 = new OneValueChartDataPoint();
dataPoint1.setValue(40.0);
dataPoints.add(dataPoint1);

OneValueChartDataPoint dataPoint2 = new OneValueChartDataPoint();
dataPoint2.setValue(50.0);
dataPoints.add(dataPoint2);

OneValueChartDataPoint dataPoint3 = new OneValueChartDataPoint();
dataPoint3.setValue(70.0);
dataPoints.add(dataPoint3);

OneValueChartDataPoint dataPoint4 = new OneValueChartDataPoint();
dataPoint4.setValue(60.0);
dataPoints.add(dataPoint4);

series.setDataPoints(dataPoints);
seriesList.add(series);
dto.setSeries(seriesList);

Chart chart = (Chart)api.createShape("MyPresentation.pptx", 1, dto, null, null, null, null, null);
System.out.println(chart.getSeries().size());
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
$dto->setChartType("Sunburst");
$dto->setX(100);
$dto->setY(100);
$dto->setWidth(400);
$dto->setHeight(400);

$title = new ChartTitle();
$title->setHasTitle(true);
$title->setText("Sunburst Chart");
$dto->setTitle($title);

$category1 = new ChartCategory();
$category1->setValue("Leaf1");
$category1->setLevel(3);
$category1->setParentCategories([ "Branch1", "Stem1" ]);

$category2 = new ChartCategory();
$category2->setValue("Leaf2");
$category2->setLevel(3);
$category2->setParentCategories([ "Branch1", "Stem1" ]);

$category3 = new ChartCategory();
$category3->setValue("Branch2");
$category3->setLevel(2);
$category3->setParentCategories([ "Stem1" ]);

$category4 = new ChartCategory();
$category4->setValue("Stem2");
$category4->setLevel(1);
$dto->setCategories([ $category1, $category2, $category3, $category4 ]);

$series = new OneValueSeries();
$dataPoint1 = new OneValueChartDataPoint();
$dataPoint1->setValue(40);

$dataPoint2 = new OneValueChartDataPoint();
$dataPoint2->setValue(50);

$dataPoint3 = new OneValueChartDataPoint();
$dataPoint3->setValue(70);

$dataPoint4 = new OneValueChartDataPoint();
$dataPoint4->setValue(60);
$series->setDataPoints([ $dataPoint1, $dataPoint2, $dataPoint3, $dataPoint4 ]);
$dto->setSeries([ $series ]);

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
from asposeslidescloud.models.chart_category import ChartCategory
from asposeslidescloud.models.one_value_series import OneValueSeries
from asposeslidescloud.models.one_value_chart_data_point import OneValueChartDataPoint

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = Chart()
dto.chart_type = 'Sunburst'
dto.x = 100
dto.y = 100
dto.width = 400
dto.height = 400

title = ChartTitle()
title.hasTitle = True
title.text = 'Sunburst Chart'
dto.title = title

category1 = ChartCategory()
category1.value = "Leaf1"
category1.level = 3
category1.parent_categories = [ "Branch1", "Stem1" ]
category2 = ChartCategory()
category2.value = "Leaf2"
category2.level = 3
category2.parent_categories = [ "Branch1", "Stem1" ]
category3 = ChartCategory()
category3.value = "Branch2"
category3.level = 2
category3.parent_categories = [ "Stem1" ]
category4 = ChartCategory()
category4.value = "Stem2"
category4.level = 1
chart.categories = [ category1, category2, category3, category4 ]

series = OneValueSeries()
data_point1 = OneValueChartDataPoint()
data_point1.value = 40
data_point2 = OneValueChartDataPoint()
data_point2.value = 50
data_point3 = OneValueChartDataPoint()
data_point3.value = 70
data_point4 = OneValueChartDataPoint()
data_point4.value = 60
series.data_points = [ data_point1, data_point2, data_point3, data_point4 ])
dto.series = [ series ]

result = api.create_shape("MyPresentation.pptx", 1, dto)
print(len(result.series[0]))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const chart = new CloudSdk.Chart();
chart.chartType = CloudSdk.Chart.ChartTypeEnum.Sunburst;
chart.x = 100;
chart.y = 100;
chart.width = 400;
chart.height = 400;

title = new CloudSdk.ChartTitle();
title.hasTitle = true;
title.text = 'Sunburst Chart';
chart.title = title;

const category1 = new CloudSdk.ChartCategory();
category1.value = "Leaf1";
category1.level = 3;
category1.parentCategories = [ "Branch1", "Stem1" ];
const category2 = new CloudSdk.ChartCategory();
category2.value = "Leaf2";
category2.level = 3;
category2.parentCategories = [ "Branch1", "Stem1" ];
const category3 = new CloudSdk.ChartCategory();
category3.value = "Branch2";
category3.level = 2;
category3.parentCategories = [ "Stem1" ];
const category4 = new CloudSdk.ChartCategory();
category4.value = "Stem2";
category4.level = 1;
chart.categories = [ category1, category2, category3, category4 ];

const series = new CloudSdk.OneValueSeries();
series.dataPoints = [{ value: 40 }, { value: 50 }, { value: 70 }, { value: 60 }];
chart.series = [ series ];
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
dto.ChartType = "Sunburst"
dto.X = 100
dto.Y = 100
dto.Width = 400
dto.Height = 400

title := NewChartTitle()
title.HasTitle = true
title.Text = "Sunburst Chart"
dto.Title = title

category1 := NewChartCategory()
category1.Value = "Leaf1"
category1.Level = 3
category1.ParentCategories = []string { "Branch1", "Stem1" }
category2 := NewChartCategory()
category2.Value = "Leaf2"
category2.Level = 3
category2.ParentCategories = []string { "Branch1", "Stem1" }
category3 := NewChartCategory()
category3.Value = "Branch2"
category3.Level = 2
category3.ParentCategories = []string { "Stem1" }
category4 := NewChartCategory()
category4.Value = "Stem2"
category4.Level = 1
dto.Categories = []IChartCategory { category1, category2, category3, category4 }

series := NewOneValueSeries()
dataPoint1 := NewOneValueChartDataPoint()
dataPoint1.Value = 40

dataPoint2 := NewOneValueChartDataPoint()
dataPoint2.Value = 50

dataPoint3 := NewOneValueChartDataPoint()
dataPoint3.Value = 70

dataPoint3 := NewOneValueChartDataPoint()
dataPoint3.Value = 60
series.DataPoints = []IOneValueChartDataPoint { dataPoint1, dataPoint2, dataPoint3, dataPoint4 }
dto.Series = []ISeries { series }

result, _, e := c.SlidesApi.CreateShape("MyPresentation.pptx", 1, dto, nil, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("%v categories.", len(result.(IChart).getSeries()[0].(IOneValueSeries).getDataPoints())) //3
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
