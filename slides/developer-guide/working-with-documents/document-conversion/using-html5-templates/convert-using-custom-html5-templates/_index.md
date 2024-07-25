---
title: "Convert Using Custom HTML5 Templates"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- convert a presentation
- export a presentation
type: docs
url: /convert-using-custom-html5-templates/
weight: 10
---
## **Introduction**

Presentations are converted to HTML5 using html (Razor) templates. You can upload and use your own templates to override default conversion layout and/or styles.

To use custom templates, you need to,

1. Create a storage folder.
1. Upload your custom HTML5 templates to that folder.
1. Call one of the [conversion](/slides/convert-presentations/) methods and specify the storage folder as **TemplatesPath** option value.

Only the last step is repeated for every conversion. The rest are done once; when you have uploaded your templates, you use them as long as you need. You have to upload them again only when your templates are modified and need to be refreshed.

You need not have the whole set of templates in your templates folder. E.g. if you wish to render picture frames in a customized way, and leave all the rest as they are, you only need to provide your custom *pictureFrame.html* file. The application will use default files for all the other templates.

Instead of creating the template(s) from scratch, you can get the default template set by using [GetHtml5Templates](/slides/get-default-html5-templates/) method, and then modify the template files you need.

The example below shows conversion to HTML5 using custom PictureFrame template.

## **cURL Example**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Token**

```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Create Templates Folder**

```sh
curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/folder/Html5Templates" -d "" -H "Authorization: Bearer [Access Token]
```

**Upload Template**

```sh
curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/Html5Templates/pictureFrame.html" -F "file=@pictureFrame.html" -H "Authorization: Bearer [Access Token]
```

**Convert**

```sh
curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pdf" -d @"options.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]
```

**options.json file**

```json
{
    "templatesPath": "Html5Templates",
    "animateTransitions": true
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns the document.

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="8" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
string templatesPath = "Html5Templates";
string templateFileName = "pictureFrame.html";

SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

api.CreateFolder(templatesPath);

Stream template = File.OpenRead(templateFileName);
api.UploadFile(templatesPath + "/" + templateFileName, template);

Html5ExportOptions exportOptions = new Html5ExportOptions
{
    TemplatesPath = templatesPath,
    AnimateTransitions = true
};

Stream presentation = File.OpenRead("MyPresentation.pptx");
Stream response = api.Convert(presentation, ExportFormat.Html5, options: exportOptions);
using Stream outFile = File.Create("MyPresentation.zip");
response.CopyTo(outFile);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String templatesPath = "Html5Templates";
String templateFileName = "pictureFrame.html";

SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

api.createFolder(templatesPath, null);

byte[] template = Files.readAllBytes(templateFileName);
api.uploadFile(templatesPath + "/" + templateFileName, template, null);

Html5ExportOptions exportOptions = new Html5ExportOptions();
exportOptions.setTemplatesPath(templatesPath);
exportOptions.setAnimateTransitions(true);

byte[] file = Files.readAllBytes("MyPresentation.pptx");
File response = api.convert(fileName, ExportFormat.HTML5, null, null, null, null, exportOptions);
System.out.println("The converted file was saved to " + response.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;
use Aspose\Slides\Cloud\Sdk\Model\Html5ExportOptions;

$templatesPath = "Html5Templates";
$templateFileName = "pictureFrame.html";

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$api->createFolder($templatesPath);

$api->uploadFile($templatesPath."/".$templateFileName, fopen($templateFileName, 'r'));

$exportOptions = new Html5ExportOptions();
$exportOptions->setTemplatesPath(templatesPath);
$exportOptions->setAnimateTransitions(true);

$response = $api->convert(fopen("MyPresentation.pptx", 'r'), "html5", null, null, null, null, exportOptions);
print("The converted file was saved to " . $result->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
templates_path = "Html5Templates"
template_file_name = "pictureFrame.html"

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

api.create_folder(templates_path)

api.upload_file(templates_path + "/" + template_file_name, File.binread(template_file_name))

export_options = AsposeSlidesCloud::Html5ExportOptions.new
export_options.templates_path = templates_path
export_options.animate_transitions = true

result = api.convert(File.binread("MyPresentation.pptx"), AsposeSlidesCloud::ExportFormat::HTML5, nil, nil, nil, nil, export_options)
File.binwrite("MyPresentation.zip", result)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.export_format import ExportFormat
from asposeslidescloud.models.html5_export_options import Html5ExportOptions

templates_path = "Html5Templates"
template_file_name = "pictureFrame.html"

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

api.create_folder(templates_path)

with open(template_file_name, 'rb') as f:
    template = f.read()
api.upload_file(templates_path + "/" + template_file_name, template)

export_options = Html5ExportOptions()
export_options.templates_path = templates_path
export_options.animate_transitions = true

with open("MyPresentation.pptx", 'rb') as f:
    presentation = f.read()
result = api.convert(presentation, ExportFormat.HTML5, None, None, None, None, export_options)
print('The converted file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
String templatesPath = "Html5Templates";
String templateFileName = "pictureFrame.html";

const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

api.createFolder(templatesPath);

api.uploadFile(templatesPath + "/" + templateFileName, fs.createReadStream(templateFileName));

const exportOptions = new Html5ExportOptions();
exportOptions.templatesPath = templatesPath;
exportOptions.animateTransitions = true;

api.convert(fs.createReadStream("MyPresentation.pptx"), CloudSdk.ExportFormat.Html5, null, null, null, null, exportOptions).then(response => {
    fs.writeFile("MyPresentation.zip", response.body, (err) => {
        if (err) throw err;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
templatesPath := "Html5Templates"
templateFileName := "pictureFrame.html"

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

_, e := api.SlidesApi.CreateFolder(templatesPath, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

template, e := ioutil.ReadFile(templateFileName)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
_, e = api.SlidesApi.UploadFile(templatesPath+"/"+templateFileName, template, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

exportOptions := slidescloud.NewHtml5ExportOptions()
exportOptions.SetTemplatesPath(templatesPath)
animateTransitions := true
exportOptions.SetAnimateTransitions(&animateTransitions)

presentation, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
result, _, e := api.SlidesApi.DownloadPresentation("MyPresentation.pptx", "html5", "", "", "", nil, exportOptions)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The converted file was saved to %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Html5ExportOptions;

my $templatesPath = "Html5Templates";
my $templateFileName = "pictureFrame.html";

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %create_params = ('path' => $templatesPath);
$api->create_folder(%create_params);

my $template = read_file($templateFileName, { binmode => ':raw' });
my %upload_template_params = ('path' => $templatesPath."/".$templateFileName, 'file' => $template);
$api->upload_file(%upload_template_params);

my $export_options = AsposeSlidesCloud::Object::Html5ExportOptions -> new();
$export_options->{templates_path} = $templatesPath;
$export_options->{animate_transitions} = 1;

my $presentation = "MyPresentation.pptx";
my %params = ('name' => $presentation, 'format' => 'Html5', 'options' => $export_options);
my $result = $api->convert(%params);
my $zip = "MyPresentation.zip";
open my $fh, '>', $zip;
binmode $fh;
print $fh $result;
close $fh;
```

{{< /tab >}}

{{< /tabs >}}
