---
title: "Get a VBA Project"
type: docs
url: /get-a-vba-project/
weight: 40
---
## **Introduction**
Aspose.Slides.Cloud API allows to retrieve VBA project data. 
## **GetVbaProject**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/vbaProject|GET|Returns VBA project info|[GetVbaProject](#)
### **Examples**
**cURL Example**

The code example below shows how to retrieve VBA project data.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptm/vbaProject" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json"
```

{{< /tab >}}

{{< tab tabNum="2" >}}
```sh

Code: 200
Returns VBA project info.

```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
VbaProject response = api.GetVbaProject("MyPresentation.pptm");
Console.WriteLine($"VBA project contains: {response.Modules.Count} module(s), and {response.References.Count} references");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
VbaProject response = (VbaProject)api.getVbaProject("MyPresentation.pptm", null, null, null);
System.out.println("VBA project contains: " + response.getModules().size() + " module(s), and " + response.getReferences().size() + " references");
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

$result = $api->getVbaProject("MyPresentation.pptm");
echo "VBA project contains: " . count($result->getModules()) . " module(s), and " . count($result->getReferences()) . " references";
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

response = api.get_vba_project("MyPresentation.pptm")
puts "VBA project contains: #{response.modules.length} module(s), and #{response.references.length} references"
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

response = api.get_vba_project("MyPresentation.pptm")
print("VBA project contains: " + str(len(response.modules)) + " module(s), and " + str(len(response.references)) + " references")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const response = await api.getVbaProject("MyPresentation.pptm").then((response) => {
const vbaProject = response.body;
console.log("VBA project contains: " + vbaProject.modules.length + " module(s), and " + vbaProject.references.length + " references");
});
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

response, _, e := api.SlidesApi.GetVbaProject("MyPresentation.pptm", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("VBA project contains: %v module(s), and %v references", len(response.GetModules()), len(response.GetReferences()))
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

my %params = ('name' => 'MyPresentation.pptm');
my $response = $api->get_vba_project(%params);
my $modules_count = scalar @{$response->{modules}};
my $references_count = scalar @{$response->{references}};
print "VBA project contains: ".$modules_count." module(s), and ".$references_count." references";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
