---
title: "Get a Rectangle of a Text Portion"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- text
- rectangle
- text bounds
- get bounds
- coordinates
- text width
- text height
type: docs
url: /get-a-rectangle-of-a-text-portion/
weight: 130
---
## **Introduction**

The article shows how to obtain coordinates of the rectangle that bounds portion using Aspose.Slides Cloud.

There is [a similar method](/slides/get-a-paragraph-rectangle/) to get rectangle coordinates for a paragraph.

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}/bounds|GET|Returns coordinates of rect that bounds portion|[GetPortionRectangle]()|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```
```sh

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/1/portions/1/bounds" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```
{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Code: 200
Returns rectangle info.

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
TextBounds response = api.GetPortionRectangle("MyPresentation.pptx", 1, 2, 1, 1);
Console.WriteLine($"x: {response.X}");
Console.WriteLine($"y: {response.Y}");
Console.WriteLine($"width: {response.Width}");
Console.WriteLine($"height: {response.Height}");
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
TextBounds response = api.getPortionRectangle("MyPresentation.pptx", 1, 2, 1, 1, null, null, null);
System.out.println("x: " + response.getX());
System.out.println("y: " + response.getY());
System.out.println("width: " + response.getWidth());
System.out.println("height: " + response.getHeight());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$response = $api->GetPortionRectangle("MyPresentation.pptx", 1, 2, 1, 1);
print("x: " . $response->getX());
print("y: " . $response->getY());
print("width: " . $response->getWidth());
print("height: " . $response->getHeight());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)
response = api.get_portion_rectangle("MyPresentation.pptx", 1, 2, 1, 1)
p("x: #{ response.x }")
p("y: #{ response.y }")
p("width: #{ response.width }")
p("height: #{ response.height }")
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

response = api.get_portion_rectangle("MyPresentation.pptx", 1, 2, 1, 1)
print(f"x: { response.x }")
print(f"y: { response.y }")
print(f"width: { response.width }")
print(f"height: { response.height }")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
api.getPortionRectangle("MyPresentation.pptx", 1, 2, 1, 1).then(response => {
    console.log("x: " + response.body.x);
    console.log("y: " + response.body.y);
    console.log("width: " + response.body.width);
    console.log("height: " + response.body.height);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)
response, _, e := api.SlidesApi.GetPortionRectangle("MyPresentation.pptx", 1, 2, 1, 1, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("x: %v\ny: %v\nwidth: %v\nheight: %v\n", response.(asposeslidescloud.ITextBounds).GetX(), response.(asposeslidescloud.ITextBounds).GetY(), response.(asposeslidescloud.ITextBounds).GetWidth(), response.(asposeslidescloud.ITextBounds).GetHeight())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);
my %params = ('name' => 'MyPresentation.pptx', 'slide_index' => 1, 'shape_index' => 2, 'paragraph_index' => 1, 'portion_index' => 1);
my $response = $api->get_portion_rectangle(%params);
print "X: $response->{x}\nY: $response->{y}\nWidth: $response->{width}\nHeight: $response->{height}\n";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
