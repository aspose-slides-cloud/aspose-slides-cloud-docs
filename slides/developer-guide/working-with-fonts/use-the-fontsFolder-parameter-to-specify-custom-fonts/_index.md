---
title: "Use the fontsFolder Parameter to Specify Custom Fonts"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- font
- presentation fonts
type: docs
url: /use-the-fontsFolder-parameter-to-specify-custom-fonts/
weight: 10
---

## **Introduction**
Aspose.Slides for Cloud allows you to optionally specify fontsFolder Parameter for methods that convert presentations or their parts to other formats. The fontsFolder parameter allows you to specify the location at Aspose Cloud Storage where custom font files are uploaded.
## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Convert](https://apireference.aspose.cloud/slides/#/Document/Convert).
## **Examples**
**cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d84119"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl -v "http://api.aspose.cloud/v3.0/slides/convert?format=pdf&fontsFolder=fonts" --data-binary @sample.pptx

-X PUT -H "Accept:application/json"  -H "Authorization: Bearer -Ou_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw_c8cAuk3qoag3g7bghMHw_pe_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR_hOD8Doqk5SBi_j-efODJK_PmGUxj0onOrUUx8Tj_GuUKrG6DcBnpl84_UykdOP87IeHnT2_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS_q3lthTDRMg2LuZ6s0r9MKlwVJ_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{response-data}

```

{{< /tab >}}

{{< /tabs >}}

**SDK Examples**
{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName9="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream file = File.OpenRead("sample.pptx");
Stream response = api.Convert(file, ExportFormat.Pdf, fontsFolder: "fonts");
response.CopyTo(File.Create("myPresentation.pdf"));
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
byte[] file = Files.readAllBytes(Paths.get("customfont.pptx"));
File response = api.convert(file, ExportFormat.PDF, null, null, "customFonts", null, null);
System.out.println("The converted file was saved to " + response.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$file = fopen("customfont.pptx", 'r');
$result = $api->Convert($file, ExportFormat::PDF, null, null, "customFonts");
print("The converted file was saved to " . $result->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.export_format import ExportFormat

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

with open("customfont.pptx", 'rb') as f:
    input_file = f.read()
result = api.convert(input_file, ExportFormat.PDF, None, None, "customFonts")
print('The converted file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const file = fs.createReadStream("customfont.pptx");
api.convert(file, "pdf", null, null, "customFonts").then(response => {
    fs.writeFile("customfont.pdf", response.body, (err) => {
        if (err) throw err;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

source, e := ioutil.ReadFile("customfont.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

result, _, e := api.SlidesApi.Convert(source, "pdf", "", "", "customFonts", nil, nil)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The converted file was saved to  %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
