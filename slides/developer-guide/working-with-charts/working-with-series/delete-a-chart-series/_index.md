---
title: "Delete a Chart Series"
keywords: "PowerPoint, presentation, REST API, Cloud API, chart, chart data, chart series, data series, remove a data series"
type: docs
url: /delete-a-chart-series/
weight: 20
---

## **Introduction**

In Microsoft PowerPoint, chart series are used to represent and display data in graphical form. A chart series is a collection of related data points that are plotted on the chart. Use the following method to delete data series from a chart.

## **DeleteChartSeries**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/series/{seriesIndex}|DELETE|Deletes a data series from a chart in a presentation saved in a storage.|[DeleteChartSeries](https://apireference.aspose.cloud/slides/#/Chart/DeleteChartSeries)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape (must be a chart).|
|seriesIndex|integer|path|true|The 1-based index of a data series.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

The document **MyPresentation.pptx**, saved in the **default** storage, contains a chart (the **second** shape) with three lines on the **first** slide - sales volumes of products "Product A", "Product B", and "Product C" for 2021 to 2023. Delete the **third** data series ("Product C") from the chart.

{{% alert color="primary" %}}
The referenced shape must be a chart, otherwise the operation will fail.
{{% /alert %}}

![The line chart](input.png)

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Data Series**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/series/3" \
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
        int seriesIndex = 3;

        Chart chart = slidesApi.DeleteChartSeries(fileName, slideIndex, shapeIndex, seriesIndex);

        int seriesCount = chart.Series.Count;
        Console.WriteLine($"Number of data series: {seriesCount}");
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Chart;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int shapeIndex = 2;
        int seriesIndex = 3;

        Chart chart = slidesApi.deleteChartSeries(fileName, slideIndex, shapeIndex, seriesIndex, null, null, null);

        int seriesCount = chart.getSeries().size();
        System.out.println("Number of data series: " + seriesCount);
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
$seriesIndex = 3;

$chart = $slidesApi->deleteChartSeries($fileName, $slideIndex, $shapeIndex, $seriesIndex);

$seriesCount = count($chart->getSeries());
echo "Number of data series: ", $seriesCount;
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

chart = slides_api.delete_chart_series(file_name, slide_index, shape_index, series_index)

series_count = chart.series.length()
puts "Number of data series: #{series_count}"
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
series_index = 3

chart = slides_api.delete_chart_series(file_name, slide_index, shape_index, series_index)

series_count = len(chart.series)
print("Number of data series:", series_count)
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

slidesApi.deleteChartSeries(fileName, slideIndex, shapeIndex, seriesIndex).then(chart => {
    seriesCount = chart.body.series.length;
    console.log("Number of data series:", seriesCount);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;
    int shapeIndex = 2;
    int seriesIndex = 3;

    std::shared_ptr<Chart> chart = slidesApi->deleteChartSeries(fileName, slideIndex, shapeIndex, seriesIndex).get();

    int seriesCount = chart->getSeries().size();
    std::wcout << L"Number of data series: " << seriesCount;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $shape_index = 2;
my $series_index = 3;

my $chart = $slides_api->delete_chart_series(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, series_index => $series_index);

my $series_count = @{$chart->{series}};
print("Number of data series: ", $series_count);
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

result, _, e := api.SlidesApi.DeleteChartSeries(fileName, slideIndex, shapeIndex, seriesIndex, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("Number of data series: %v", len(result.(asposeslidescloud.IChart).GetSeries()))
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![The line chart](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
