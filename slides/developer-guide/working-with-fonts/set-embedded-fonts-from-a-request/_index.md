---
title: "Set Embedded Fonts from a Request"
type: docs
url: /set-embedded-fonts-from-a-request/
weight: 40
---
## **Introduction**
Aspose.Slides Cloud API allows embedding a font used in a presentation. The font can be provided in the request body if needed. The feature can be applied to presentations located in the storage or presentations uploaded in the request body along with the font file.

## **SetEmbeddedFontFromRequest**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/fonts/embedded|POST|Embeds font from request and returns presentation fonts info.|[SetEmbeddedFontFromRequest](https://apireference.aspose.cloud/slides/#/Fonts/SetEmbeddedFontFromRequest)|

### **Examples**
**cURL Example**

The code examples below show how to embed fonts in a presentation located in the storage.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fonts/embedded" \
-H "Authorization: Bearer [Access Token]" \
-F "file=@TestData/calibri.ttf" \ 
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Code: 200
Returns presentation fonts info.

```
{{< /tab >}}

{{< /tabs >}}


**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Stream fontFile = File.OpenRead("calibri.ttf");
FontsData response = api.SetEmbeddedFontFromRequest(fontFile, "MyPresentation.pptx", false);

Console.WriteLine("Font " + response.List[2].FontName + " has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

byte[] file = Files.readAllBytes(Paths.get("calibri.ttf"));
FontsData response = api.setEmbeddedFontFromRequest(file, "MyPresentation.pptx", false, null, null, null);

System.out.println("Font " + response.getList().get(2).getFontName() + " has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\FontsData;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$file = fopen("calibri.ttf", 'r');
$result = $api->setEmbeddedFontFromRequest($file, "MyPresentation.pptx", false);

print("Font " . $result->getList()[2]->getFontName() . " has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

source = File.binread("calibri.ttf")
response = api.set_embedded_font_from_request(source, "MyPresentation.pptx", false)
print "Font " + response.list[2].font_name + " has been embedded."      
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

with open("calibri.ttf", 'rb') as f:
    source = f.read()

response = api.set_embedded_font_from_request(source, "MyPresentation.pptx", False)

print("Font " + response.list[2].font_name + " has been embedded.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const stream = fs.createReadStream("calibri.ttf");
let result = await api.setEmbeddedFontFromRequest(stream, "MyPresentation.pptx", false);
console.log("Font " + result.body.list[2].fontName + " has been embedded.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

document, e := ioutil.ReadFile("calibri.ttf")
var onlyUsed bool = false
response, _, e := api.SlidesApi.SetEmbeddedFontFromRequest(document, "MyPresentation.pptx", &onlyUsed, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Font " + response.GetList()[2].GetFontName() + " has been embedded.")
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


## **SetEmbeddedFontFromRequestOnline**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/fonts/embedded|POST|Embeds font from request and returns presentation.|[SetEmbeddedFontFromRequestOnline](https://apireference.aspose.cloud/slides/#/Fonts/SetEmbeddedFontFromRequestOnline)|

### **Examples**
**cURL Example**

The code examples below show how to embed fonts in a presentation located in the request body.

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/fonts/embedded" \
-H "Authorization: Bearer [Access Token]" \
-F "file=@TestData/MyPresentation.pptx" \
-F "file=@TestData/calibri.ttf" \
-o "MyPresentation.pptx" \
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Document with embedded font.

```
{{< /tab >}}

{{< /tabs >}}


**SDK Examples**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Stream file = File.OpenRead("MyPresentation.pptx");
Stream fontFile = File.OpenRead("calibri.ttf");
Stream response = api.SetEmbeddedFontFromRequestOnline(file, fontFile, false);

Console.WriteLine("Font Calibri has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
byte[] fontFile = Files.readAllBytes(Paths.get("calibri.ttf"));
File response = api.setEmbeddedFontFromRequestOnline(file, fontFile, false, null);

System.out.println("Font Calibri has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\FontsData;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$file = fopen("MyPresentataion.pptx", 'r');
$fontFile = fopen("calibri.ttf", 'r');
$result = $api->setEmbeddedFontFromRequestOnline($file, $fontFile, false);

print("Font Calibri has been embedded.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

source = File.binread("MyPresentation.pptx")
fontSource = File.binread("calibri.ttf")
response = api.set_embedded_font_from_request_online(source, fontSource, false)
print "Font Calibri has been embedded."      
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

with open("MyPresentation.pptx", 'rb') as f:
    source = f.read()

with open("calibri.ttf", 'rb') as f:
    fontsource = f.read()

response = api.set_embedded_font_from_request_online(source, fontsource, False)

print("Font Calibri has been embedded.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const stream = fs.createReadStream("MyPresentation.pptx");
const fontStream = fs.createReadStream("calibri.ttf");
let reponse = await api.setEmbeddedFontFromRequestOnline(stream, fontStream, false);
console.log("Font Calibri has been embedded.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

document, e := ioutil.ReadFile("MyPresentation.pptx")
fontFile, e := ioutil.ReadFile("calibri.ttf")
var onlyUsed bool = false
_, _, e = api.SlidesApi.SetEmbeddedFontFromRequestOnline(document, fontFile, &onlyUsed, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Font Calibri has been embedded.")
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

## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
