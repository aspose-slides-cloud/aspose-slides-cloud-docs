---
title: "Update a VBA Module"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- VBA
- macros
- module
- VBA module
- update a module
- edit a module
- change a module
type: docs
url: /update-a-vba-module/
weight: 40
---
## **Introduction**
Aspose.Slides.Cloud API allows to update VBA modules and add global references if needed. The module name can't be updated.
## **UpdateVbaModule**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/vbaProject/modules/{moduleIndex}|PUT|Returns VBA module info|[UpdateVbaModule](#)
### **Examples**
**cURL Example**

The code example below shows how to update VBA module with index 1 and add two global references.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptm/vbaProject/modules/1" -H "Authorization: Bearer [Access Token]" -H "Content-Type: text/json" -F @"vbaModule.json"
```

vbaModule.json
```json
{
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
Returns VBA module info.

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

VbaModule response = api.UpdateVbaModule("MyPresentation.pptm", 1, dto);

Console.WriteLine($"\"{response.Name} has been updated \n{response.SelfUri.Href}");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

VbaModule dto = new VbaModule();
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
VbaModule response = api.updateVbaModule("MyPresentation.pptm", 1, dto, null, null, null);
String s = String.format("\"%s\" has been updated \n%s", response.getName(), response.getSelfUri().getHref());
System.out.println(s);
```
{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\VbaModule;
use Aspose\Slides\Cloud\Sdk\Model\VbaReference;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$vbaModule = new VbaModule();
$vbaModule->setSourceCode("Sub Test() MsgBox \"Test\" End Sub");

$reference1 = new VbaReference();
$reference1->setName("stdole");
$reference1->setLibId("*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation");
$reference2 = new VbaReference();
$reference2->setName("Office");
$reference2->setLibId("*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library");
$vbaModule->setReferences([$reference1, $reference2]);

$result = $api->updateVbaModule("MyPresentation.pptm", 1, $vbaModule);
echo "\"" . $result->getName() . "\" has been updated\n" . $result->getSelfUri()->getHref();
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

dto = AsposeSlidesCloud::VbaModule.new
dto.source_code = "Sub Test() MsgBox ""Test"" End Sub"
        
reference1 = AsposeSlidesCloud::VbaReference.new
reference1.name = "stdole"
reference1.lib_id = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation"
reference2 = AsposeSlidesCloud::VbaReference.new
reference2.name = "Office"
reference2.lib_id = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library"
dto.references = [reference1, reference2]

response = api.update_vba_module("MyPresentation.pptm", 1, dto)
puts "'#{response.name}' has been updated \n #{response.self_uri.href}"
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.vba_module import VbaModule
from asposeslidescloud.models.vba_reference import VbaReference

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = VbaModule()
dto.source_code = "Sub Test() MsgBox ""Test"" End Sub"
reference1 = VbaReference()
reference1.name = "stdole"
reference1.lib_id = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation"
reference2 = VbaReference()
reference2.name = "Office"
reference2.lib_id = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library"
dto.references = [reference1, reference2]
response = api.update_vba_module("MyPresentation.pptm", 1, dto)
print("\"" + response.name + "\" has been updated\n" + response.self_uri.href)
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new CloudSdk.VbaModule();
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
const response = await api.updateVbaModule("MyPresentation.pptm", 1, dto).then(response => {
const vbaModule = response.body;
console.log("\"" + vbaModule.name + "\" has been updated\n" + vbaModule.selfUri.href);
});
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptm"
dto := asposeslidescloud.NewVbaModule()
dto.SourceCode = "Sub Test() MsgBox \"Test\" End Sub"
reference1 := asposeslidescloud.NewVbaReference()
reference1.Name = "stdole"
reference1.LibId = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation"
reference2 := asposeslidescloud.NewVbaReference()
reference2.Name = "Office"
reference2.LibId = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library"
dto.References = []asposeslidescloud.IVbaReference{reference1, reference2}

response, _, e := api.SlidesApi.UpdateVbaModule(fileName, 1, dto,"", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("\"%v\", has been updated \n%v", response.GetName(), response.GetSelfUri().GetHref())
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::VbaModule;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $dto = AsposeSlidesCloud::Object::VbaModule->new();
$dto->{source_code} = "Sub Test() MsgBox \"Test\" End Sub";
my $reference_1 = AsposeSlidesCloud::Object::VbaReference->new();
$reference_1->{name} = "stdole";
$reference_1->{lib_id} = "*\\G{00020430-0000-0000-C000-000000000046}#2.0#0#C:\\Windows\\system32\\stdole2.tlb#OLE Automation";
my $reference_2 = AsposeSlidesCloud::Object::VbaReference->new();
$reference_2->{name} = "Office";
$reference_2->{lib_id} = "*\\G{2DF8D04C-5BFA-101B-BDE5-00AA0044DE52}#2.0#0#C:\\Program Files\\Common Files\\Microsoft Shared\\OFFICE14\\MSO.DLL#Microsoft Office 14.0 Object Library";
my @references = ($reference_1, $reference_2);
$dto->{references} = \@references;

my %params = ('name' => 'MyPresentation.pptm', 'module_dto' => $dto, "module_index" => 1);
my $response = $api->update_vba_module(%params);

print "'".$response->{name}."' has been updated\n".$response->{self_uri}->{href};
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
