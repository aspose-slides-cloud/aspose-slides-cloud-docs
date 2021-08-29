---
title: "Convert PowerPoint Documents to other File Formats"
type: docs
url: /convert-powerpoint-documents-to-other-file-formats/
weight: 10
---

## **Convert**

## **Introduction**
You can convert presentations to different formats using Aspose.Slides Cloud API in your applications. You can convert files that are uploaded to Aspose Cloud Storage, or local files provided in request body. Likewise, you can either save the conversion result to Aspose Cloud Storage or download in response body. Thus, Slides Cloud API provides four conversion methods:
## **Using Storage**
### **API Information**

|**URL**|**HTTP Method**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/convert/{format}|POST|Convert the file in request body to the desired format and returns it|[Convert](https://apireference.aspose.cloud/slides/#/Document/Convert)|
|/slides/convert/{format}|PUT|Convert the file in request body to the desired format and saves the result to Cloud Storage|[ConvertAndSave](https://apireference.aspose.cloud/slides/#/Document/ConvertAndSave)|
|/slides/{name}/{format}|POST|Convert a file on Cloud Storage to the desired format and returns it|[DownloadPresentation](https://apireference.aspose.cloud/slides/#/Document/DownloadPresentation)|
|/slides/{name}/{format}|PUT|Convert a file on Cloud Storage to the desired format and saves the result to Cloud Storage|[SavePresentation](https://apireference.aspose.cloud/slides/#/Document/SavePresentation)|

PUT-methods require **outPath** query string parameter that specifies Storage path to save the output file.

You can optionally use **fontsFolder** parameter to use custom fonts with your files. **fontsFolder** should be a Storage folder that contains font files. You can create storage folders and upload files to it using Slides Cloud API.

You can [convert parts of presentations](/slides/convert-selected-document-slides/) using optional **slides** parameter.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```


**Create Fonts Folder**


```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/folder/customFonts" -d "" -H "Authorization: Bearer CwEsXL_ddljbOuknQ2d-grMMRhNcAUhsDDEbBfORflhLt7zZZEVDIC15mmk99AjMBlSywCpPiFcvPqJ0dc2SJBEhdGNcDBTQ1rbuy08Wa6LGvcASPRXXmj04WxgC4nkzuoJN4UTTECNruH1n85P3V1s2hwFXqCVWxcushRupPXr1L9bpALlG9uEQq9_1OAF_m_REnrTSF51YKKr1NJkzcL0YuZqPsu4ER4qu9Y132ipP4SruqjrHWnkbgQ0JcE81Zuw7hmCXjb8SJDi0xsfKWBfhQOPT-Ff9-OnrmMJ1m6KyaqLTpGmhgrSMVYf5KXbRNspaBdTgKMToKH-rUOukIdMWOjV7VF8L0libDd2YaMzleJdo6DVRLQN12oBZDYDXPL3QDkD3doi9aq848rNSw_Mj_3aHQ1xaGehBMPk7ea_WuKMf" --ssl-no-revoke

```

**Upload Font File**


```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/customFonts/custom.ttf" --data-binary @custom.ttf -H "Content-Type: application/octet-stream" -H "Authorization: Bearer CwEsXL_ddljbOuknQ2d-grMMRhNcAUhsDDEbBfORflhLt7zZZEVDIC15mmk99AjMBlSywCpPiFcvPqJ0dc2SJBEhdGNcDBTQ1rbuy08Wa6LGvcASPRXXmj04WxgC4nkzuoJN4UTTECNruH1n85P3V1s2hwFXqCVWxcushRupPXr1L9bpALlG9uEQq9_1OAF_m_REnrTSF51YKKr1NJkzcL0YuZqPsu4ER4qu9Y132ipP4SruqjrHWnkbgQ0JcE81Zuw7hmCXjb8SJDi0xsfKWBfhQOPT-Ff9-OnrmMJ1m6KyaqLTpGmhgrSMVYf5KXbRNspaBdTgKMToKH-rUOukIdMWOjV7VF8L0libDd2YaMzleJdo6DVRLQN12oBZDYDXPL3QDkD3doi9aq848rNSw_Mj_3aHQ1xaGehBMPk7ea_WuKMf" --ssl-no-revoke

```

**Convert the Presentation**


```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/convert/pdf?fontsFolder=customFonts" --data-binary @customfont.pptx -H "Content-Type: application/octet-stream" -H "Authorization: Bearer CwEsXL_ddljbOuknQ2d-grMMRhNcAUhsDDEbBfORflhLt7zZZEVDIC15mmk99AjMBlSywCpPiFcvPqJ0dc2SJBEhdGNcDBTQ1rbuy08Wa6LGvcASPRXXmj04WxgC4nkzuoJN4UTTECNruH1n85P3V1s2hwFXqCVWxcushRupPXr1L9bpALlG9uEQq9_1OAF_m_REnrTSF51YKKr1NJkzcL0YuZqPsu4ER4qu9Y132ipP4SruqjrHWnkbgQ0JcE81Zuw7hmCXjb8SJDi0xsfKWBfhQOPT-Ff9-OnrmMJ1m6KyaqLTpGmhgrSMVYf5KXbRNspaBdTgKMToKH-rUOukIdMWOjV7VF8L0libDd2YaMzleJdo6DVRLQN12oBZDYDXPL3QDkD3doi9aq848rNSw_Mj_3aHQ1xaGehBMPk7ea_WuKMf" --ssl-no-revoke -o customfont.pdf

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
const string fontsFolder = "customFonts";
api.CreateFolder(fontsFolder);
Stream font = File.OpenRead("custom.ttf");
api.UploadFile(font, $"{fontsFolder}/custom.ttf");
Stream file = File.OpenRead("customfont.pptx");
Stream response = api.Convert(file, ExportFormat.Pdf, fontsFolder: fontsFolder);
response.CopyTo(File.Create("customfont.pdf"));
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
String fontsFolder = "customFonts";
api.createFolder(fontsFolder);
byte[] font = Files.readAllBytes(Paths.get("custom.ttf"));
api.uploadFile(font, $"{fontsFolder}/custom.ttf");
byte[] file = Files.readAllBytes(Paths.get("customfont.pptx"));
File response = api.convert(file, ExportFormat.PDF, null, null, fontsFolder);
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

$fontsFolder = "customFonts";
$api->CreateFolder($fontsFolder);

$font = fopen("custom.ttf", 'r');
$api->UploadFile($font, $fontsFolder . "/custom.ttf");

$file = fopen("customfont.pptx", 'r');
$result = $api->Convert($file, ExportFormat::PDF, null, null, $fontsFolder);
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

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

fonts_folder = "customFonts"
api.create_folder(fonts_folder)

with open("custom.ttf", 'rb') as ff:
    font_file = ff.read()
api.upload_file(font_file, fonts_folder + "/custom.ttf")

with open("customfont.pptx", 'rb') as f:
    input_file = f.read()
result = api.convert(input_file, ExportFormat.PDF, None, None, fonts_folder)
print('The converted file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fontsFolder = "customFonts";
api.createFolder(fontsFolder).then(() => {
    const font = fs.createReadStream("custom.ttf");
    api.uploadFile(font, fontsFolder + "/custom.ttf").then(() => {
        const file = fs.createReadStream("customfont.pptx");
        api.convert(file, "pdf", null, null, fontsFolder).then(() => {
            fs.writeFile("customfont.pdf", response.body, (err) => {
                if (err) throw err;
            });
        });
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}


## **Conversion Formats**
The Aspose.Slides Cloud API supports the following format conversions

|**File Type**|**Extension**|
| :- | :- |
|PowerPoint Presentation|pptx|
|PowerPoint Presentation|ppt|
|Microsoft PowerPoint Open XML Macro-Enabled Presentation File|pptm|
|Microsoft PowerPoint Open XML Slide Show File|ppsx|
|Microsoft PowerPoint Show File|pps|
|Microsoft PowerPoint Open XML Macro-enabled Slide Show File |ppsm|
|Microsoft PowerPoint Open XML Template File |potx|
|Microsoft PowerPoint Macro-Enabled Template|potm|
|OpenDocument Presentation file|odp|
|Open Office / Star Office Presentation|otp|
|Portable Document Format|pdf|
|HTML File|html|
|Open XML Paper Specification|xps|
|Shockwave Flash File|swf|
|Scalable Vector Graphics File|svg|
|Tiff Image|tiff|
|JPEG Image|jpeg|
|PNG File|png|
|GIF Image|gif|
|Bitmap File|bmp|
