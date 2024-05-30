---
title: "Get a VBA Module"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- VBA
- macros
- module
- VBA module
- get a module
type: docs
url: /get-a-vba-module/
weight: 30
---
## **Introduction**
Aspose.Slides.Cloud API allows to retrieve VBA module info. 
## **GetVbaModule**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/vbaProject/modules/{moduleIndex}|GET|Returns VBA module info|[GetVbaModule](#)
### **Examples**
**cURL Example**

The code example below shows how to retrieve VBA module with index 1.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptm/vbaProject/modules/1" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json"
```

{{< /tab >}}

{{< tab tabNum="2" >}}
```sh

Code: 200
Returns VBA module info.

```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
VbaModule response = api.GetVbaModule("MyPresentation.pptm", 1);
Console.WriteLine($"Module: {response.Name}\n{response.SourceCode}");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
VbaModule response = (VbaModule)api.getVbaModule("MyPresentation.pptm", 1, null, null, null);
String s = String.format("Module: \"%s\"\n%s", response.getName(), response.getSourceCode());
System.out.println(s);
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

$result = $api->getVbaModule("MyPresentation.pptm", 1);
echo "Module: " . $result->getName() . "\n" . $result->getSourceCode();
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

response = api.get_vba_module("MyPresentation.pptm", 1)
puts "#{response.name} \n#{response.source_code}"
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

response = api.get_vba_module("MyPresentation.pptm", 1)
print("Module: " + response.name + "\n" + response.source_code)
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const response = await api.getVbaModule("MyPresentation.pptm", 1).then(response => {
const vbaModule = response.body;
console.log("Module: " + vbaModule.name + "\n" + vbaModule.sourceCode);
});
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

response, _, e := api.SlidesApi.GetVbaModule("MyPresentation.pptm", 1, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Module: %v \n %v", response.GetName(), response.GetSourceCode())
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

my %params = ('name' => 'MyPresentation.pptm', 'module_index' => 1);
my $response = $api->get_vba_module(%params);
print "Module: ".$response->{name}."\n".$response->{source_code};
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
