---
title: "Text Highlighting"
type: docs
url: /text-highlighting/
weight: 100
---

## **Introduction**
1
You can use **highlightText** or **highlightRegex** methods of shape resource to highlight text in a shape.
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{slideIndex}/shapes/{shapeIndex}/highlightText|POST|Highlight text in a shape|[HighlightShapeText](https://apireference.aspose.cloud/slides/#/Text/HighlightShapeRegex)|
|/slides/{slideIndex}/shapes/{shapeIndex}/highlightRegex|POST|Highlight text in a shape using a regular expression|[HighlightShapeRegex](https://apireference.aspose.cloud/slides/#/Text/HighlightShapeRegex)|

### **cURL Example**

{{% alert color="primary" %}} 

We are using the **highlightText** resource as an example below.

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl -v "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/highlightText?text=important&color=00FF0000" -d "" -H "Authorization: Bearer MyAuthToken"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

The shape info.

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Shape result = api.HighlightShapeText("MyPresentation.pptx", 2, 1, "important", "00FF0000");
Console.WriteLine(result.Text);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Shape result = api.highlightShapeText("MyPresentation.pptx", 2, 1, "important", "00FF0000", null, null, null, null, null);
System.out.println(result.getText());
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
$result = $api->HighlightShapeText("MyPresentation.pptx", 2, 1, "important", "00FF0000");
print($result->getText());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)
result = api.highlight_shape_text("MyPresentation.pptx", 2, 1, "important", "00FF0000")
p(result.text)
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

result = api.highlight_shape_text("MyPresentation.pptx", 2, 1, "important", "00FF0000")
print(result.text)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
api.highlightShapeText("MyPresentation.pptx", 2, 1, "important", "00FF0000").then((response) => {
    console.log(response.body.text);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

result, _, e := c.SlidesApi.HighlightShapeText("MyPresentation.pptx", 2, 1, "important", "00FF0000", nil, nil, "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf(result.(IShape).getText())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
