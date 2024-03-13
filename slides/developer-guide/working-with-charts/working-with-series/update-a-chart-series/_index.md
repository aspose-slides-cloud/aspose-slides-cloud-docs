---
title: "Update a Chart Series"
type: docs
url: /update-a-chart-series/
weight: 30
---

## **Introduction**

In PowerPoint documents, chart series refer to the data sets or groups of related data points that are plotted on a chart. A chart series typically consists of a collection of data points that represent a particular category or set of values. PowerPoint supports various types of charts, such as bar charts, line charts, pie charts, and more, and each of these chart types can have one or multiple series. Use the following method to update a data series in a chart. 

## **UpdateChartSeries**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/series/{seriesIndex}|PUT|Updates a data series of a chart in a presentation saved in a storage.|[UpdateChartSeries](https://apireference.aspose.cloud/slides/#/Chart/UpdateChartSeries)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape (must be a chart).|
|seriesIndex|integer|path|true|The 1-based index of a data series.|
|series|`Series`|body|true|The data transfer object with a series of data.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

The document **MyPresentation.pptx**, saved in the **default** storage, contains a chart (the **second** shape) with three lines on the **first** slide - sales volumes of products "Product A", "Product B", "Product C" for 2021 to 2023. Update the sales volumes of **Product C** to (**25**, **30**, **30**) for the same years.

{{% alert color="primary" %}}
The referenced shape must be a chart, otherwise the operation will fail.
{{% /alert %}}

![The sales chart](input.png)

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Update the Data Series**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/series/3" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @DataSeries.json
```

DataSeries.json content:
```json
{
  "DataPointType": "OneValue",
  "DataPoints": [
    { "Value": 25 },
    { "Value": 30 },
    { "Value": 30 }
  ]
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
using System.Collections.Generic;

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
        int seriesIndex = 3;

        OneValueSeries dataSeries = new OneValueSeries
        {
            DataPoints = new List<OneValueChartDataPoint>
            {
                new OneValueChartDataPoint { Value = 25 },
                new OneValueChartDataPoint { Value = 30 },
                new OneValueChartDataPoint { Value = 30 }
            }
        };

        Chart chart = slidesApi.UpdateChartSeries(fileName, slideIndex, shapeIndex, seriesIndex, dataSeries);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.OneValueChartDataPoint;
import com.aspose.slides.model.OneValueSeries;
import com.aspose.slides.model.Chart;

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int shapeIndex = 2;
        int seriesIndex = 3;

        OneValueChartDataPoint dataPoint1 = new OneValueChartDataPoint();
        dataPoint1.setValue(25d);

        OneValueChartDataPoint dataPoint2 = new OneValueChartDataPoint();
        dataPoint2.setValue(30d);

        OneValueChartDataPoint dataPoint3 = new OneValueChartDataPoint();
        dataPoint3.setValue(30d);

        OneValueSeries dataSeries = new OneValueSeries();
        dataSeries.setDataPoints(Arrays.asList(dataPoint1, dataPoint2, dataPoint3));

        Chart chart = slidesApi.updateChartSeries(fileName, slideIndex, shapeIndex, seriesIndex, dataSeries, null, null, null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\OneValueChartDataPoint;
use Aspose\Slides\Cloud\Sdk\Model\OneValueSeries;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$seriesIndex = 3;

$dataPoint1 = new OneValueChartDataPoint();
$dataPoint1->setValue(25);

$dataPoint2 = new OneValueChartDataPoint();
$dataPoint2->setValue(30);

$dataPoint3 = new OneValueChartDataPoint();
$dataPoint3->setValue(30);

$dataSeries = new OneValueSeries();
$dataSeries->setDataPoints([$dataPoint1, $dataPoint2, $dataPoint3]);

$chart = $slidesApi->updateChartSeries($fileName, $slideIndex, $shapeIndex, $seriesIndex, $dataSeries);
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
series_index = 3

data_point1 = OneValueChartDataPoint.new
data_point1.value = 25

data_point2 = OneValueChartDataPoint.new
data_point2.value = 30

data_point3 = OneValueChartDataPoint.new
data_point3.value = 30

data_series = OneValueSeries.new
data_series.data_points = [data_point1, data_point2, data_point3]

chart = slides_api.update_chart_series(file_name, slide_index, shape_index, series_index, data_series)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.one_value_chart_data_point import OneValueChartDataPoint
from asposeslidescloud.models.one_value_series import OneValueSeries

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
series_index = 3

data_point1 = OneValueChartDataPoint()
data_point1.value = 25

data_point2 = OneValueChartDataPoint()
data_point2.value = 30

data_point3 = OneValueChartDataPoint()
data_point3.value = 30

data_series = OneValueSeries()
data_series.data_points = [data_point1, data_point2, data_point3]

chart = slides_api.update_chart_series(file_name, slide_index, shape_index, series_index, data_series)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
shapeIndex = 2;
seriesIndex = 3;

dataSeries = new cloudSdk.OneValueSeries();
dataSeries.dataPoints = [{ value: 25 }, { value: 30 }, { value: 30 }];

slidesApi.updateChartSeries(fileName, slideIndex, shapeIndex, seriesIndex, dataSeries).then(chart => {
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/OneValueSeries.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;
    int shapeIndex = 2;
    int seriesIndex = 3;

    std::shared_ptr<OneValueChartDataPoint> dataPoint1 = std::make_shared<OneValueChartDataPoint>();
    dataPoint1->setValue(25);

    std::shared_ptr<OneValueChartDataPoint> dataPoint2 = std::make_shared<OneValueChartDataPoint>();
    dataPoint2->setValue(30);

    std::shared_ptr<OneValueChartDataPoint> dataPoint3 = std::make_shared<OneValueChartDataPoint>();
    dataPoint3->setValue(30);

    std::shared_ptr<OneValueSeries> dataSeries = std::make_shared<OneValueSeries>();
    dataSeries->setDataPoints({ dataPoint1, dataPoint2, dataPoint3 });

    std::shared_ptr<Chart> chart = slidesApi->updateChartSeries(fileName, slideIndex, shapeIndex, seriesIndex, dataSeries).get();
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::OneValueChartDataPoint;
use AsposeSlidesCloud::Object::OneValueSeries;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $shape_index = 2;
my $series_index = 3;

my $data_point1 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$data_point1->{value} = 25;

my $data_point2 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$data_point2->{value} = 30;

my $data_point3 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$data_point3->{value} = 30;

my $data_series = AsposeSlidesCloud::Object::OneValueSeries->new();
$data_series->{data_points} = [$data_point1, $data_point2, $data_point3];

my $chart = $slides_api->create_chart_series(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, series_index => $series_index, series => $data_series);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"

api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
slideIndex := 1
shapeIndex := 2
seriesIndex := 3

dataPoint1 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint1.Value = 25

dataPoint2 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint2.Value = 30

dataPoint3 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint3.Value = 30

dataSeries := asposeslidescloud.NewOneValueSeries()
dataSeries.DataPoints = []asposeslidescloud.IOneValueChartDataPoint { dataPoint1, dataPoint2, dataPoint3 }

result, _, e := api.SlidesApi.UpdateChartSeries(fileName, slideIndex, shapeIndex, seriesIndex, dataSeries, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![The sales chart](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project
