---
title: "Compress Embedded Fonts"
type: docs
url: /compress-embedded-fonts/
weight: 60
---
## **Introduction**

Aspose.Slides Cloud API allows compressing embedded fonts by removing unused characters. The feature can be applied to presentations located in the storage or presentations uploaded in the request body.

## **CompressEmbeddedFonts**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/fonts/embedded/compress|POST| Compresses embedded fonts in a presentation.|[CompressEmbeddedFonts](https://apireference.aspose.cloud/slides/#/Fonts/CompressEmbeddedFonts)|

### **Examples**

**cURL Example**

The code examples below show how to compress embedded fonts for a presentation in the storage.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Compress embedded fonts**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fonts/embedded/compress" -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Code: 200

```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.CompressEmbeddedFonts("MyPresentation.pptx");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.compressEmbeddedFonts("MyPresentation.pptx", null, null, null);
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

$api->compressEmbeddedFonts("MyPresentation.pptx");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

api.compress_embedded_fonts('MyPresentation.pptx')
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

api.compress_embedded_fonts("MyPresentation.pptx")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

await api.compressEmbeddedFonts("MyPresentation.pptx");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
_, e := api.SlidesApi.CompressEmbeddedFonts(fileName, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
```

{{< /tab >}}
{{< tab tabNum="8" >}}

```cpp
std::shared_ptr<ApiConfiguration> configuration = std::make_shared<ApiConfiguration>();
configuration->setAppSid(L"MyClientId");
configuration->setAppKey(L"MyClientSecret");
std::shared_ptr<SlidesApi> api = std::make_shared<SlidesApi>(configuration);

api->compressEmbeddedFonts("MyPresentation.pptx").get();
```

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

my %params = (name => "MyPresentation.pptx");
$api->compress_embedded_fonts(%params);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift
AsposeSlidesCloudAPI.appSid = "MyClientId"
AsposeSlidesCloudAPI.appKey = "MyClientSecret"
SlidesAPI.deleteUnusedMasterSlides("MyPresentation.pptx") { (error) -> Void in
    if error != nil {
        print("Error: \(error!)")
    }
}
```

{{< /tab >}}

{{< /tabs >}}

## **CompressEmbeddedFontsOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/fonts/embedded/compress|POST| Compresses embedded fonts in a presentation.|[CompressEmbeddedFontsOnline](https://apireference.aspose.cloud/slides/#/Fonts/CompressEmbeddedFontsOnline)|

### **Examples**

**cURL Example**

The code examples below show how to compress embedded fonts for a presentation in request body.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Compress embedded fonts**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fonts/embedded/compress" -H "Authorization: Bearer [Access Token]" -F "file=@MyData/MyPresentation.pptx"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Code: 200
Returns the updated presentation.

```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

using Stream input = File.OpenRead("MyPresentation.pptx");
using Stream output = api.CompressEmbeddedFontsOnline(input);
using Stream outputFile = File.Create("output.pptx");
output.CopyTo(outputFile);
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
File response = api.compressEmbeddedFontsOnline(file, null);
System.out.println("The compressed file has been saved to " + response.getPath());
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
$response = $api->compressEmbeddedFontsOnline($file);
print("The compressed file has been saved to " . $response->getPathname());
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

input_data = File.binread("MyPresentation.pptx")
output_data = api.compress_embedded_fonts_online(input_data)
File.binwrite("output.pptx", output_data)
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

output_path = api.compress_embedded_fonts_online(source)
print("The output file has been saved to " + output_path)
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const input = fs.createReadStream("MyPresentation.pptx");
let response = await api.compressEmbeddedFontsOnline(input);
fs.writeFile("output.pptx", response.body, (error) => {
    if (error) throw error;
});
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
response, _, e := api.SlidesApi.CompressEmbeddedFontsOnline(document, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The output file was saved to  %v.", response.Name())
```

{{< /tab >}}
{{< tab tabNum="8" >}}

```cpp
std::shared_ptr<ApiConfiguration> configuration = std::make_shared<ApiConfiguration>();
configuration->setAppSid(L"MyClientId");
configuration->setAppKey(L"MyClientSecret");
std::shared_ptr<SlidesApi> api = std::make_shared<SlidesApi>(configuration);

std::make_shared<std::ifstream> file = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
std::ofstream fs("output.pptx", std::ios::binary);
api->compressEmbeddedFontsOnline(file, format).get().writeTo(fs);
```

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

my $input_file = read_file("MyPresentation.pptx", { binmode => ':raw' });
my %params = ('document' => $input_file);
my $result = $api->compress_embedded_fonts_online(%params);
my $output_name = "output.pptx";
open my $fh, '>', $output_name;
binmode $fh;
print $fh $result;
close $fh;
```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift
import Foundation
import AsposeSlidesCloud

let dispatchGroup = DispatchGroup()

AsposeSlidesCloudAPI.appSid = "MyClientId"
AsposeSlidesCloudAPI.appKey = "MyClientSecret"

dispatchGroup.enter()
let input = FileManager.default.contents(atPath: "MyPresentation.pptx")!
SlidesAPI.compressEmbeddedFontsOnline(input) { (response, e) -> Void in
    do {
        let url = URL(fileURLWithPath: "output.pptx")
        try (response as! Data).write(to: url)
    } catch {
        print("Error saving file: \(error).")
    }
    if (e != nil) {
        print("An error occured: \(e).")
    }
    dispatchGroup.leave()
}
dispatchGroup.notify(queue: DispatchQueue.main) {
    exit(EXIT_SUCCESS)
}
dispatchMain()
```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)