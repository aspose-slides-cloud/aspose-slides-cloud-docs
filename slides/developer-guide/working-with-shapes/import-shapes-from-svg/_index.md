---
title: "Import Shapes From SVG"
type: docs
url: /import-shapes-from-svg/
weight: 170
---
## **Introduction**

Aspose.Slides for Cloud allows you importing shapes from the SVG file.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/fromSvg|POST|Imports shapes from SVG file.|[ImportShapesFromSvg](https://apireference.aspose.cloud/slides/#/Shapes/ImportShapesFromSvg)|

### **cURL Example**
The code example below shows how to import shapes by indexes from the SVG file and place the result in the specified area on the target slide.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Import shapes from SVG**
```sh
curl -v -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/5/shapes/fromSvg?x=50&y=50&width=300&height=300&shapes=1,3,5"\
-H "Authorization: Bearer [Access Token]"\
-F "file=@TestData/shapes.svg" \
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns shapes info.

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

int slideIndex = 5;

Stream file = File.OpenRead("shapes.svg");

Shapes response = api.ImportShapesFromSvg("MyPresentation.pptx", slideIndex, file, 50, 50, 300, 300, new List<int> { 1, 3, 5 });

Console.WriteLine("The slide contains " + response.ShapesLinks.Count + " shapes.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 5;
byte[] file = Files.readAllBytes("shapes.svg");

Shapes response = api.importShapesFromSvg("MyPresentation.pptx", slideIndex, file, 50, 50, 300, 300, Arrays.asList(1,3,5), null, null, null);

System.out.println("The slide contains " + response.getShapesLinks().size() + " shapes.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Shapes;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 5;
$file = fopen("shapes.svg", 'r');

$result = $api->importShapesFromSvg("MyPresentation.pptx", $slideIndex, $file, 50, 50, 300, 300, [1,2,3]);

print("The slide contains " + count($result->getShapesLinks()) + " shapes.");
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

slide_index = 5

with open("shapes.svg", 'rb') as f:
    source = f.read()

response = api.import_shapes_from_svg("MyPresentation.pptx", slide_index, source, 50, 50, 300, 300, [1, 3, 5])

print("The slide contains " +  len(response.shapes_links) + " shapes.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const slideIndex = 5;

const stream = fs.createReadStream("shapes.svg")
let result = await api.importShapesFromSvg("MyPresentation.pptx", slideIndex, stream, 50, 50, 300, 300, [1, 3, 5]);
            
console.log("The slide contains " +  response.body.shapesLinks.length + " shapes.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
var slideIndex int32 = 5
var x int32 = 50
var y int32 = 50
var width int32 = 300
var height int32 = 300

document, e := ioutil.ReadFile("shapes.svg")
shapes := []int32{1, 3, 5}

response, _, e := api.ImportShapesFromSvg(fileName, slideIndex, document, &x, &y, &width, &height, shapes, "", "", "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

 fmt.Printf("The slide contains " + len(response.GetShapesLinks()) + " shapes.")
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