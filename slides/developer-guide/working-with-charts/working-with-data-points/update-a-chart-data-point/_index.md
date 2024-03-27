---
title: "Update a Chart Data Point"
type: docs
url: /update-a-chart-data-point/
weight: 30
---

## **Introduction**

In PowerPoint presentations, data points are individual values or specific pieces of data that are plotted on a chart. Each data point represents a particular value within a dataset and is typically represented graphically as a marker, bar, line, or other visual element on the chart. Use the following method to update data points of a chart in presentations.

## **UpdateChartDataPoint**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/series/{seriesIndex}/dataPoints/{pointIndex}|PUT|Updates a data point of a chart in a presentation saved in a storage.|[UpdateChartDataPoint](https://reference.aspose.cloud/slides/#/Chart/UpdateChartDataPoint)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape (must be a chart).|
|seriesIndex|integer|path|true|The 1-based index of a data series.|
|pointIndex|integer|path|true|The 1-based index of a data point.|
|dataPoint|`DataPoint`|body|true|The data transfer object of the data point.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

In the **default** storage, the document **MyPresentation.pptx** contains a scatter chart (the **second** shape) that displays the number of items sold for quarters 1 through 4 (**one** data series). Update the sales value for the **4th** quarter to **35** items.

{{% alert color="primary" %}}
The referenced shape must be a chart, otherwise the operation will fail.
{{% /alert %}}

![Sales chart](input.png)

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/series/1/dataPoints/4" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @DataPoint.json
```

DataPoint.json content:
```json
{
  "xValue": 4,
  "yValue": 35
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```text
Code: 200
Body: Chart JSON
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int shapeIndex = 2;
        int seriesIndex = 1;
        int pointIndex = 4;

        ScatterChartDataPoint dataPoint = new ScatterChartDataPoint
        {
            XValue = 4,
            YValue = 35,
        };

        Chart chart = slidesApi.UpdateChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex, dataPoint);

        ScatterSeries series = (ScatterSeries)chart.Series[0];
        int dataPointCount = series.DataPoints.Count;
        Console.WriteLine("Number of data points: " + dataPointCount);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ScatterChartDataPoint;
import com.aspose.slides.model.Chart;
import com.aspose.slides.model.ScatterSeries;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int shapeIndex = 2;
        int seriesIndex = 1;
        int pointIndex = 4;

        ScatterChartDataPoint dataPoint = new ScatterChartDataPoint();
        dataPoint.setXvalue(4d);
        dataPoint.setYvalue(35d);

        Chart chart = slidesApi.updateChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex, dataPoint, null, null, null);

        ScatterSeries series = (ScatterSeries)chart.getSeries().get(0);
        int dataPointCount = series.getDataPoints().size();
        System.out.println("Number of data points: " + dataPointCount);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ScatterChartDataPoint;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$seriesIndex = 1;
$pointIndex = 4;

$dataPoint = new ScatterChartDataPoint();
$dataPoint->setXvalue(4);
$dataPoint->setYvalue(35);

$chart = $slidesApi->updateChartDataPoint($fileName, $slideIndex, $shapeIndex, $seriesIndex, $pointIndex, $dataPoint);

$dataPointCount = count($chart->getSeries()[0]->getDataPoints());
echo "Number of data points: ", $dataPointCount;
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
series_index = 1
point_index = 4

data_point = ScatterChartDataPoint.new
data_point.x_value = 4
data_point.y_value = 35

chart = slides_api.update_chart_data_point(file_name, slide_index, shape_index, series_index, point_index, data_point)

data_point_count = chart.series[0].data_points.length()
print "Number of data points: ", data_point_count
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.scatter_chart_data_point import ScatterChartDataPoint

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
series_index = 1
point_index = 4

data_point = ScatterChartDataPoint()
data_point.x_value = 4
data_point.y_value = 35

chart = slides_api.update_chart_data_point(file_name, slide_index, shape_index, series_index, point_index, data_point)

data_point_count = len(chart.series[0].data_points)
print("Number of data points:", data_point_count)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
shapeIndex = 2;
seriesIndex = 1;
pointIndex = 4;

dataPoint = new cloudSdk.ScatterChartDataPoint();
dataPoint.xValue = 4;
dataPoint.yValue = 35;

slidesApi.updateChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex, dataPoint).then(chart => {
    dataPointCount = chart.body.series[0].dataPoints.length;
    console.log("Number of data points:", dataPointCount);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/ScatterSeries.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;
    int shapeIndex = 2;
    int seriesIndex = 1;
    int pointIndex = 4;

    std::shared_ptr<ScatterChartDataPoint> dataPoint = std::make_shared<ScatterChartDataPoint>();
    dataPoint->setXValue(4);
    dataPoint->setYValue(35);

    std::shared_ptr<Chart> chart = slidesApi->updateChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex, dataPoint).get();

    std::shared_ptr<ScatterSeries> series = std::static_pointer_cast<ScatterSeries>(chart->getSeries()[0]);
    int dataPointCount = series->getDataPoints().size();
    std::wcout << L"Number of data points: " << dataPointCount;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::ScatterChartDataPoint;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $shape_index = 2;
my $series_index = 1;
my $point_index = 4;

my $data_point = AsposeSlidesCloud::Object::ScatterChartDataPoint->new();
$data_point->{x_value} = 4;
$data_point->{y_value} = 35;

my $chart = $slides_api->update_chart_data_point(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, series_index => $series_index, point_index => $point_index, data_point => $data_point);

my $data_point_count = @{$chart->{series}[0]->{data_points}};
print("Number of data points: ", $data_point_count);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
import (
	"fmt"

	asposeslidescloud "github.com/aspose-slides-cloud/aspose-slides-cloud-go/v24"
)

func main() {
	configuration := asposeslidescloud.NewConfiguration()
	configuration.AppSid = "MyClientId"
	configuration.AppKey = "MyClientSecret"

	slidesApi := asposeslidescloud.NewAPIClient(configuration).SlidesApi

	var fileName = "MyPresentation.pptx"
	var slideIndex int32 = 1
	var shapeIndex int32 = 2
	var seriesIndex int32 = 1
	var pointIndex int32 = 4

	dataPoint := asposeslidescloud.NewScatterChartDataPoint()
	dataPoint.XValue = 4
	dataPoint.YValue = 35

	chart, _, _ := slidesApi.UpdateChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex, dataPoint, "", "", "")

	series := chart.GetSeries()[0].(asposeslidescloud.IScatterSeries)
	dataPointCount := len(series.GetDataPoints())
	fmt.Print("Number of data points: ", dataPointCount)
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![Sales chart](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
