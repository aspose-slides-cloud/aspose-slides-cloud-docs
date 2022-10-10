---
title: "Replace Font"
type: docs
url: /replace-font/
weight: 60
---
## **Introduction**
Aspose.Slides Cloud API allows replacing a font used in a presentation. The feature can be applied to presentations located in the storage or presentations uploaded in the request body. Optionaly the new font can be embedded.

## **ReplaceFont**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/fonts/{sourceFont}/replace/{targetFont}|POST|Replaces specified font and returns presentation fonts info.|[ReplaceFont]()|

### **Examples**
**cURL Example**

The code examples below show how to replace a font in the presentation in the storage.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fonts/Calibri/replace/Times%20New%20Roman?embed=true" -H "Authorization: Bearer [Access Token]"
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

FontsData response = api.ReplaceFont("MyPresentation.pptx", "Calibri", "Times New Roman",  true);

Console.WriteLine("Font Calibri has been replaced with Times New Roman.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

FontsData response = api.replaceFont("MyPresentation.pptx", "Calibri", "Times New Roman", true, null, null, null);

System.out.println("Font Calibri has been replaced with Times New Roman.");
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

$result = $api->replaceFont("MyPresentation.pptx", "Calibri", "Times New Roman", true);

print("Font Calibri has been replaced with Times New Roman.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)
response = api.replace_font("MyPresentation.pptx", "Calibri", "Times%20New%20Roman", true)
print "Font Calibri has been replaced with Times New Roman."
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

response = api.replace_font("MyPresentation.pptx", "Calibri", "Times New Roman", true)

print("Font Calibri has been replaced with Times New Roman.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let result = await api.replaceFont("MyPresentation.pptx", "Calibri", "Times New Roman", true);
            
console.log("Font Calibri has been replaced with Times New Roman.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
fontName := "Calibri"
targetFontName := "Times New Roman"
var embed bool = true
response, _, e := api.ReplaceFont(fileName, fontName, targetFontName, &embed, "", "", "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

fmt.Printf("Font Calibri has been replaced with Times New Roman.")
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


## **ReplaceFontOnline**

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/fonts/fonts/{sourceFont}/replace/{targetFont}|POST|Replaces specified font and returns presentation.|[ReplaceFontOnline]()|

### **Examples**
**cURL Example**

The code examples below show how to replace a font in the presentation in the request body.

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/fonts/Calibri/replace/Times%20New%20Roman?embed=true" \
-H "Authorization: Bearer [Access Token]" \
-F "file=@MyPresentation.pptx"
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
Stream response = api.ReplaceFontOnline(file, "Calibri", "Times New Roman",  true);

Console.WriteLine("Font Calibri has been replaced with Times New Roman.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
File response = api.replaceFontOnline(file, "Calibri", "Times New Roman", true, null);

System.out.println("Font Calibri has been replaced with Times New Roman.");
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
$file = fopen("MyPresentation.pptx", 'r');
$result = $api->replaceFontOnline($file, "Calibri", "Times New Roman", true);

print("Font Calibri has been replaced with Times New Roman.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)
source = File.binread("MyPresentation.pptx") 
response = api.replace_font_onlne(source, "Calibri", "Times%20New%20Roman", true)
print "Font Calibri has been replaced with Times New Roman."
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
response = api.replace_font_online(source, "Calibri", "Times New Roman", true)

print("Font Calibri has been replaced with Times New Roman.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const stream = fs.createReadStream("MyPresentation.pptx");
let result = await api.replaceFontOnline(stream, "Calibri", "Times New Roman", true);
            
console.log("Font Calibri has been replaced with Times New Roman.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
fontName := "Calibri"
targetFontName := "Times New Roman"
var embed bool = true

document, e := ioutil.ReadFile("MyPresentation.pptx")
response, _, e := api.ReplaceFont(document, fontName, targetFontName, &embed, "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

fmt.Printf("Font Calibri has been replaced with Times New Roman.")
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