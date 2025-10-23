---
title: "Set Embedded Fonts"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- font
- embedded fonts
- presentation fonts
type: docs
url: /set-embedded-fonts/
weight: 50
---
## **Introduction**
Aspose.Slides Cloud API allows embedding multiple fonts in one request. You can specify font names in the query string, or (and) provide the font files in the request body. The second option is good for custom fonts that are not available on the server. The feature can be applied to presentations located in the storage or presentations uploaded in the request body along with the font file(s).

## **SetEmbeddedFonts**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/fonts/embedded|POST|Embeds fonts and returns presentation fonts info.|[SetEmbeddedFonts](https://apireference.aspose.cloud/slides/#/Fonts/SetEmbeddedFonts)|

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
-F "file1=@TestData/calibri.ttf" \ 
-F "file2=@TestData/arial.ttf" \ 
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

Stream fontFile1 = File.OpenRead("calibri.ttf");
Stream fontFile2 = File.OpenRead("arial.ttf");
List<FileInfo> fontFiles = new List<FileInfo>
{
    new FileInfo { Name = "calibri.ttf", Content = fontFile1 },
    new FileInfo { Name = "arial.ttf", Content = fontFile2 }
};
FontsData response = api.SetEmbeddedFonts("MyPresentation.pptx", fontFiles, null, false);

Console.WriteLine("Number of used fonts: " + response.List.Count);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

FileInfo file1 = new FileInfo();
file1.setName("calibri.ttf");
file1.setData(Files.readAllBytes(Paths.get("calibri.ttf")));

FileInfo file2 = new FileInfo();
file2.setName("arial.ttf");
file2.setData(Files.readAllBytes(Paths.get("arial.ttf")));
List<FileInfo> fontFiles = new ArrayList<FileInfo>();
fontFiles.add(file1);
fontFiles.add(file2);
FontsData response = api.setEmbeddedFonts("MyPresentation.pptx", fontfiles, null, false, null, null, null);

System.out.println("Number of used fonts: " + response.getList().size());
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

$file1 = fopen("calibri.ttf", 'r');
$file2 = fopen("arial.ttf", 'r');
$files = [ $file1, $file2 ];
$result = $api->setEmbeddedFonts("MyPresentation.pptx", $files, null, false);

print("Number of used fonts: " . count($result->getList()));
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

source1 = File.binread("calibri.ttf")
source2 = File.binread("arial.ttf")
response = api.set_embedded_fonts("MyPresentation.pptx", [ source1, source2 ], nil, false)
print "Number of used fonts: " + response.list.length
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
    source1 = f.read()
with open("arial.ttf", 'rb') as f:
    source2 = f.read()

response = api.set_embedded_fonts("MyPresentation.pptx", [ source1, source2 ], None, False)

print("Number of used fonts: " + len(response.list) + " has been embedded.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const file1 = fs.createReadStream("calibri.ttf");
const file2 = fs.createReadStream("arial.ttf");
let result = await api.setEmbeddedFonts("MyPresentation.pptx", [ file1, file2 ], null, false);
console.log("Number of used fonts: " + result.body.list.length);
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

font1, e := ioutil.ReadFile("calibri.ttf")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

font2, e := ioutil.ReadFile("arial.ttf")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

var onlyUsed bool = false
response, _, e := api.SlidesApi.SetEmbeddedFonts("MyPresentation.pptx", [][]byte{ font1, font2 }, nil, &onlyUsed, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Number of used fonts: " + len(response.GetList()))
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

## **SetEmbeddedFontsOnline**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/fonts/embedded|POST|Embeds fonts and returns presentation.|[SetEmbeddedFontsOnline](https://apireference.aspose.cloud/slides/#/Fonts/SetEmbeddedFontsOnline)|

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
curl -X POST "https://api.aspose.cloud/v3.0/slides/fonts/embedded&fontNames=Calibri,Arial" \
-H "Authorization: Bearer [Access Token]" \
-F "file=@TestData/MyPresentation.pptx" \
-o "MyPresentation.pptx" \
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Document with embedded fonts.

```
{{< /tab >}}

{{< /tabs >}}


**SDK Examples**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Stream file = File.OpenRead("MyPresentation.pptx");
List<string> fontsToEmbed = new List<string> { "Calibri", "Arial" };
Stream response = api.SetEmbeddedFontsOnline(file, null, fontsToEmbed, false);

Console.WriteLine("Fonts have been embedded.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
ArrayList fonts = new ArrayList(Arrays.asList("Calibri", "Arial"));
File response = api.setEmbeddedFontsOnline(file, null, fonts, false, null);

System.out.println("Fonts have been embedded.");
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

$file = fopen("MyPresentataion.pptx", 'r');
$result = $api->setEmbeddedFontsOnline($file, null, [ "Calibri", "Arial" ], false);

print("Fonts have been embedded.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

source = File.binread("MyPresentation.pptx")
response = api.set_embedded_fonts_online(source, nil, [ "Calibri", "Arial" ], false)
print "Fonts have been embedded."
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

response = api.set_embedded_fonts_online(source, None, [ "Calibri", "Arial" ], False)

print("Fonts have been embedded.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const stream = fs.createReadStream("MyPresentation.pptx");
let reponse = await api.setEmbeddedFontsOnline(stream, null, [ "Calibri", "Arial" ], false);
console.log("Fonts have been embedded.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

document, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

var onlyUsed bool = false
_, _, e = api.SlidesApi.SetEmbeddedFontsOnline(document, nil, []string{ "Calibri", "Arial" }, &onlyUsed, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Fonts have been embedded.")
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
