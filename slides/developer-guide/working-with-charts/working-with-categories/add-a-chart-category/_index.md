---
title: "Add a Chart Category"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- chart
- chart data
- chart category
- add chart data
type: docs
url: /add-a-chart-category/
weight: 10
---

## **Introduction**

In PowerPoint documents, data for charts is usually organized in a table consisting of series and categories of data. Use the following method to add data categories to a presentation chart. You provide data points that will be added to a respective data series for the category.

## **CreateChartCategory**

### **API Information**
 
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/categories|POST|Adds a data category to a chart in a presentation saved in a storage.|[CreateChartCategory](https://apireference.aspose.cloud/slides/#/Chart/CreateChartCategory)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape (must be a chart).|
|category|`ChartCategory`|body|true|The data transfer object with category data.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

The document **MyPresentation.pptx**, saved in the **default** storage, contains a column chart (the **second** shape) on the **first** slide - sales volumes of products "Product A", "Product B", and "Product C" for 2021 to 2022. Add sales data (**30**, **35**, **25**) for 2023.

{{% alert color="primary" %}}
The referenced shape must be a chart that supports categories (e.g. column or pie chart), otherwise the operation will fail.
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

**Add the Data Category**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/categories" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @DataCategory.json
```

DataCategory.json content:
```json
{
  "value": "2023",
  "dataPoints": [
    { "value": 30 },
    { "value": 35 },
    { "value": 25 }
  ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```text
Code: 201
Body: Chart JSON
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using System.Collections.Generic;

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string fileName = "MyPresentation.pptx";
        int slideIndex = 3;
        int shapeIndex = 1;

        ChartCategory dataCategory = new ChartCategory
        {
            Value = "2023",
            DataPoints = new List<OneValueChartDataPoint>
            {
                new OneValueChartDataPoint { Value = 30 },
                new OneValueChartDataPoint { Value = 35 },
                new OneValueChartDataPoint { Value = 25 }
            }
        };

        Chart chart = slidesApi.CreateChartCategory(fileName, slideIndex, shapeIndex, dataCategory);

        int categoryCount = chart.Categories.Count;
        Console.WriteLine($"Number of data categories: {categoryCount}");
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.OneValueChartDataPoint;
import com.aspose.slides.model.ChartCategory;
import com.aspose.slides.model.Chart;

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 3;
        int shapeIndex = 1;

        OneValueChartDataPoint dataPoint1 = new OneValueChartDataPoint();
        dataPoint1.setValue(30d);

        OneValueChartDataPoint dataPoint2 = new OneValueChartDataPoint();
        dataPoint2.setValue(35d);

        OneValueChartDataPoint dataPoint3 = new OneValueChartDataPoint();
        dataPoint3.setValue(25d);

        ChartCategory dataCategory = new ChartCategory();
        dataCategory.setValue("2023");
        dataCategory.setDataPoints(Arrays.asList(dataPoint1, dataPoint2, dataPoint3));

        Chart chart = slidesApi.createChartCategory(fileName, slideIndex, shapeIndex, dataCategory, null, null, null);

        int categoryCount = chart.getCategories().size();
        System.out.printf("Number of data categories: %d", categoryCount);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\OneValueChartDataPoint;
use Aspose\Slides\Cloud\Sdk\Model\ChartCategory;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 3;
$shapeIndex = 1;

$dataPoint1 = new OneValueChartDataPoint();
$dataPoint1->setValue(30);

$dataPoint2 = new OneValueChartDataPoint();
$dataPoint2->setValue(35);

$dataPoint3 = new OneValueChartDataPoint();
$dataPoint3->setValue(25);

$dataCategory = new ChartCategory();
$dataCategory->setValue("2023");
$dataCategory->setDataPoints([$dataPoint1, $dataPoint2, $dataPoint3]);

$chart = $slidesApi->createChartCategory($fileName, $slideIndex, $shapeIndex, $dataCategory);

$categoryCount = count($chart->getCategories());
echo "Number of data categories: ", $categoryCount;
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
slide_index = 3
shape_index = 1

data_point1 = OneValueChartDataPoint.new
data_point1.value = 30

data_point2 = OneValueChartDataPoint.new
data_point2.value = 35

data_point3 = OneValueChartDataPoint.new
data_point3.value = 25

data_category = ChartCategory.new
data_category.value = "2023"
data_category.data_points = [data_point1, data_point2, data_point3]

chart = slides_api.create_chart_category(file_name, slide_index, shape_index, data_category)

category_count = chart.categories.length()
puts "Number of data categories: #{category_count}"
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.one_value_chart_data_point import OneValueChartDataPoint
from asposeslidescloud.models.chart_category import ChartCategory

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 3
shape_index = 1

data_point1 = OneValueChartDataPoint()
data_point1.value = 30

data_point2 = OneValueChartDataPoint()
data_point2.value = 35

data_point3 = OneValueChartDataPoint()
data_point3.value = 25

data_category = ChartCategory()
data_category.value = "2023"
data_category.data_points = [data_point1, data_point2, data_point3]

chart = slides_api.create_chart_category(file_name, slide_index, shape_index, data_category)

category_count = len(chart.categories)
print(f"Number of data categories: {category_count}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 3;
shapeIndex = 1;

dataCategory = new cloudSdk.ChartCategory();
dataCategory.value = "2023";
dataCategory.dataPoints = [{ value: 30 }, { value: 35 }, { value: 25 }];

slidesApi.createChartCategory(fileName, slideIndex, shapeIndex, dataCategory).then(chart => {
    categoryCount = chart.body.categories.length;
    console.log("Number of data categories:", categoryCount);
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
    int slideIndex = 3;
    int shapeIndex = 1;

    std::shared_ptr<OneValueChartDataPoint> dataPoint1 = std::make_shared<OneValueChartDataPoint>();
    dataPoint1->setValue(30);

    std::shared_ptr<OneValueChartDataPoint> dataPoint2 = std::make_shared<OneValueChartDataPoint>();
    dataPoint2->setValue(35);

    std::shared_ptr<OneValueChartDataPoint> dataPoint3 = std::make_shared<OneValueChartDataPoint>();
    dataPoint3->setValue(25);

    std::shared_ptr<ChartCategory> dataCategory = std::make_shared<ChartCategory>();
    dataCategory->setValue(L"2023");
    dataCategory->setDataPoints({ dataPoint1, dataPoint2, dataPoint3 });

    std::shared_ptr<Chart> chart = slidesApi->createChartCategory(fileName, slideIndex, shapeIndex, dataCategory).get();

    int categoryCount = chart->getCategories().size();
    std::wcout << L"Number of data categories: " << categoryCount;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::OneValueChartDataPoint;
use AsposeSlidesCloud::Object::ChartCategory;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 3;
my $shape_index = 1;

my $data_point1 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$data_point1->{value} = 30;

my $data_point2 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$data_point2->{value} = 35;

my $data_point3 = AsposeSlidesCloud::Object::OneValueChartDataPoint->new();
$data_point3->{value} = 25;

my $data_category = AsposeSlidesCloud::Object::ChartCategory->new();
$data_category->{value} = "2023";
$data_category->{data_points} = [$data_point1, $data_point2, $data_point3];

$chart = $slides_api->create_chart_category(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, category => $data_category);

$category_count = @{$chart->{categories}};
print("Number of data categories: ", $category_count);
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
slideIndex := 3
shapeIndex := 1

dataPoint1 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint1.Value = 30

dataPoint2 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint2.Value = 35

dataPoint3 := asposeslidescloud.NewOneValueChartDataPoint()
dataPoint3.Value = 25

dataCategory := asposeslidescloud.NewChartCategory()
dataCategory.Value = "2023"
dataCategory.DataPoints = []asposeslidescloud.IOneValueChartDataPoint { dataPoint1, dataPoint2, dataPoint3 }

result, _, e := api.SlidesApi.CreateChartCategory(fileName, slideIndex, shapeIndex, dataCategory, "", "", "")

if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("Number of data categories: %v", len(result.(asposeslidescloud.IChart).GetSeries()))
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![Sales chart](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
