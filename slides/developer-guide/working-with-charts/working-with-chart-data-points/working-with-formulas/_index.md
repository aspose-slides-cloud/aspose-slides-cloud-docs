---
title: "Working with Formulas"
type: docs
url: /working-with-formulas/
weight: 40
---
## **Introduction**
Chart data point value can be calculated based on a formula.
Formulas can be specified for values, x-values, y-values, and bubble sizes.
You can use formulas in the case when an Excel workbook is used as the data source.

## **Formulas**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{shapeIndex}/shapes|POST|Create new shape.|[CreateShape]()|

### **Examples**
**cURL Example**

The code examples below show how to use the formula for calculating the value of the third data point on the first series. The formula looks like "SUM(B2:B3)". It means the third data point value is the sum of the first two data point values.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
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
	"dataSourceForCategories" : {
		"type": "workbook",
		"woksheetIndex": 0,
		"columnIndex": 0,
		"rowIndex": 1
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
				"woksheetIndex": 0,
				"columnIndex": 1,
				"rowIndex": 0
			},
			"name": "Series1",
			"dataSourceForValues" : {
				"type": "workbook",
				"woksheetIndex": 0,
				"columnIndex": 1,
				"rowIndex": 1
			},
            "dataPoints": [
                { "value": 40 },
                { "value": 50 },
                { "value_formula": "SUM(B2:B3)" }
            ]
		}
    ]              
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

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

ShapeBase dto = new Chart
{
	ChartType = Chart.ChartTypeEnum.ClusteredColumn,
	Width = 400,
	Height = 300,
	DataSourceForCategories = new Workbook()
	{
		WorksheetIndex = 0,
		ColumnIndex = 0,
		RowIndex = 1
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
				WorksheetIndex = 0,
				ColumnIndex = 1,
				RowIndex = 0
			},
			DataSourceForValues = new Workbook()
			{
				WorksheetIndex = 0,
				ColumnIndex = 1,
				RowIndex = 1
			},
			DataPoints = new List<OneValueChartDataPoint>
			{
				new OneValueChartDataPoint { Value = 40 },
				new OneValueChartDataPoint { Value = 50 },
				new OneValueChartDataPoint { ValueFormula = "SUM(B2:B3)" }
			}
		}
	}
};

Chart chart = api.CreateShape("MyPresentation.pptx", 1, dto) as Chart;

Console.WriteLine("Third data point value is: " + (chart.Series[0] as OneValueSeries).DataPoints[2].Value);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Chart dto = new Chart();
dto.setChartType(Chart.ChartTypeEnum.CLUSTEREDCOLUMN);
dto.setWidth(400.0);
dto.setHeight(300.0);

Workbook dataSourceForCategories = new Workbook();
dataSourceForCategories.setWorksheetIndex(0);
dataSourceForCategories.setColumnIndex(0);
dataSourceForCategories.setRowIndex(1);
dto.setDataSourceForCategories(dataSourceForCategories);
ChartCategory category1 = new ChartCategory();
category1.setValue("Category1");
ChartCategory category2 = new ChartCategory();
category2.setValue("Category2");
ChartCategory category3 = new ChartCategory();
.setValue("Category3");
List<ChartCategory> categories = new ArrayList<ChartCategory>();
categories.add(category1);
categories.add(category2);
categories.add(category3);
dto.setCategories(categories);

List<Series> seriesList = new ArrayList<Series>();
OneValueSeries series1 = new OneValueSeries();
Workbook dataSourceForSeries1Name = new Workbook();
dataSourceForSeries1Name.setWorksheetIndex(0);
dataSourceForSeries1Name.setColumnIndex(1);
dataSourceForSeries1Name.setRowIndex(0);
series1.setDataSourceForSeriesName(dataSourceForSeries1Name);
Workbook dataSourceForSeries1Values = new Workbook();
dataSourceForSeries1Values.setWorksheetIndex(0);
dataSourceForSeries1Values.setColumnIndex(1);
dataSourceForSeries1Values.setRowIndex(1);
series1.setDataSourceForSeriesName(dataSourceForSeries1Values);
series1.setName("Series1");
List<OneValueChartDataPoint> dataPoints1 = new ArrayList<OneValueChartDataPoint>();
OneValueChartDataPoint dataPoint11 = new OneValueChartDataPoint();
dataPoint11.setValue(40.0);
dataPoints1.add(dataPoint11);
OneValueChartDataPoint dataPoint12 = new OneValueChartDataPoint();
dataPoint12.setValue(50.0);
dataPoints1.add(dataPoint12);
OneValueChartDataPoint dataPoint13 = new OneValueChartDataPoint();
dataPoint13.setValueFormula("SUM(B2:B3)");
dataPoints1.add(dataPoint13);
series1.setDataPoints(dataPoints1);
seriesList.add(series1);
dto.setSeries(seriesList);
Chart chart = (Chart)api.createShape("MyPresentation.pptx", 1, dto, null, null, null, null, null, null);

System.out.println("Third data point value is: " + ((OneValueSeries)chart.getSeries().get(0)).getDataPoints().get(2).getValue().doubleValue());
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

$dto = new Chart();
$dto->setChartType('ClusteredColumn');
$dto->setWidth(400);
$dto->setHeight(300);

$categoryDataSource = new Workbook();
$categoryDataSource->setWorksheetIndex(0);
$categoryDataSource->setColumnIndex(0);
$categoryDataSource->setRowIndex(1);
$dto->setDataSourceForCategories($categoryDataSource);
$category1 = new ChartCategory();
$category1->setValue("Category 1");
$category2 = new ChartCategory();
$category2->setValue("Category 2");
$category3 = new ChartCategory();
$category3->setValue("Category 3");
$dto->setCategories([ $category1, $category2, $category3 ]);

$series1 = new OneValueSeries();
$series1NameDataSource = new Workbook();
$series1NameDataSource->setWorksheetIndex(0);
$series1NameDataSource->setColumnIndex(1);
$series1NameDataSource->setRowIndex(0);
$series1->setDataSourceForSeriesName($series1NameDataSource);
$values1DataSource = new Workbook();
$values1DataSource->setWorksheetIndex(0);
$values1DataSource->setColumnIndex(1);
$values1DataSource->setRowIndex(1);
$series1->setDataSourceForValues($values1DataSource);
$dataPoint11 = new OneValueChartDataPoint();
$dataPoint11->setValue(40);
$dataPoint12 = new OneValueChartDataPoint();
$dataPoint12->setValue(50);
$dataPoint13 = new OneValueChartDataPoint();
$dataPoint13->setValueFormula("SUM(B2:B3)");
$series1->setDataPoints([ $dataPoint11, $dataPoint12, $dataPoint13 ]);
$dto->setSeries([ $series1 ]);
$result = $api->createShape("MyPresentation.pptx", 1, $dto);
$dataPoint = $result->getSeries()[0]->getDataPoints()[2];
print("Third data point value is: " + $dataPoint->getValue());
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

chart = AsposeSlidesCloud::Chart.new
chart.chart_type = 'ClusteredColumn'
chart.width = 400
chart.height = 300

data_source_for_categories = AsposeSlidesCloud::Workbook.new
data_source_for_categories.worksheet_index = 0
data_source_for_categories.column_index = 0
data_source_for_categories.row_index = 1
chart.data_source_for_categories = data_source_for_categories
category1 = AsposeSlidesCloud::ChartCategory.new
category1.value = "Category1"
category2 = AsposeSlidesCloud::ChartCategory.new
category2.value = "Category2"
category3 = AsposeSlidesCloud::ChartCategory.new
category3.value = "Category3"
chart.categories = [category1, category2, category3]

series1 = AsposeSlidesCloud::OneValueSeries.new
data_source_for_series1_name = AsposeSlidesCloud::Workbook.new
data_source_for_series1_name.worksheet_index = 0
data_source_for_series1_name.column_index = 1
data_source_for_series1_name.row_index = 0
series1.data_source_for_series_name = data_source_for_series1_name    
series1.name = "Series1"
data_source_for_series1_values =  AsposeSlidesCloud::Workbook.new
data_source_for_series1_values.worksheet_index = 0
data_source_for_series1_values.column_index = 1
data_source_for_series1_values.row_index = 1
series1.data_source_for_values = data_source_for_series1_values
point11 = AsposeSlidesCloud::OneValueChartDataPoint.new
point11.value = 40
point12 = AsposeSlidesCloud::OneValueChartDataPoint.new
point12.value = 50
point13 = AsposeSlidesCloud::OneValueChartDataPoint.new
point13.value_formula = "SUM(B2:B3)"
series1.data_points = [point11, point12, point13]
chart.series = [ series1 ]
result = api.create_shape("MyPresentation.ppx", 1, chart)

print "Third data point value is: " + result.series[0].data_points[2].value
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

chart = Chart()
chart.chart_type = 'ClusteredColumn'
chart.width = 400
chart.height = 300

categories_data_source = Workbook()
categories_data_source.worksheet_index = 0
categories_data_source.row_index = 1
categories_data_source.column_index = 0
chart.data_source_for_categories = categories_data_source
category1 = ChartCategory()
category1.value = "Category1"
category2 = ChartCategory()
category2.value = "Category2"
category3 = ChartCategory()
category3.value = "Category3"
chart.categories = [category1, category2, category3]

series1 = OneValueSeries()
series1_name_data_source = Workbook()
series1_name_data_source.worksheet_index = 0
series1_name_data_source.column_index = 1
series1_name_data_source.row_index = 0
series1.data_source_for_series_name = series1_name_data_source
series1.name = "Series1"
series1_values_data_source = Workbook()
series1_values_data_source.worksheet_index = 0
series1_values_data_source.column_index = 1
series1_values_data_source.row_index = 1
series1.data_source_for_values = series1_values_data_source
point11 = OneValueChartDataPoint()
point11.value = 40
point12 = OneValueChartDataPoint()
point12.value = 50
point13 = OneValueChartDataPoint()
point13.value_formula = "SUM(B2:B3)"
series1.data_points = [point11, point12, point13]
chart.series = [series1]
        
result = api.create_shape("MyPresentation.pptx", 1, chart)

print("Third data point value is: " + result.series[0].data_points[2].value)
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const chart = new model.Chart();
chart.chartType = model.Chart.ChartTypeEnum.ClusteredColumn;
chart.width = 400;
chart.height = 300;

const dataSourceForCategories = new model.Workbook();
dataSourceForCategories.worksheetIndex = 0;
dataSourceForCategories.columnIndex = 0;
dataSourceForCategories.rowIndex = 1;
chart.dataSourceForCategories = dataSourceForCategories;
chart.categories = [{value: "Category1"}, {value: "Category2"}, {value: "Category3"}];

const series1 = new model.OneValueSeries();
const dataSourceForSeriesName1 = new model.Workbook();
dataSourceForSeriesName1.worksheetIndex = 0;
dataSourceForSeriesName1.columnIndex = 1;
dataSourceForSeriesName1.rowIndex = 0;
series1.dataSourceForSeriesName = dataSourceForSeriesName1;
series1.name = "Series1";
const dataSourceForValues1 = new model.Workbook();
dataSourceForValues1.worksheetIndex = 0;
dataSourceForValues1.columnIndex = 1;
dataSourceForValues1.rowIndex = 1;
series1.dataSourceForValues = dataSourceForValues1;
series1.dataPoints = [{value: 40}, {value: 50}, {valueFormula: "SUM(B2:B3)"}];      
chart.series = [series1];
                
let result = await api.createShape("MyPresentation.pptx", 1, chart);
console.log("Third data point value is: " + series.dataPoints[2].value);
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

chart := slidescloud.NewChart()
chart.ChartType = "ClusteredColumn"
chart.Width = 400
chart.Height = 300

dataSourceForCategories := slidescloud.NewWorkbook()
dataSourceForCategories.WorksheetIndex = 0
dataSourceForCategories.ColumnIndex = 0
dataSourceForCategories.RowIndex = 1
chart.DataSourceForCategories = dataSourceForCategories
category1 := slidescloud.NewChartCategory()
category1.Value = "Category1"
category2 := slidescloud.NewChartCategory()
category2.Value = "Category2"
category3 := slidescloud.NewChartCategory()
category3.Value = "Category3"
chart.Categories = []slidescloud.IChartCategory{category1, category2, category3}

series1 := slidescloud.NewOneValueSeries()
dataSourceForSeries1Name := slidescloud.NewWorkbook()
dataSourceForSeries1Name.WorksheetIndex = 0
dataSourceForSeries1Name.ColumnIndex = 1
dataSourceForSeries1Name.RowIndex = 0
series1.DataSourceForSeriesName = dataSourceForSeries1Name
series1.Name = "Series1"
dataSourceForSeries1Values := slidescloud.NewWorkbook()
dataSourceForSeries1Values.WorksheetIndex = 0
dataSourceForSeries1Values.ColumnIndex = 1
dataSourceForSeries1Values.RowIndex = 1
series1.DataSourceForValues = dataSourceForSeries1Values
point11 := slidescloud.NewOneValueChartDataPoint()
point11.Value = 40
point12 := slidescloud.NewOneValueChartDataPoint()
point12.Value = 50
point13 := slidescloud.NewOneValueChartDataPoint()
point13.ValueFormula = "SUM(B2:B3)"
series1.DataPoints = []slidescloud.IOneValueChartDataPoint{point11, point12, point13}
chart.Series = []slidescloud.ISeries{series1}

fileName := "MyPresentation.pptx"
result, _, e := api.CreateShape(fileName, 1, chart, nil, nil, "", "", "", "")
	
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

dataPoint := result.(slidescloud.IChart).GetSeries()[0].(slidescloud.IOneValueSeries).GetDataPoints()[2]
fmt.Printf("Third data point value is: " + dataPoint.GetValue())
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Chart;
use AsposeSlidesCloud::Object::OneValueSeries;
use AsposeSlidesCloud::Object::Workbook;
use AsposeSlidesCloud::Object::Literals;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $dto = AsposeSlidesCloud::Object::Chart->new();
$dto->{chart_type} = "ClusteredColumn";
$dto->{width} = 400;
$dto->{height} = 300;

my $data_source_for_categories = AsposeSlidesCloud::Object::Workbook->new();
$data_source_for_categories->{worksheet_index} = 0;
$data_source_for_categories->{column_index} = 0;
$data_source_for_categories->{row_index} = 1;
$dto->{data_source_for_categories} = $data_source_for_categories;
my $category1 = AsposeSlidesCloud::Object::ChartCategory->new();
$category1->{value} = "Category1";
my $category2 = AsposeSlidesCloud::Object::ChartCategory->new();
$category2->{value} = "Category2";
my $category3 = AsposeSlidesCloud::Object::ChartCategory->new();
$category3->{value} = "Category3";
my @categories = ( $category1, $category2, $category3 );

my $series1 = AsposeSlidesCloud::Object::OneValueSeries->new();
my $data_source_for_series1_name = AsposeSlidesCloud::Object::Workbook->new();
$data_source_for_series1_name->{worksheet_index} = 0;
$data_source_for_series1_name->{column_index} = 1;
$data_source_for_series1_name->{row_index} = 0;
$series1->{data_source_for_series_name} = $data_source_for_series1_name;
$series1->{name} = "Series1";
my $data_source_for_series1_values = AsposeSlidesCloud::Object::Workbook->new();
$data_source_for_series1_values->{worksheet_index} = 0;
$data_source_for_series1_values->{column_index} = 1;
$data_source_for_series1_values->{row_index} = 1;
$series1->{data_source_for_values} = $data_source_for_series1_values;
my $point11 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point11->{value} = 40;
my $point12 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point12->{value} = 50;
my $point13 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$point13->{value_formula} = "SUM(B2:B3)";
my @points1 = ( $point11, $point12, $point13 );
$series1->{data_points} = \@points1;
my @series = ( $series1 );
$dto->{series} = \@series;
$dto->{categories} = \@categories;
my %params = ('name' => 'MyPresentation.pptx', 'slide_index' => 1, 'dto' => $dto);
my $chart = $api->create_shape(%params);
print "Third data point value is: " + $chart->{series}[0]{data_points}[2]->{value};
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)