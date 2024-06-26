---
title: "Get Presentation Fonts"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- font
- presentation fonts
type: docs
url: /get-presentation-fonts/
weight: 20
---
## **Introduction**
Aspose.Slides Cloud API allows getting list of fonts used in the presentation. The list can be obtained from the presentation located in the storage or the presentation uploaded in the request body.

## **GetFonts**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/fonts|Get|Returns presentation fonts info.|[GetFonts](https://apireference.aspose.cloud/slides/#/Fonts/GetFonts)|

### **Examples**

**cURL Example**

The code examples below show how to obtain fonts information from presentations in the storage.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fonts" -H "Authorization: Bearer [Access Token]"
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

FontsData response = api.GetFonts("MyPresentation.pptx");

Console.WriteLine("Count of fonts used in the presentation: " + response.List.Count);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

FontsData response = api.getFonts("MyPresentation.pptx", null, null, null);

System.out.println("Count of fonts used in the presentation: " + response.getList().size());
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

$result = $api->getFonts("MyPresentation.pptx");

print("Count of fonts used in the presentation: " . count($result->getList()));
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

response = api.get_fonts("MyPresentation.pptx")

print(f"Count of fonts used in the presentation: { len(response.list) }")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let response = await api.getFonts("MyPresentation.pptx");
            
console.log("Count of fonts used in the presentation: " +  response.body.list.length);
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"

response, _, e := api.SlidesApi.GetFonts(fileName, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Count of fonts used in the presentation: %v", len(response.GetList()))
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

## **GetFontsOnline**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/fonts|Get|Returns presentation fonts info.|[GetFontsOnline](https://apireference.aspose.cloud/slides/#/Fonts/GetFontsOnline)|

## **Examples**
**cURL Example**

The code examples below show how to obtain fonts information from presentations in request body.

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/fonts" \
-H "Authorization: Bearer [Access Token]" \
-F "file=@TestData/MyPresentation.pptx"
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

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Stream file = File.OpenRead("MyPresentation.pptx");
FontsData response = api.GetFontsOnline(file);

Console.WriteLine("Count of fonts used in the presentation: " + response.List.Count);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
FontsData response = api.getFontsOnline(file, null);

System.out.println("Count of fonts used in the presentation: " + response.getList().size());
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
$result = $api->getFontsOnline($file);

print("Count of fonts used in the presentation: " . count($result->getList()));
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

with open("MyPresentation.pptx", 'rb') as f:
    source = f.read()

response = api.get_fonts_online(source)

print(f"Count of fonts used in the presentation: { len(response.list) }")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const stream = fs.createReadStream("MyPresentation.pptx");
let response = await api.getFontsOnline(stream);
            
console.log("Count of fonts used in the presentation: " +  response.body.list.length);
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

document, e := ioutil.ReadFile("MyPresentation.pptx")

response, _, e := api.SlidesApi.GetFontsOnline(document, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Count of fonts used in the presentation: %v", len(response.GetList()))
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
