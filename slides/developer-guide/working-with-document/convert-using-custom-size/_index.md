---
title: "Convert Using Custom Size"
type: docs
url: /convert-using-custom-size/
weight: 40
---

## **Convert Documents Using Custom Size**

## **Introduction**
You can use **ExportOptions** to specify custom size for [conversion](/slides/convert-powerpoint-documents-to-other-file-formats/) of presentations.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Convert the Presentation**

```java
curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/convert/png" -F "file=@MyPresentation.pptx" -F "data=@options.json;filename=" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer CwEsXL_ddljbOuknQ2d-grMMRhNcAUhsDDEbBfORflhLt7zZZEVDIC15mmk99AjMBlSywCpPiFcvPqJ0dc2SJBEhdGNcDBTQ1rbuy08Wa6LGvcASPRXXmj04WxgC4nkzuoJN4UTTECNruH1n85P3V1s2hwFXqCVWxcushRupPXr1L9bpALlG9uEQq9_1OAF_m_REnrTSF51YKKr1NJkzcL0YuZqPsu4ER4qu9Y132ipP4SruqjrHWnkbgQ0JcE81Zuw7hmCXjb8SJDi0xsfKWBfhQOPT-Ff9-OnrmMJ1m6KyaqLTpGmhgrSMVYf5KXbRNspaBdTgKMToKH-rUOukIdMWOjV7VF8L0libDd2YaMzleJdo6DVRLQN12oBZDYDXPL3QDkD3doi9aq848rNSw_Mj_3aHQ1xaGehBMPk7ea_WuKMf" -o MyPresentation.zip
```

```javascript
{
    "width": 480,
    "height": 360
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{response-data}

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream file = File.OpenRead("MyPresentation.pptx");
ExportOptions options = new ImageExportOptions { Width = 480, Height = 360 };
Stream response = api.Convert(file, ExportFormat.Png, null, null, null, null, options);
response.CopyTo(File.Create("MyPresentation.zip"));
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
ExportOptions options = new ImageExportOptions();
options.setWidth(480);
options.setHeight(360);
File response = api.convert(file, ExportFormat.PNG, null, null, null, null, options);
System.out.println("The converted file was saved to " + response.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;
use Aspose\Slides\Cloud\Sdk\Model\ImageExportOptions;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$file = fopen("MyPresentation.pptx", 'r');
$options = new ImageExportOptions();
$options->setWidth(480);
$options->setHeight(360);
$result = $api->Convert($file, ExportFormat::PNG, null, null, null, null, $options);
print("The converted file was saved to " . $result->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "ConvertToOtherFormat.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.export_format import ExportFormat
from asposeslidescloud.models.image_export_options import ImageExportOptions

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

with open("MyPresentation.pptx", 'rb') as f:
    input_file = f.read()
options = ImageExportOptions()
options.width = 480
options.height = 360
result = api.convert(input_file, ExportFormat.PNG, None, None, None, None, options)
print('The converted file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const file = fs.createReadStream("MyPresentation.pptx");
    const options = new CloudSdk.ImageExportOptions();
    options.width = 480;
    options.height = 360;
    api.convert(file, "png", null, null, null, options).then(() => {
        fs.writeFile("MyPresentation.zip", response.body, (err) => {
            if (err) throw err;
        });
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

source, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

options := NewImageExportOptions()
options.Width = 480
options.Height = 360
result, _, e := c.SlidesApi.Convert(source, "png", "", "", "", nil, options)
if e != nil {
    fmt.Printf("Error: %v.", e)
}
fmt.Printf("The converted file was saved to  %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
