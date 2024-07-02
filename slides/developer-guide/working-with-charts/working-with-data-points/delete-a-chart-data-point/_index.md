---
title: "Delete a Chart Data Point"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- chart
- chart data
- data point
- chart data point
- remove a data point
type: docs
url: /delete-a-chart-data-point/
weight: 20
---

## **Introduction**

In PowerPoint presentations, data points are the individual values or pieces of data represented on a chart. They visually depict specific information such as numerical values, percentages, or other quantitative data. Use the following method to delete data points from a chart in a presentation.

## **DeleteChartDataPoint**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/series/{seriesIndex}/dataPoints/{pointIndex}|DELETE|Deletes a data point from a chart in a presentation saved in a storage.|[DeleteChartDataPoint](https://apireference.aspose.cloud/slides/#/Chart/DeleteChartDataPoint)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape (must be a chart).|
|seriesIndex|integer|path|true|The 1-based index of a data series.|
|pointIndex|integer|path|true|The 1-based index of a data point.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

In the **default** storage, the document **MyPresentation.pptx** contains a scatter chart (the **second** shape) that displays the number of items sold for quarters 1 through 4 (**one** data series). Delete data for the **3th** quarter.

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

**Delete the Data**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/series/1/dataPoints/3" \
     -H "authorization: Bearer MyAccessToken"
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
        int pointIndex = 3;

        Chart chart = slidesApi.DeleteChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex);

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
import com.aspose.slides.model.Chart;
import com.aspose.slides.model.ScatterSeries;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int shapeIndex = 2;
        int seriesIndex = 1;
        int pointIndex = 3;

        Chart chart = slidesApi.deleteChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex, null, null, null);

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

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$seriesIndex = 1;
$pointIndex = 3;

$chart = $slidesApi->deleteChartDataPoint($fileName, $slideIndex, $shapeIndex, $seriesIndex, $pointIndex);

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
point_index = 3

chart = slides_api.delete_chart_data_point(file_name, slide_index, shape_index, series_index, point_index)

data_point_count = chart.series[0].data_points.length()
print "Number of data points: ", data_point_count
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
series_index = 1
point_index = 3

chart = slides_api.delete_chart_data_point(file_name, slide_index, shape_index, series_index, point_index)

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
pointIndex = 3;

slidesApi.deleteChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex).then(chart => {
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
    int pointIndex = 3;

    std::shared_ptr<Chart> chart = slidesApi->deleteChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex).get();

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

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $shape_index = 2;
my $series_index = 1;
my $point_index = 3;

my $chart = $slides_api->delete_chart_data_point(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, series_index => $series_index, point_index => $point_index);

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
	var pointIndex int32 = 3

	chart, _, _ := slidesApi.DeleteChartDataPoint(fileName, slideIndex, shapeIndex, seriesIndex, pointIndex, "", "", "")

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
