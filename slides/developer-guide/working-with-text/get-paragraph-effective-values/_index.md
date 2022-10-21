---
title: "Get Paragraph Effective Values"
type: docs
url: /get-paragraph-effective-values/
weight: 130
---
## **Introduction**

Effective values are format values that are actually applied to the paragraph. They are either explicitly set in the paragraph, or implicitly returned as a result of inheritance. They represent the final result of formatting that might be seen in the PowerPoint or in an exported document. For example, if the font height value is not defined for the specific portion of text, the value from the default portion format of the parent paragraph will be taken, if availiable. If not, the value is taken from the presentation theme.

You can also get effective values for [Portions](/slides/get-portion-effective-values/).

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/effective|GET|Get paragraph effective|[GetParagraphEffective]()|
/{name}/slides/{slideIndex}/shapes/{path}/{shapeIndex}/paragraphs/{paragraphIndex}/effective|GET|Get sub-shape paragraph effective|[GetSubshapeParagraphEffective]()|

### **cURL Example**

The code example below shows how to obtain "effective formatting values" from a paragraph.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Get paragraph effective format values**
```sh
curl -v -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs/1/effective" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
```

**Get sub-shape paragraph effective format values**
```sh
curl -v -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/shapes/2/paragraphs/1/effective" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns effective paragraph info.

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

int slideIndex = 1;
int shapeIndex = 1;
int paragraphIndex = 1;

Paragraph response = api.GetParagraphEffective("MyPresentation.pptx", slideIndex, shapeIndex, paragraphIndex);

Console.WriteLine($"The default tab size is \"{response.DefaultTabSize}\".");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

int slideIndex = 1;
int shapeIndex = 1;
int paragraphIndex = 1;

Paragraph response = api.getParagraphEffective("MyPresentation.pptx", slideIndex, shapeIndex, paragraphIndex, null, null, null, null);

System.out.println("The default tab size is \"" + response.getDefaultTabSize() + "\".");
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

$slideIndex = 1;
$shapeIndex = 1;
$paragraphIndex = 1;

$response = $api->getParagraphEffective("MyPresentation.pptx", $slideIndex, $shapeIndex, $paragraphIndex);
print("The default tab size is \"" . $response->getDefaultTabSize() . "\".");
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

slide_index = 1
shape_index = 1
paragraph_index = 1

response = api.get_paragraph_effective("MyPresentation.pptx", slide_index, shape_index, paragraph_index)
print(f"The default tab size is \"{ response.default_tab_size }\".")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const slideIndex = 1;
const shapeIndex = 1;
const paragraphIndex = 1;

const response = await api.getParagraphEffective("MyPresentation.pptx", slideIndex, shapeIndex, paragraphIndex);
console.log("The default tab size is \"" + response.body.defaultTabSize + "\".");
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