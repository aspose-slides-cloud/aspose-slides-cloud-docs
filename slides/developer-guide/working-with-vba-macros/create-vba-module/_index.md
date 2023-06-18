---
title: "Create VBA Module"
type: docs
url: /create-vba-module/
weight: 10
---
## **Introduction**
Aspose.Slides.Cloud API allows to create VBA modules and add global references if needed. 
## **CreateVbaModule**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/vbaProject|POST|Returns VBA project info|[CreateVbaModule](#)
### **Examples**
**cURL Example**

The code example below shows how to create VBA module and add two global references.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/vbaProject" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json" -F @"vbaModule.json"
```

vbaModule.json
```json
{
    "name": "Module1",
    "sourceCode": "Sub Test() MsgBox \"Test\" End Sub",
    "references": [
        {
            "name": "stdole",
            "libId": "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation"
        },
        {
            "name": "Office",
            "libId": "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library"
        }
    ]
}
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

VbaModule dto = new VbaModule()
{
    Name = c_moduleName,
    SourceCode = @"Sub Test() MsgBox ""Test"" End Sub",
    References = new List<VbaReference>()
    {
        new VbaReference()
        {
            Name = "stdole",
            LibId = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation"
        },
        new VbaReference()
        {
            Name = "Office",
            LibId = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library"
        }    
    }
};

VbaProject response = api.CreateVbaModule("MyPresentation.pptx", dto);

Console.WriteLine($"VBA project contains: {response.Modules.Count} module(s), and {response.References.Count} references");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

VbaModule dto = new VbaModule();
dto.setName("Module1");
dto.setSourceCode("Sub Test() MsgBox \"Test\" End Sub");
VbaReference reference0 = new VbaReference();
reference0.setName("stdole");
reference0.setLibId("*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation");
VbaReference reference1 = new VbaReference();
reference1.setName("Office");
reference1.setLibId("*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library");
List<VbaReference> references = new ArrayList<VbaReference>();
references.add(reference0);
references.add(reference1);
dto.setReferences(references);
VbaProject response = (VbaProject)api.createVbaModule("MyPresentation.pptx", dto, null, null, null);
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

$vbaModule = new VbaModule();
$vbaModule->setName("Module1");
$vbaModule->setSourceCode("Sub Test() MsgBox \"Test\" End Sub");

$reference0 = new VbaReference();
$reference0->setName("stdole");
$reference0->setLibId("*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation");
$reference1 = new VbaReference();
$reference1->setName("Office");
$reference1->setLibId("*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library");
$vbaModule->setReferences([$reference0, $reference1]);

$result = $api->createVbaModule("MyPresentation.pptx", $vbaModule);
echo "VBA project contains: " . count($result->getModules()) . " module(s), and " . count($result->getReferences()) . " references";
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

dto = AsposeSlidesCloud::VbaModule.new
dto.name = "Module1"
dto.source_code = "Sub Test() MsgBox ""Test"" End Sub"
        
reference0 = AsposeSlidesCloud::VbaReference.new
reference0.name = "stdole"
reference0.lib_id = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation"
reference1 = AsposeSlidesCloud::VbaReference.new
reference1.name = "Office"
reference1.lib_id = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library"
dto.references = [reference0, reference1]

response = api.create_vba_module("MyPresentation.pptx", dto)
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

dto = VbaModule()
dto.name = "Module1"
dto.source_code = "Sub Test() MsgBox ""Test"" End Sub"
reference0 = VbaReference()
reference0.name = "stdole"
reference0.lib_id = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation"
reference1 = VbaReference()
reference1.name = "Office"
reference1.lib_id = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library"
dto.references = [reference0, reference1]
response = api.create_vba_module("MyPresentation.pptx", dto)
print("VBA project contains: " + str(len(response.modules)) + " module(s), and " + str(len(response.references)) + " references")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new model.VbaModule();
dto.name = "Module1";
dto.sourceCode = "Sub Test() MsgBox \"Test\" End Sub";
dto.references = [
    {
        name: "stdole",
        libId: "*\\\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\\\Windows\\\\system32\\\\stdole2.tlb#OLE Automation"
    },
    {
        name: "Office",
        libId: "*\\\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\\\Program Files\\\\Common Files\\\\Microsoft Shared\\\\OFFICE14\\\\MSO.DLL#Microsoft Office 14.0 Object Library"
    }
];
const response = await api.createVbaModule("MyPresentation.pptx", dto).then((response) => {
const vbaProject = (response.body as model.VbaProject);
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

fileName := "MyPresentation.pptx"
dto := slidescloud.NewVbaModule()
dto.Name = "Module1"
dto.SourceCode = "Sub Test() MsgBox \"Test\" End Sub"
reference0 := slidescloud.NewVbaReference()
reference0.Name = "stdole"
reference0.LibId = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation"
reference1 := slidescloud.NewVbaReference()
reference1.Name = "Office"
reference1.LibId = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library"
dto.References = []slidescloud.IVbaReference{reference0, reference1}

response, _, e := api.CreateVbaModule(fileName, dto, "", "", "")
if e != nil {
    t.Errorf("Error: %v.", e)
    return
}
result := fmt.Sprintf("VBA project contains: %v module(s), and %v references", len(response.GetModules()), len(response.GetReferences()))
fmt.Println(result)
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

my $dto = AsposeSlidesCloud::Object::VbaModule->new();
$dto->{name} = "Module1";
$dto->{source_code} = "Sub Test() MsgBox \"Test\" End Sub";
my $reference_0 = AsposeSlidesCloud::Object::VbaReference->new();
$reference_0->{name} = "stdole";
$reference_0->{lib_id} = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation";
my $reference_1 = AsposeSlidesCloud::Object::VbaReference->new();
$reference_1->{name} = "Office";
$reference_1->{lib_id} = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library";
my @references = ($reference_0, $reference_1);
$dto->{references} = \@references;

my %params = ('name' => 'MyPresentation.pptx', 'dto' => $dto);
my $response = $api->create_vba_module(%params);
my $modules_count = scalar @{$response->{modules}};
my $references_count = scalar @{$response->{references}};
print STDERR "VBA project contains: ".$modules_count." module(s), and ".$references_count." references";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
