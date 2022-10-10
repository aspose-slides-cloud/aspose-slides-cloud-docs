---
title: "Deleting Embedded Font"
type: docs
url: /deleting-embedded-font/
weight: 50
---
## **Introduction**
Aspose.Slides Cloud API allows deleting an embedded font from the presentation. The feature can be applied to presentations located in the storage or presentations uploaded in the request body.
## **DeleteEmbeddedFont**

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/fonts/embedded/{fontName}|DELETE| Removes specified embedded font and returns presentation fonts info.|[DeleteEmbeddedFont]()
## **Examples**
**cURL Example**

The code examples below show how to delete an embedded font from a presentation in the storage.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fonts/embedded/arial" -H "Authorization: Bearer [Access Token]"
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

FontsData response = api.DeleteEmbeddedFont("MyPresentation.pptx", "Arial");

Console.WriteLine("Arial has been removed from the embedded fonts.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

FontsData response = api.deleteEmbeddedFont("MyPresentation.pptx", "Arial", null, null, null);

System.out.println("Arial has been removed from the embedded fonts.");
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

$result = $api->deleteEmbeddedFont("MyPresentation.pptx", "Arial");

print("Arial has been removed from the embedded fonts.");
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

response = api.delete_embedded_font("MyPresentation.pptx", "Arial")

print("Arial has been removed from the embedded fonts.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let result = await api.deleteEmbeddedFont("MyPresentation.pptx", "Arial");
            
console.log("Arial has been removed from the embedded fonts.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
fontName := "Arial"
_, _, e = api.DeleteEmbeddedFont(fileName, fontName, "", "", "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

fmt.Printf("Arial has been removed from the embedded fonts.")
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

**Request**

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Stream file = File.OpenRead("MyPresentation.pptx");
api.DeleteEmbeddedFontOnline(file, "Arial");

Console.WriteLine("Arial has been removed from the embedded fonts.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
api.deleteEmbeddedFontOnline(file, "Arial", null);

System.out.println("Arial has been removed from the embedded fonts.");
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
$api->deleteEmbeddedFontOnline($file, "Arial");

print("Arial has been removed from the embedded fonts.");
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

api.delete_embedded_font_online(source, "Arial")

print("Arial has been removed from the embedded fonts.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const stream = fs.createReadStream("MyPresentation.pptx");
let result = await api.deleteEmbeddedFontOnline(stream, "Arial");
            
console.log("Arial has been removed from the embedded fonts.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

document, e := ioutil.ReadFile("MyPresentation.pptx")
fontName := "Arial"
_, _, e = api.DeleteEmbeddedFontOnline(document, fontName, "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

fmt.Printf("Arial has been removed from the embedded fonts.")
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


## **DeleteEmbeddedFontOnline**

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/fonts/embedded/{fontName}/delete|POST|Removes specified embedded font and returns presentation.|[DeleteEmbeddedFontOnline]()|

### **Examples**
**cURL Example**

The code examples below show how to delete an embedded font from a presentation in request body.

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/fonts/embedded/Arial/delete" \
-H "Authorization: Bearer [Access Token]" \
-F "file=@TestData/MyPresentation.pptx"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Document without specified embedded font.

```
{{< /tab >}}

{{< /tabs >}}


**SDK Examples**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Stream file = File.OpenRead("MyPresentation.pptx");
api.DeleteEmbeddedFontOnline(file, "Arial");

Console.WriteLine("Arial has been removed from the embedded fonts.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
api.deleteEmbeddedFontOnline(file, "Arial", null);

System.out.println("Arial has been removed from the embedded fonts.");
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
$api->deleteEmbeddedFontOnline($file, "Arial");

print("Arial has been removed from the embedded fonts.");
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

api.delete_embedded_font_online(source, "Arial")

print("Arial has been removed from the embedded fonts.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const stream = fs.createReadStream("MyPresentation.pptx");
let result = await api.deleteEmbeddedFontOnline(stream, "Arial");
            
console.log("Arial has been removed from the embedded fonts.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

document, e := ioutil.ReadFile("MyPresentation.pptx")
fontName := "Arial"
_, _, e = api.DeleteEmbeddedFontOnline(document, fontName, "")
if e != nil {
	t.Errorf("Error: %v.", e)
	return
}

fmt.Printf("Arial has been removed from the embedded fonts.")
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