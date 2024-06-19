---
title: "Set a Chart Data Source"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- chart
- chart data
- chart data source
- chart workbook
- data series
- data categories
type: docs
url: /set-a-chart-data-source/
weight: 80
---

## **Introduction**

By default, chart data is placed in an Excel workbook. You can explicitly specify the data source for your chart data. Two options are available: Workbook and Literals.
Storing data in the workbook means specifying the address of the first cell of the data range. Let's say we want to store the series of four data points in the workbook cells B2:B5. In this case, "B2" is the first cell of the data range. Cell addresses are represented as row and column indexes, thus "B2" is row 1 and column 1 accordingly.
Literals means storing values as is in the chart cache.
The data source can be specified for series name, values, x-values, y-values, bubble sizes, and categories.

This article uses the `CreateShape` method described in [Add a Shape to a Slide](/slides/add-a-shape-to-a-slide/).

## **Workbook**

### **Examples**

The code examples below show how to create a ClustereColumn chart, and explicitly specify data allocation in the workbook.

**cURL Example**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Create the Chart**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes" \
     -H "authorization: Bearer MyAccessToken" \
	 -H "Content-Type: application/json" \
	 -d @chart.json
```

chart.json content:

```json
{
    "type": "Chart",
    "chartType": "ClusteredColumn",
    "x": 20,
    "y": 20,
    "width": 400,
    "height": 300,
	"dataSourceForCategories" : {
		"type": "workbook",
		"woksheetIndex": 1,
		"columnIndex": 1,
		"rowIndex": 2
	},
    "categories": [
        { "Value": "Category1" },
        { "Value": "Category2" },
        { "Value": "Category3" }
    ],
    "series": [
        {
            "dataPointType": "OneValue",
			"dataSourecForSeriesName" : {
				"type": "workbook",
				"woksheetIndex": 1,
				"columnIndex": 2,
				"rowIndex": 1
			},
			"name": "Series1",
			"dataSourceForValues" : {
				"type": "workbook",
				"woksheetIndex": 1,
				"columnIndex": 2,
				"rowIndex": 2
			},
            "dataPoints": [
                { "value": 40 },
                { "value": 50 },
                { "value": 70 }
            ]
        },
        {
            "dataPointType": "OneValue",
			"dataSourecForSeriesName" : {
				"type": "workbook",
				"woksheetIndex": 1,
				"columnIndex": 3,
				"rowIndex": 1
			},
			"name": "Series2",
			"dataSourceForValues" : {
				"type": "workbook",
				"woksheetIndex": 1,
				"columnIndex": 3,
				"rowIndex": 2
			},
            "dataPoints": [
                { "value": 55 },
                { "value": 35 },
                { "value": 90 }
            ]
        }
    ]              
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```text
Code: 200
Returns shape info.
```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

string fileName = "MyPresentation.pptx";
int slideIndex = 1;

ShapeBase dto = new Chart
{
	ChartType = Chart.ChartTypeEnum.ClusteredColumn,
	X = 20,
	Y = 20,
	Width = 400,
	Height = 300,
	DataSourceForCategories = new Workbook()
	{
		WorksheetIndex = 1,
		ColumnIndex = 1,
		RowIndex = 2
	},
	Categories = new List<ChartCategory>
	{
		new ChartCategory { Value = "Category1" },
		new ChartCategory { Value = "Category2" },
		new ChartCategory { Value = "Category3" }
	},
	Series = new List<Series>
	{
		new OneValueSeries
		{
			Name = "Series1",
			DataSourceForSeriesName = new Workbook()
			{
				WorksheetIndex = 1,
				ColumnIndex = 2,
				RowIndex = 1
			},
			DataSourceForValues = new Workbook()
			{
				WorksheetIndex = 1,
				ColumnIndex = 2,
				RowIndex = 2
			},
			DataPoints = new List<OneValueChartDataPoint>
			{
				new OneValueChartDataPoint { Value = 40 },
				new OneValueChartDataPoint { Value = 50 },
				new OneValueChartDataPoint { Value = 70 }
			}
		},
		new OneValueSeries
		{
			Name = "Series2",
			DataSourceForSeriesName = new Workbook()
			{
				WorksheetIndex = 1,
				ColumnIndex = 3,
				RowIndex = 1
			},
			DataSourceForValues = new Workbook()
			{
				WorksheetIndex = 1,
				ColumnIndex = 3,
				RowIndex = 2
			},
			DataPoints = new List<OneValueChartDataPoint>
			{
				new OneValueChartDataPoint { Value = 55 },
				new OneValueChartDataPoint { Value = 35 },
				new OneValueChartDataPoint { Value = 90 }
			}
		}
	}
};

Chart chart = api.CreateShape(fileName, slideIndex, dto) as Chart;
Console.WriteLine("Chart has been created.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

String fileName = "MyPresentation.pptx";
int slideIndex = 1;

Chart dto = new Chart();
dto.setChartType(Chart.ChartTypeEnum.CLUSTEREDCOLUMN);
dto.setX(20.0);
dto.setY(20.0);
dto.setWidth(400.0);
dto.setHeight(300.0);

Workbook dataSourceForCategories = new Workbook();
dataSourceForCategories.setWorksheetIndex(1);
dataSourceForCategories.setColumnIndex(1);
dataSourceForCategories.setRowIndex(2);

dto.setDataSourceForCategories(dataSourceForCategories);

ChartCategory category1 = new ChartCategory();
category1.setValue("Category1");
ChartCategory category2 = new ChartCategory();
category2.setValue("Category2");
ChartCategory category3 = new ChartCategory();
category3.setValue("Category3");

dto.setCategories(Arrays.asList(category1, category2, category3));

OneValueSeries series1 = new OneValueSeries();
series1.setName("Series1");

Workbook dataSourceForSeries1Name = new Workbook();
dataSourceForSeries1Name.setWorksheetIndex(1);
dataSourceForSeries1Name.setColumnIndex(2);
dataSourceForSeries1Name.setRowIndex(1);

series1.setDataSourceForSeriesName(dataSourceForSeries1Name);

Workbook dataSourceForSeries1Values = new Workbook();
dataSourceForSeries1Values.setWorksheetIndex(1);
dataSourceForSeries1Values.setColumnIndex(2);
dataSourceForSeries1Values.setRowIndex(2);

series1.setDataSourceForValues(dataSourceForSeries1Values);

OneValueChartDataPoint dataPoint11 = new OneValueChartDataPoint();
dataPoint11.setValue(40.0);
OneValueChartDataPoint dataPoint12 = new OneValueChartDataPoint();
dataPoint12.setValue(50.0);
OneValueChartDataPoint dataPoint13 = new OneValueChartDataPoint();
dataPoint13.setValue(70.0);

series1.setDataPoints(Arrays.asList(dataPoint11, dataPoint12, dataPoint13));

OneValueSeries series2 = new OneValueSeries();
series2.setName("Series2");

Workbook dataSourceForSeries2Name = new Workbook();
dataSourceForSeries2Name.setWorksheetIndex(1);
dataSourceForSeries2Name.setColumnIndex(3);
dataSourceForSeries2Name.setRowIndex(1);

series2.setDataSourceForSeriesName(dataSourceForSeries2Name);

Workbook dataSourceForSeries2Values = new Workbook();
dataSourceForSeries2Values.setWorksheetIndex(1);
dataSourceForSeries2Values.setColumnIndex(3);
dataSourceForSeries2Values.setRowIndex(2);

series2.setDataSourceForValues(dataSourceForSeries2Values);

OneValueChartDataPoint dataPoint21 = new OneValueChartDataPoint();
dataPoint21.setValue(55.0);
OneValueChartDataPoint dataPoint22 = new OneValueChartDataPoint();
dataPoint22.setValue(35.0);
OneValueChartDataPoint dataPoint23 = new OneValueChartDataPoint();
dataPoint23.setValue(90.0);

series2.setDataPoints(Arrays.asList(dataPoint21, dataPoint22, dataPoint23));

dto.setSeries(Arrays.asList(series1, series2));

Chart chart = (Chart)api.createShape(fileName, slideIndex, dto, null, null, null, null, null, null);
System.out.println("Chart has been created.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Chart;
use Aspose\Slides\Cloud\Sdk\Model\ChartCategory;
use Aspose\Slides\Cloud\Sdk\Model\OneValueSeries;
use Aspose\Slides\Cloud\Sdk\Model\OneValueChartDataPoint;
use Aspose\Slides\Cloud\Sdk\Model\Workbook;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;

$dto = new Chart();
$dto->setChartType("ClusteredColumn");
$dto->setX(20);
$dto->setY(20);
$dto->setWidth(400);
$dto->setHeight(300);

$categoryDataSource = new Workbook();
$categoryDataSource->setWorksheetIndex(1);
$categoryDataSource->setColumnIndex(1);
$categoryDataSource->setRowIndex(2);

$dto->setDataSourceForCategories($categoryDataSource);

$category1 = new ChartCategory();
$category1->setValue("Category1");
$category2 = new ChartCategory();
$category2->setValue("Category2");
$category3 = new ChartCategory();
$category3->setValue("Category3");

$dto->setCategories([ $category1, $category2, $category3 ]);

$series1 = new OneValueSeries();
$series1->setName("Series1");

$series1NameDataSource = new Workbook();
$series1NameDataSource->setWorksheetIndex(1);
$series1NameDataSource->setColumnIndex(2);
$series1NameDataSource->setRowIndex(1);

$series1->setDataSourceForSeriesName($series1NameDataSource);

$values1DataSource = new Workbook();
$values1DataSource->setWorksheetIndex(1);
$values1DataSource->setColumnIndex(2);
$values1DataSource->setRowIndex(2);

$series1->setDataSourceForValues($values1DataSource);

$dataPoint11 = new OneValueChartDataPoint();
$dataPoint11->setValue(40);
$dataPoint12 = new OneValueChartDataPoint();
$dataPoint12->setValue(50);
$dataPoint13 = new OneValueChartDataPoint();
$dataPoint13->setValue(70);

$series1->setDataPoints([ $dataPoint11, $dataPoint12, $dataPoint13 ]);

$series2 = new OneValueSeries();
$series2->setName("Series2");

$series2NameDataSource = new Workbook();
$series2NameDataSource->setWorksheetIndex(1);
$series2NameDataSource->setColumnIndex(3);
$series2NameDataSource->setRowIndex(1);

$series2->setDataSourceForSeriesName($series2NameDataSource);

$values2DataSource = new Workbook();
$values2DataSource->setWorksheetIndex(1);
$values2DataSource->setColumnIndex(3);
$values2DataSource->setRowIndex(2);

$series2->setDataSourceForValues($values2DataSource);

$dataPoint21 = new OneValueChartDataPoint();
$dataPoint21->setValue(55);
$dataPoint22 = new OneValueChartDataPoint();
$dataPoint22->setValue(35);
$dataPoint23 = new OneValueChartDataPoint();
$dataPoint23->setValue(90);

$series2->setDataPoints([ $dataPoint21, $dataPoint22, $dataPoint23 ]);

$dto->setSeries([ $series1, $series2 ]);

$result = $api->createShape($fileName, $slideIndex, $dto);
print("Chart has been created.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1

chart = Chart.new
chart.chart_type = "ClusteredColumn"
chart.x = 20
chart.y = 20
chart.width = 400
chart.height = 300

data_source_for_categories = Workbook.new
data_source_for_categories.worksheet_index = 1
data_source_for_categories.column_index = 1
data_source_for_categories.row_index = 2

chart.data_source_for_categories = data_source_for_categories

category1 = ChartCategory.new
category1.value = "Category1"
category2 = ChartCategory.new
category2.value = "Category2"
category3 = ChartCategory.new
category3.value = "Category3"

chart.categories = [category1, category2, category3]

series1 = OneValueSeries.new
series1.name = "Series1"

data_source_for_series1_name = Workbook.new
data_source_for_series1_name.worksheet_index = 1
data_source_for_series1_name.column_index = 2
data_source_for_series1_name.row_index = 1

series1.data_source_for_series_name = data_source_for_series1_name    

data_source_for_series1_values =  Workbook.new
data_source_for_series1_values.worksheet_index = 1
data_source_for_series1_values.column_index = 2
data_source_for_series1_values.row_index = 2

series1.data_source_for_values = data_source_for_series1_values

point11 = OneValueChartDataPoint.new
point11.value = 40
point12 = OneValueChartDataPoint.new
point12.value = 50
point13 = OneValueChartDataPoint.new
point13.value = 70

series1.data_points = [point11, point12, point13]

series2 = OneValueSeries.new
series2.name = "Series2"

data_source_for_series2_name = Workbook.new
data_source_for_series2_name.worksheet_index = 1
data_source_for_series2_name.column_index = 3
data_source_for_series2_name.row_index = 1

series2.data_source_for_series_name = data_source_for_series2_name 

data_source_for_series2_values = Workbook.new
data_source_for_series2_values.worksheet_index = 1
data_source_for_series2_values.column_index = 3
data_source_for_series2_values.row_index = 2

series2.data_source_for_values = data_source_for_series2_values

point21 = OneValueChartDataPoint.new
point21.value = 55
point22 = OneValueChartDataPoint.new
point22.value = 35
point23 = OneValueChartDataPoint.new
point23.value = 90

series2.data_points = [point21, point22, point23]

chart.series = [series1, series2]

result = api.create_shape(file_name, slide_index, chart)
print "Chart has been created."
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import Chart
from asposeslidescloud.models import Workbook
from asposeslidescloud.models import ChartCategory
from asposeslidescloud.models import OneValueSeries
from asposeslidescloud.models import OneValueChartDataPoint

api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1

chart = Chart()
chart.chart_type = "ClusteredColumn"
chart.x = 20
chart.y = 20
chart.width = 400
chart.height = 300

categories_data_source = Workbook()
categories_data_source.worksheet_index = 1
categories_data_source.row_index = 2
categories_data_source.column_index = 1

chart.data_source_for_categories = categories_data_source

category1 = ChartCategory()
category1.value = "Category1"
category2 = ChartCategory()
category2.value = "Category2"
category3 = ChartCategory()
category3.value = "Category3"

chart.categories = [category1, category2, category3]

series1 = OneValueSeries()
series1.name = "Series1"

series1_name_data_source = Workbook()
series1_name_data_source.worksheet_index = 1
series1_name_data_source.column_index = 2
series1_name_data_source.row_index = 1

series1.data_source_for_series_name = series1_name_data_source

series1_values_data_source = Workbook()
series1_values_data_source.worksheet_index = 1
series1_values_data_source.column_index = 2
series1_values_data_source.row_index = 2

series1.data_source_for_values = series1_values_data_source

point11 = OneValueChartDataPoint()
point11.value = 40
point12 = OneValueChartDataPoint()
point12.value = 50
point13 = OneValueChartDataPoint()
point13.value = 70

series1.data_points = [point11, point12, point13]

series2 = OneValueSeries()
series2.name = "Series2"

series2_name_data_source = Workbook()
series2_name_data_source.worksheet_index = 1
series2_name_data_source.column_index = 3
series2_name_data_source.row_index = 1

series2.data_source_for_series_name = series2_name_data_source

series2_values_data_source = Workbook()
series2_values_data_source.worksheet_index = 1
series2_values_data_source.column_index = 3
series2_values_data_source.row_index = 2

series2.data_source_for_values = series2_values_data_source

point21 = OneValueChartDataPoint()
point21.value = 55
point22 = OneValueChartDataPoint()
point22.value = 35
point23 = OneValueChartDataPoint()
point23.value = 90

series2.data_points = [point21, point22, point23]

chart.series = [series1, series2]
     
result = api.create_shape(file_name, slide_index, chart)
print("Chart has been created.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;

const chart = new CloudSdk.Chart();
chart.chartType = CloudSdk.Chart.ChartTypeEnum.ClusteredColumn;
chart.x = 20;
chart.y = 20;
chart.width = 400;
chart.height = 300;

const dataSourceForCategories = new CloudSdk.Workbook();
dataSourceForCategories.worksheetIndex = 1;
dataSourceForCategories.columnIndex = 1;
dataSourceForCategories.rowIndex = 2;

chart.dataSourceForCategories = dataSourceForCategories;
chart.categories = [{value: "Category1"}, {value: "Category2"}, {value: "Category3"}];

const series1 = new CloudSdk.OneValueSeries();
series1.name = "Series1";

const dataSourceForSeriesName1 = new CloudSdk.Workbook();
dataSourceForSeriesName1.worksheetIndex = 1;
dataSourceForSeriesName1.columnIndex = 2;
dataSourceForSeriesName1.rowIndex = 1;

series1.dataSourceForSeriesName = dataSourceForSeriesName1;

const dataSourceForValues1 = new CloudSdk.Workbook();
dataSourceForValues1.worksheetIndex = 1;
dataSourceForValues1.columnIndex = 2;
dataSourceForValues1.rowIndex = 2;

series1.dataSourceForValues = dataSourceForValues1;
series1.dataPoints = [{value: 40}, {value: 50}, {value: 70}];    

const series2 = new CloudSdk.OneValueSeries();
series2.name = "Series2";

const dataSourceForSeriesName2 = new CloudSdk.Workbook();
dataSourceForSeriesName2.worksheetIndex = 1;
dataSourceForSeriesName2.columnIndex = 3;
dataSourceForSeriesName2.rowIndex = 1;

series2.dataSourceForSeriesName = dataSourceForSeriesName2;

const dataSourceForValues2 = new CloudSdk.Workbook();
dataSourceForValues2.worksheetIndex = 1;
dataSourceForValues2.columnIndex = 3;
dataSourceForValues2.rowIndex = 2;

series2.dataSourceForValues = dataSourceForValues2;
series2.dataPoints = [{value: 55}, {value: 35}, {value: 90}];

chart.series = [series1, series2];

let result = await api.createShape(fileName, slideIndex, chart);
console.log("Chart has been created.");
```

{{< /tab >}}
{{< tab tabNum="7" >}}

```go
config := asposeslidescloud.NewConfiguration()
config.AppSid = "MyClientId"
config.AppKey = "MyClientSecret"

api := asposeslidescloud.NewAPIClient(config).SlidesApi

fileName := "MyPresentation.pptx"
var slideIndex int32 = 1

chart := asposeslidescloud.NewChart()
chart.ChartType = "ClusteredColumn"
chart.X = 20
chart.Y = 20
chart.Width = 400
chart.Height = 300

dataSourceForCategories := asposeslidescloud.NewWorkbook()
dataSourceForCategories.WorksheetIndex = 1
dataSourceForCategories.ColumnIndex = 1
dataSourceForCategories.RowIndex = 2

chart.DataSourceForCategories = dataSourceForCategories

category1 := asposeslidescloud.NewChartCategory()
category1.Value = "Category1"
category2 := asposeslidescloud.NewChartCategory()
category2.Value = "Category2"
category3 := asposeslidescloud.NewChartCategory()
category3.Value = "Category3"

chart.Categories = []asposeslidescloud.IChartCategory{category1, category2, category3}

series1 := asposeslidescloud.NewOneValueSeries()
series1.Name = "Series1"

dataSourceForSeries1Name := asposeslidescloud.NewWorkbook()
dataSourceForSeries1Name.WorksheetIndex = 1
dataSourceForSeries1Name.ColumnIndex = 2
dataSourceForSeries1Name.RowIndex = 1

series1.DataSourceForSeriesName = dataSourceForSeries1Name

dataSourceForSeries1Values := asposeslidescloud.NewWorkbook()
dataSourceForSeries1Values.WorksheetIndex = 1
dataSourceForSeries1Values.ColumnIndex = 2
dataSourceForSeries1Values.RowIndex = 2

series1.DataSourceForValues = dataSourceForSeries1Values

point11 := asposeslidescloud.NewOneValueChartDataPoint()
point11.Value = 40
point12 := asposeslidescloud.NewOneValueChartDataPoint()
point12.Value = 50
point13 := asposeslidescloud.NewOneValueChartDataPoint()
point13.Value = 70

series1.DataPoints = []asposeslidescloud.IOneValueChartDataPoint{point11, point12, point13}

series2 := asposeslidescloud.NewOneValueSeries()
series2.Name = "Series2"

dataSourceForSeries2Name := asposeslidescloud.NewWorkbook()
dataSourceForSeries2Name.WorksheetIndex = 1
dataSourceForSeries2Name.ColumnIndex = 3
dataSourceForSeries2Name.RowIndex = 1

series2.DataSourceForSeriesName = dataSourceForSeries2Name

dataSourceForSeries2Values := asposeslidescloud.NewWorkbook()
dataSourceForSeries2Values.WorksheetIndex = 1
dataSourceForSeries2Values.ColumnIndex = 3
dataSourceForSeries2Values.RowIndex = 2

series2.DataSourceForValues = dataSourceForSeries2Values

point21 := asposeslidescloud.NewOneValueChartDataPoint()
point21.Value = 55
point22 := asposeslidescloud.NewOneValueChartDataPoint()
point22.Value = 35
point23 := asposeslidescloud.NewOneValueChartDataPoint()
point23.Value = 90

series2.DataPoints = []asposeslidescloud.IOneValueChartDataPoint{point21, point22, point23}

chart.Series = []asposeslidescloud.ISeries{series1, series2}

api.CreateShape(fileName, slideIndex, chart, nil, nil, "", "", "", "")
fmt.Printf("Chart has been created.")
```

{{< /tab >}}
{{< tab tabNum="8" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/Workbook.h"
#include "asposeslidescloud/model/OneValueSeries.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> api = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;

    std::shared_ptr<Chart> dto = std::make_shared<Chart>();
    dto->setChartType(L"ClusteredColumn");
    dto->setX(20);
    dto->setY(20);
    dto->setWidth(400);
    dto->setHeight(300);

    std::shared_ptr<Workbook> dataSourceForCategories = std::make_shared<Workbook>();
    dataSourceForCategories->setWorksheetIndex(1);
    dataSourceForCategories->setColumnIndex(1);
    dataSourceForCategories->setRowIndex(2);

    dto->setDataSourceForCategories(dataSourceForCategories);

    std::shared_ptr<ChartCategory> category1 = std::make_shared<ChartCategory>();
    category1->setValue(L"Category1");
    std::shared_ptr<ChartCategory> category2 = std::make_shared<ChartCategory>();
    category2->setValue(L"Category2");
    std::shared_ptr<ChartCategory> category3 = std::make_shared<ChartCategory>();
    category3->setValue(L"Category3");

    dto->setCategories({ category1, category2, category3 });

    std::shared_ptr<OneValueSeries> series1 = std::make_shared<OneValueSeries>();
    series1->setName(L"Series1");

    std::shared_ptr<Workbook> dataSourceForSeries1Name = std::make_shared<Workbook>();
    dataSourceForSeries1Name->setWorksheetIndex(1);
    dataSourceForSeries1Name->setColumnIndex(2);
    dataSourceForSeries1Name->setRowIndex(1);

    series1->setDataSourceForSeriesName(dataSourceForSeries1Name);

    std::shared_ptr<Workbook> dataSourceForSeries1Values = std::make_shared<Workbook>();
    dataSourceForSeries1Values->setWorksheetIndex(1);
    dataSourceForSeries1Values->setColumnIndex(2);
    dataSourceForSeries1Values->setRowIndex(2);

    series1->setDataSourceForValues(dataSourceForSeries1Values);

    std::shared_ptr<OneValueChartDataPoint> dataPoint11 = std::make_shared<OneValueChartDataPoint>();
    dataPoint11->setValue(40.0);
    std::shared_ptr<OneValueChartDataPoint> dataPoint12 = std::make_shared<OneValueChartDataPoint>();
    dataPoint12->setValue(50.0);
    std::shared_ptr<OneValueChartDataPoint> dataPoint13 = std::make_shared<OneValueChartDataPoint>();
    dataPoint13->setValue(70.0);

    series1->setDataPoints({ dataPoint11, dataPoint12, dataPoint13 });

    std::shared_ptr<OneValueSeries> series2 = std::make_shared<OneValueSeries>();
    series2->setName(L"Series2");

    std::shared_ptr<Workbook> dataSourceForSeries2Name = std::make_shared<Workbook>();
    dataSourceForSeries2Name->setWorksheetIndex(1);
    dataSourceForSeries2Name->setColumnIndex(3);
    dataSourceForSeries2Name->setRowIndex(1);

    series2->setDataSourceForSeriesName(dataSourceForSeries2Name);

    std::shared_ptr<Workbook> dataSourceForSeries2Values = std::make_shared<Workbook>();
    dataSourceForSeries2Values->setWorksheetIndex(1);
    dataSourceForSeries2Values->setColumnIndex(3);
    dataSourceForSeries2Values->setRowIndex(2);

    series2->setDataSourceForValues(dataSourceForSeries2Values);

    std::shared_ptr<OneValueChartDataPoint> dataPoint21 = std::make_shared<OneValueChartDataPoint>();
    dataPoint21->setValue(55.0);
    std::shared_ptr<OneValueChartDataPoint> dataPoint22 = std::make_shared<OneValueChartDataPoint>();
    dataPoint22->setValue(35.0);
    std::shared_ptr<OneValueChartDataPoint> dataPoint23 = std::make_shared<OneValueChartDataPoint>();
    dataPoint23->setValue(90.0);

    series2->setDataPoints({ dataPoint21, dataPoint22, dataPoint23 });

    dto->setSeries({ series1, series2 });

    std::shared_ptr<Chart> chart = std::static_pointer_cast<Chart>(api->createShape(fileName, slideIndex, dto).get());
    std::wcout << L"Chart has been created.";
}
```

{{< /tab >}}
{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Chart;
use AsposeSlidesCloud::Object::OneValueSeries;
use AsposeSlidesCloud::Object::Workbook;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;

my $dto = AsposeSlidesCloud::Object::Chart->new();
$dto->{chart_type} = "ClusteredColumn";
$dto->{x} = 20;
$dto->{y} = 20;
$dto->{width} = 400;
$dto->{height} = 300;

my $data_source_for_categories = AsposeSlidesCloud::Object::Workbook->new();
$data_source_for_categories->{worksheet_index} = 1;
$data_source_for_categories->{column_index} = 1;
$data_source_for_categories->{row_index} = 2;

$dto->{data_source_for_categories} = $data_source_for_categories;

my $category1 = AsposeSlidesCloud::Object::ChartCategory->new();
$category1->{value} = "Category1";
my $category2 = AsposeSlidesCloud::Object::ChartCategory->new();
$category2->{value} = "Category2";
my $category3 = AsposeSlidesCloud::Object::ChartCategory->new();
$category3->{value} = "Category3";

$dto->{categories} = [ $category1, $category2, $category3 ];

my $series1 = AsposeSlidesCloud::Object::OneValueSeries->new();
$series1->{name} = "Series1";

my $data_source_for_series1_name = AsposeSlidesCloud::Object::Workbook->new();
$data_source_for_series1_name->{worksheet_index} = 1;
$data_source_for_series1_name->{column_index} = 2;
$data_source_for_series1_name->{row_index} = 1;

$series1->{data_source_for_series_name} = $data_source_for_series1_name;

my $data_source_for_series1_values = AsposeSlidesCloud::Object::Workbook->new();
$data_source_for_series1_values->{worksheet_index} = 1;
$data_source_for_series1_values->{column_index} = 2;
$data_source_for_series1_values->{row_index} = 2;

$series1->{data_source_for_values} = $data_source_for_series1_values;

my $point11 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point11->{value} = 40;
my $point12 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point12->{value} = 50;
my $point13 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point13->{value} = 70;

$series1->{data_points} = [ $point11, $point12, $point13 ];

my $series2 = AsposeSlidesCloud::Object::OneValueSeries->new();
$series2->{name} = "Series2";

my $data_source_for_series2_name = AsposeSlidesCloud::Object::Workbook->new();
$data_source_for_series2_name->{worksheet_index} = 1;
$data_source_for_series2_name->{column_index} = 3;
$data_source_for_series2_name->{row_index} = 1;

$series1->{data_source_for_series_name} = $data_source_for_series2_name;

my $data_source_for_series2_values = AsposeSlidesCloud::Object::Workbook->new();
$data_source_for_series2_values->{worksheet_index} = 1;
$data_source_for_series2_values->{column_index} = 3;
$data_source_for_series2_values->{row_index} = 2;

$series2->{data_source_for_values} = $data_source_for_series2_values;

my $point21 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point21->{value} = 55;
my $point22 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point22->{value} = 35;
my $point23 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point23->{value} = 90;

$series2->{data_points} = [ $point21, $point22, $point23 ];

$dto->{series} = [ $series1, $series2 ];

my $chart = $api->create_shape(name => $file_name, slide_index => $slide_index, dto => $dto);
print "Chart has been created.";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **Literals**

### **Examples**

The code examples below show how to create a ClustereColumn chart using literals as a data source.

**cURL Example**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Create the Chart**

```sh
curl POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes" \
     -H "authorization: Bearer MyAccessToken" \
	 -H "Content-Type: application/json" \
	 -d @chart.json
```

chart.json content:
```json
{
    "type": "Chart",
    "chartType": "ClusteredColumn",
    "x": 20,
    "y": 20,
    "width": 400,
    "height": 300,
	"dataSourceForCategories" : {
		"type": "literals"
	},
    "categories": [
        { "Value": "Category1" },
        { "Value": "Category2" },
        { "Value": "Category3" }
    ],
    "series": [
        {
            "dataPointType": "OneValue",
			"dataSourecForSeriesName" : {
				"type": "literals"
			},
			"name": "Series1",
			"dataSourceForValues" : {
				"type": "literals"
			},
            "dataPoints": [
                { "value": 20 },
                { "value": 50 },
                { "value": 30 }
            ]
        },
        {
            "dataPointType": "OneValue",
			"dataSourecForSeriesName" : {
				"type": "literals"
			},
			"name": "Series2",
			"dataSourceForValues" : {
				"type": "literals"
			},
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

```text
Code: 200
Returns shape info.
```

{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

string fileName = "MyPresentation.pptx";
int slideIndex = 1;

ShapeBase dto = new Chart
{
    ChartType = Chart.ChartTypeEnum.ClusteredColumn,
    X = 20,
    Y = 20,
    Width = 400,
    Height = 300,
    DataSourceForCategories = new Literals(),
    Categories = new List<ChartCategory>
    {
        new ChartCategory { Value = "Category1" },
        new ChartCategory { Value = "Category2" },
        new ChartCategory { Value = "Category3" }
    },
    Series = new List<Series>
    {
        new OneValueSeries
        {
            Name = "Series1",
            DataSourceForSeriesName = new Literals(),
            DataSourceForValues = new Literals(),
            DataPoints = new List<OneValueChartDataPoint>
            {
                new OneValueChartDataPoint { Value = 20 },
                new OneValueChartDataPoint { Value = 50 },
                new OneValueChartDataPoint { Value = 30 }
            }
        },
        new OneValueSeries
        {
            Name = "Series2",
            DataSourceForSeriesName = new Literals(),
            DataSourceForValues = new Literals(),
            DataPoints = new List<OneValueChartDataPoint>
            {
                new OneValueChartDataPoint { Value = 30 },
                new OneValueChartDataPoint { Value = 10 },
                new OneValueChartDataPoint { Value = 60 }
            }
        }
    }
};

Chart chart = api.CreateShape(fileName, slideIndex, dto) as Chart;
Console.WriteLine("Chart has been created.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

String fileName = "MyPresentation.pptx";
int slideIndex = 1;

Chart dto = new Chart();
dto.setChartType(Chart.ChartTypeEnum.CLUSTEREDCOLUMN);
dto.setX(20.0);
dto.setY(20.0);
dto.setWidth(400.0);
dto.setHeight(300.0);

Literals dataSourceForCategories = new Literals();
dto.setDataSourceForCategories(dataSourceForCategories);

ChartCategory category1 = new ChartCategory();
category1.setValue("Category1");
ChartCategory category2 = new ChartCategory();
category2.setValue("Category2");
ChartCategory category3 = new ChartCategory();
category3.setValue("Category3");

dto.setCategories(Arrays.asList(category1, category2, category3));

OneValueSeries series1 = new OneValueSeries();
series1.setName("Series1");

Literals dataSourceForSeries1Name = new Literals();
series1.setDataSourceForSeriesName(dataSourceForSeries1Name);
Literals dataSourceForSeries1Values = new Literals();
series1.setDataSourceForValues(dataSourceForSeries1Values);

OneValueChartDataPoint dataPoint11 = new OneValueChartDataPoint();
dataPoint11.setValue(20.0);
OneValueChartDataPoint dataPoint12 = new OneValueChartDataPoint();
dataPoint12.setValue(50.0);
OneValueChartDataPoint dataPoint13 = new OneValueChartDataPoint();
dataPoint13.setValue(30.0);

series1.setDataPoints(Arrays.asList(dataPoint11, dataPoint12, dataPoint13));

OneValueSeries series2 = new OneValueSeries();
series2.setName("Series2");

Literals dataSourceForSeries2Name = new Literals();
series2.setDataSourceForSeriesName(dataSourceForSeries2Name);
Literals dataSourceForSeries2Values = new Literals();
series2.setDataSourceForValues(dataSourceForSeries2Values);

OneValueChartDataPoint dataPoint21 = new OneValueChartDataPoint();
dataPoint21.setValue(30.0);
OneValueChartDataPoint dataPoint22 = new OneValueChartDataPoint();
dataPoint22.setValue(10.0);
OneValueChartDataPoint dataPoint23 = new OneValueChartDataPoint();
dataPoint23.setValue(60.0);

series2.setDataPoints(Arrays.asList(dataPoint21, dataPoint22, dataPoint23));

dto.setSeries(Arrays.asList(series1, series2));

Chart chart = (Chart)api.createShape(fileName, slideIndex, dto, null, null, null, null, null, null);
System.out.println("Chart has been created.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Chart;
use Aspose\Slides\Cloud\Sdk\Model\ChartCategory;
use Aspose\Slides\Cloud\Sdk\Model\OneValueSeries;
use Aspose\Slides\Cloud\Sdk\Model\OneValueChartDataPoint;
use Aspose\Slides\Cloud\Sdk\Model\Literals;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;

$dto = new Chart();
$dto->setChartType("ClusteredColumn");
$dto->setX(20);
$dto->setY(20);
$dto->setWidth(400);
$dto->setHeight(300);

$categoryDataSource = new Literals();
$dto->setDataSourceForCategories($categoryDataSource);

$category1 = new ChartCategory();
$category1->setValue("Category1");
$category2 = new ChartCategory();
$category2->setValue("Category2");
$category3 = new ChartCategory();
$category3->setValue("Category3");

$dto->setCategories([ $category1, $category2, $category3 ]);

$series1 = new OneValueSeries();
$series1->setName("Series1");

$series1NameDataSource = new Literals();
$series1->setDataSourceForSeriesName($series1NameDataSource);
$values1DataSource = new Literals();
$series1->setDataSourceForValues($values1DataSource);

$dataPoint11 = new OneValueChartDataPoint();
$dataPoint11->setValue(20);
$dataPoint12 = new OneValueChartDataPoint();
$dataPoint12->setValue(50);
$dataPoint13 = new OneValueChartDataPoint();
$dataPoint13->setValue(30);

$series1->setDataPoints([ $dataPoint11, $dataPoint12, $dataPoint13 ]);

$series2 = new OneValueSeries();
$series2->setName("Series2");

$series2NameDataSource = new Literals();
$series2->setDataSourceForSeriesName($series2NameDataSource);
$values2DataSource = new Literals();
$series2->setDataSourceForValues($values2DataSource);

$dataPoint21 = new OneValueChartDataPoint();
$dataPoint21->setValue(30);
$dataPoint22 = new OneValueChartDataPoint();
$dataPoint22->setValue(10);
$dataPoint23 = new OneValueChartDataPoint();
$dataPoint23->setValue(60);

$series2->setDataPoints([ $dataPoint21, $dataPoint22, $dataPoint23 ]);

$dto->setSeries([ $series1, $series2 ]);

$result = $api->createShape($fileName, $slideIndex, $dto);
print("Chart has been created.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1

chart = Chart.new
chart.chart_type = "ClusteredColumn"
chart.x = 20
chart.y = 20
chart.width = 400
chart.height = 300

data_source_for_categories = Literals.new
chart.data_source_for_categories = data_source_for_categories

category1 = ChartCategory.new
category1.value = "Category1"
category2 = ChartCategory.new
category2.value = "Category2"
category3 = ChartCategory.new
category3.value = "Category3"

chart.categories = [category1, category2, category3]

series1 = OneValueSeries.new
series1.name = "Series1"

data_source_for_series1_name = Literals.new
series1.data_source_for_series_name = data_source_for_series1_name    
data_source_for_series1_values =  Literals.new
series1.data_source_for_values = data_source_for_series1_values

point11 = OneValueChartDataPoint.new
point11.value = 20
point12 = OneValueChartDataPoint.new
point12.value = 50
point13 = OneValueChartDataPoint.new
point13.value = 30

series1.data_points = [point11, point12, point13]

series2 = OneValueSeries.new
series2.name = "Series2"

data_source_for_series2_name = Literals.new
series2.data_source_for_series_name = data_source_for_series2_name 
data_source_for_series2_values = Literals.new
series2.data_source_for_values = data_source_for_series2_values

point21 = OneValueChartDataPoint.new
point21.value = 30
point22 = OneValueChartDataPoint.new
point22.value = 10
point23 = OneValueChartDataPoint.new
point23.value = 60

series2.data_points = [point21, point22, point23]

chart.series = [series1, series2]

result = api.create_shape(file_name, slide_index, chart)
print "Chart has been created."
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import Chart
from asposeslidescloud.models import Literals
from asposeslidescloud.models import ChartCategory
from asposeslidescloud.models import OneValueSeries
from asposeslidescloud.models import OneValueChartDataPoint

configuration = Configuration()
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1

chart = Chart()
chart.chart_type = "ClusteredColumn"
chart.x = 20
chart.y = 20
chart.width = 400
chart.height = 300

categories_data_source = Literals()
chart.data_source_for_categories = categories_data_source

category1 = ChartCategory()
category1.value = "Category1"
category2 = ChartCategory()
category2.value = "Category2"
category3 = ChartCategory()
category3.value = "Category3"

chart.categories = [category1, category2, category3]

series1 = OneValueSeries()
series1.name = "Series1"

series1_name_data_source = Literals()
series1.data_source_for_series_name = series1_name_data_source
series1_values_data_source = Literals()
series1.data_source_for_values = series1_values_data_source

point11 = OneValueChartDataPoint()
point11.value = 20
point12 = OneValueChartDataPoint()
point12.value = 50
point13 = OneValueChartDataPoint()
point13.value = 30

series1.data_points = [point11, point12, point13]

series2 = OneValueSeries()
series2.name = "Series2"

series2_name_data_source = Literals()
series2.data_source_for_series_name = series2_name_data_source
series2_values_data_source = Literals()
series2.data_source_for_values = series2_values_data_source

point21 = OneValueChartDataPoint()
point21.value = 30
point22 = OneValueChartDataPoint()
point22.value = 10
point23 = OneValueChartDataPoint()
point23.value = 60

series2.data_points = [point21, point22, point23]

chart.series = [series1, series2]

result = api.create_shape(file_name, slide_index, chart)
print("Chart has been created.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```js
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;

const chart = new CloudSdk.Chart();
chart.chartType = CloudSdk.Chart.ChartTypeEnum.ClusteredColumn;
chart.x = 20;
chart.y = 20;
chart.width = 400;
chart.height = 300;

const dataSourceForCategories = new CloudSdk.Literals();
chart.dataSourceForCategories = dataSourceForCategories;

chart.categories = [{value: "Category1"}, {value: "Category2"}, {value: "Category3"}];

const series1 = new CloudSdk.OneValueSeries();
series1.name = "Series1";

const dataSourceForSeriesName1 = new CloudSdk.Literals();
series1.dataSourceForSeriesName = dataSourceForSeriesName1;
const dataSourceForValues1 = new CloudSdk.Literals();
series1.dataSourceForValues = dataSourceForValues1;

series1.dataPoints = [{value: 20}, {value: 50}, {value: 30}];  

const series2 = new CloudSdk.OneValueSeries();
series2.name = "Series2";

const dataSourceForSeriesName2 = new CloudSdk.Literals();
series2.dataSourceForSeriesName = dataSourceForSeriesName2;
const dataSourceForValues2 = new CloudSdk.Literals();
series2.dataSourceForValues = dataSourceForValues2;

series2.dataPoints = [{value: 30}, {value: 10}, {value: 60}];

chart.series = [series1, series2];

api.createShape(fileName, slideIndex, chart).then(()=>{
    console.log("Chart has been created.");
});
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"

api := asposeslidescloud.NewAPIClient(cfg).SlidesApi

fileName := "MyPresentation.pptx"
var slideIndex int32 = 1

chart := asposeslidescloud.NewChart()
chart.ChartType = "ClusteredColumn"
chart.X = 20
chart.Y = 20
chart.Width = 400
chart.Height = 300

dataSourceForCategories := asposeslidescloud.NewLiterals()
chart.DataSourceForCategories = dataSourceForCategories

category1 := asposeslidescloud.NewChartCategory()
category1.Value = "Category1"
category2 := asposeslidescloud.NewChartCategory()
category2.Value = "Category2"
category3 := asposeslidescloud.NewChartCategory()
category3.Value = "Category3"

chart.Categories = []asposeslidescloud.IChartCategory{category1, category2, category3}

series1 := asposeslidescloud.NewOneValueSeries()
series1.Name = "Series1"

dataSourceForSeries1Name := asposeslidescloud.NewLiterals()
series1.DataSourceForSeriesName = dataSourceForSeries1Name
dataSourceForSeries1Values := asposeslidescloud.NewLiterals()
series1.DataSourceForValues = dataSourceForSeries1Values

point11 := asposeslidescloud.NewOneValueChartDataPoint()
point11.Value = 20
point12 := asposeslidescloud.NewOneValueChartDataPoint()
point12.Value = 50
point13 := asposeslidescloud.NewOneValueChartDataPoint()
point13.Value = 30

series1.DataPoints = []asposeslidescloud.IOneValueChartDataPoint{point11, point12, point13}

series2 := asposeslidescloud.NewOneValueSeries()
series2.Name = "Series2"

dataSourceForSeries2Name := asposeslidescloud.NewLiterals()
series2.DataSourceForSeriesName = dataSourceForSeries2Name
dataSourceForSeries2Values := asposeslidescloud.NewLiterals()
series2.DataSourceForValues = dataSourceForSeries2Values

point21 := asposeslidescloud.NewOneValueChartDataPoint()
point21.Value = 30
point22 := asposeslidescloud.NewOneValueChartDataPoint()
point22.Value = 10
point23 := asposeslidescloud.NewOneValueChartDataPoint()
point23.Value = 60

series2.DataPoints = []asposeslidescloud.IOneValueChartDataPoint{point21, point22, point23}

chart.Series = []asposeslidescloud.ISeries{series1, series2}

api.CreateShape(fileName, slideIndex, chart, nil, nil, "", "", "", "")
fmt.Printf("Chart has been created.")
```

{{< /tab >}}
{{< tab tabNum="8" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/Literals.h"
#include "asposeslidescloud/model/OneValueSeries.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> api = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;

    std::shared_ptr<Chart> dto = std::make_shared<Chart>();
    dto->setChartType(L"ClusteredColumn");
    dto->setX(20);
    dto->setY(20);
    dto->setWidth(400);
    dto->setHeight(300);

    std::shared_ptr<Literals> dataSourceForCategories = std::make_shared<Literals>();
    dto->setDataSourceForCategories(dataSourceForCategories);

    std::shared_ptr<ChartCategory> category1 = std::make_shared<ChartCategory>();
    category1->setValue(L"Category1");
    std::shared_ptr<ChartCategory> category2 = std::make_shared<ChartCategory>();
    category2->setValue(L"Category2");
    std::shared_ptr<ChartCategory> category3 = std::make_shared<ChartCategory>();
    category3->setValue(L"Category3");

    dto->setCategories({ category1, category2, category3 });

    std::shared_ptr<OneValueSeries> series1 = std::make_shared<OneValueSeries>();
    series1->setName(L"Series1");

    std::shared_ptr<Literals> dataSourceForSeries1Name = std::make_shared<Literals>();
    series1->setDataSourceForSeriesName(dataSourceForSeries1Name);
    std::shared_ptr<Literals> dataSourceForSeries1Values = std::make_shared<Literals>();
    series1->setDataSourceForValues(dataSourceForSeries1Values);

    std::shared_ptr<OneValueChartDataPoint> dataPoint11 = std::make_shared<OneValueChartDataPoint>();
    dataPoint11->setValue(20);
    std::shared_ptr<OneValueChartDataPoint> dataPoint12 = std::make_shared<OneValueChartDataPoint>();
    dataPoint12->setValue(50);
    std::shared_ptr<OneValueChartDataPoint> dataPoint13 = std::make_shared<OneValueChartDataPoint>();
    dataPoint13->setValue(30);

    series1->setDataPoints({ dataPoint11, dataPoint12, dataPoint13 });

    std::shared_ptr<OneValueSeries> series2 = std::make_shared<OneValueSeries>();
    series2->setName(L"Series2");

    std::shared_ptr<Literals> dataSourceForSeries2Name = std::make_shared<Literals>();
    series2->setDataSourceForSeriesName(dataSourceForSeries2Name);
    std::shared_ptr<Literals> dataSourceForSeries2Values = std::make_shared<Literals>();
    series2->setDataSourceForValues(dataSourceForSeries2Values);

    std::shared_ptr<OneValueChartDataPoint> dataPoint21 = std::make_shared<OneValueChartDataPoint>();
    dataPoint21->setValue(30);
    std::shared_ptr<OneValueChartDataPoint> dataPoint22 = std::make_shared<OneValueChartDataPoint>();
    dataPoint22->setValue(10);
    std::shared_ptr<OneValueChartDataPoint> dataPoint23 = std::make_shared<OneValueChartDataPoint>();
    dataPoint23->setValue(60);

    series2->setDataPoints({ dataPoint21, dataPoint22, dataPoint23 });

    dto->setSeries({ series1, series2 });

    std::shared_ptr<Chart> chart = std::static_pointer_cast<Chart>(api->createShape(fileName, slideIndex, dto).get());
    std::wcout << L"Chart has been created.";
}
```

{{< /tab >}}
{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Chart;
use AsposeSlidesCloud::Object::OneValueSeries;
use AsposeSlidesCloud::Object::Literals;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;

my $dto = AsposeSlidesCloud::Object::Chart->new();
$dto->{chart_type} = "ClusteredColumn";
$dto->{x} = 20;
$dto->{y} = 20;
$dto->{width} = 400;
$dto->{height} = 300;

my $data_source_for_categories = AsposeSlidesCloud::Object::Literals->new();
$dto->{data_source_for_categories} = $data_source_for_categories;

my $category1 = AsposeSlidesCloud::Object::ChartCategory->new();
$category1->{value} = "Category1";
my $category2 = AsposeSlidesCloud::Object::ChartCategory->new();
$category2->{value} = "Category2";
my $category3 = AsposeSlidesCloud::Object::ChartCategory->new();
$category3->{value} = "Category3";

$dto->{categories} = [ $category1, $category2, $category3 ];

my $series1 = AsposeSlidesCloud::Object::OneValueSeries->new();
$series1->{name} = "Series1";

my $data_source_for_series1_name = AsposeSlidesCloud::Object::Literals->new();
$series1->{data_source_for_series_name} = $data_source_for_series1_name;
my $data_source_for_series1_values = AsposeSlidesCloud::Object::Literals->new();
$series1->{data_source_for_values} = $data_source_for_series1_values;

my $point11 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point11->{value} = 20;
my $point12 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point12->{value} = 50;
my $point13 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point13->{value} = 30;

$series1->{data_points} = [ $point11, $point12, $point13 ];

my $series2 = AsposeSlidesCloud::Object::OneValueSeries->new();
$series2->{name} = "Series2";

my $data_source_for_series2_name = AsposeSlidesCloud::Object::Literals->new();
$series1->{data_source_for_series_name} = $data_source_for_series2_name;
my $data_source_for_series2_values = AsposeSlidesCloud::Object::Literals->new();
$series2->{data_source_for_values} = $data_source_for_series2_values;

my $point21 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point21->{value} = 30;
my $point22 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point22->{value} = 10;
my $point23 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point23->{value} = 60;

$series2->{data_points} = [ $point21, $point22, $point23 ];

$dto->{series} = [ $series1, $series2 ];

my $chart = $api->create_shape(name => $file_name, slide_index => $slide_index, dto => $dto);
print "Chart has been created.";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
