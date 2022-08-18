---
title: "Update Chart Series Groups"
type: docs
url: /update-chart-series-groups/
weight: 40
---
## **Introduction**

A group of series contains series properties that are common for each series in the group. Series groups are generated automatically based on types of series contained in the chart object. Aspose.Slide Cloud allows to obtain such groups and update their properties.

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/seriesGroup/{seriesGroupIndex}|PUT|Update chart series group|[SetChartSeriesGroup]()
### **cURL Example**
The code example below shows how to update a chart series group. 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
```sh
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/seriesGroup/1" -d @"seriesGroup.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
```

seriesGroup.json
```json
{
	"Overlap": 10
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns chart info.

```

{{< /tab >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
ChartSeriesGroup seriesGroup = new ChartSeriesGroup()
{
    Overlap = 10
};

int slideIndex = 3;
int shapeIndex = 1;
int seriesGroupIndex = 1;

Chart chart = api.SetChartSeriesGroup("MyPresentation.pptx", slideIndex, shapeIndex, seriesGroupIndex, seriesGroup);

Console.WriteLine($"The chart has {chart.SeriesGroups.Count} series groups.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ChartSeriesGroup seriesGroup = new ChartSeriesGroup();
seriesGroup.setOverlap(10);

int slideIndex = 3;
int shapeIndex = 1;
int seriesGroupIndex = 1;

Chart chart = api.setChartSeriesGroup("MyPresentation.pptx", slideIndex, shapeIndex, seriesGroupIndex, seriesGroup, null, null, null);

System.out.println("The chart has  \"" + chart.getSeriesGroups().size() + "\" series groups.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ChartSeriesGroup;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$chartSeriesGroup = new ChartSeriesGroup();
$chartSeriesGroup-> setOverlap(10);

$slideIndex = 3;
$shapeIndex = 1;
$seriesGroupIndex = 1;

$chart = $api->setChartSeriesGroup("MyPresentation.pptx", $slideIndex, $shapeIndex, $seriesGroupIndex, $chartSeriesGroup);
print("The chart has " . count($chart->getSeriesGroups()) . " sereis groups.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

#Code example will be added soon.
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

series_group = ChartSeriesGroup()
series_group.overlap = 10

slide_index = 3
shape_index = 1
series_group_index = 1

chart = api.set_chart_series_group("MyPresentation.pptx", slide_index, shape_index, series_group_index, series_group)
print("The chart contains \"" + len(chart.series_groups) + "\" series groups.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let seriesGroup = new CloudSdk.ChartSeriesGroup();
seriesGroup.overlap = 10;

const slideIndex = 3;
const shapeIndex = 1;
const seriesGroupIndex = 1;

const result = await api.setChartSeriesGroup("MyPresentation.pptx", slideIndex, shapeIndex, seriesGroupIndex, seriesGroup);
console.log("The chart contains \"" + result.body.seriesGroups.length + "\" series groups.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

//Code example will be added soon.
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

#Code example will be added soon.
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}