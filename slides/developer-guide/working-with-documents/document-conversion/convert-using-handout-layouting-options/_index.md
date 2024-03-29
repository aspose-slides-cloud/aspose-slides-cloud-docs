---
title: "Convert Using Handout Layouting Options"
type: docs
url: /convert-using-handout-layouting-options/
weight: 70
---
## **Introduction**

You can convert presentations to some formats (**PDF**, **TIFF**, **HTML** and images) using print handout master. To do that, use a **HandoutLayoutingOptions** object for **SlidesLayoutOptions** property of export options.

The example below shows conversion to PDF using two-slide handout.

### **cURL Example**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Convert**

```sh
curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pdf" -d @"options.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]
```

**options.json file**

```javascript
{
    "format":"pdf",
    "slidesLayoutOptions": {
        "layoutType": "Handout",
        "handout": "Handouts2",
        "printSlideNumbers": true
    }
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
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

PdfExportOptions exportOptions = new PdfExportOptions
{
    SlidesLayoutOptions = new HandoutLayoutingOptions
    {
        Handout = HandoutLayoutingOptions.HandoutEnum.Handouts2,
        PrintSlideNumbers = true
    }
};

using Stream response = api.DownloadPresentation("MyPresentation.pptx", ExportFormat.Pdf, exportOptions);
using Stream outFile = File.Create("MyPresentation.pdf");
response.CopyTo(outFile);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

HandoutLayoutingOptions slidesLayoutOptions = new HandoutLayoutingOptions();
slidesLayoutOptions.setHandout(HandoutLayoutingOptions.HandoutEnum.HANDOUTS2);
slidesLayoutOptions.setPrintSlideNumbers(true);

PdfExportOptions exportOptions = new PdfExportOptions();
exportOptions.setSlidesLayoutOptions(slidesLayoutOptions);
File response = api.downloadPresentation(fileName, ExportFormat.PDF, exportOptions, password, folderName, null, null, null);
System.out.println("The converted file was saved to " + response.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;
use Aspose\Slides\Cloud\Sdk\Model\PdfExportOptions;
use Aspose\Slides\Cloud\Sdk\Model\HandoutLayoutingOptions;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slidesLayoutOptions = new HandoutLayoutingOptions();
$slidesLayoutOptions->setHandout("Handouts2");
$slidesLayoutOptions->setPrintSlideNumbers(true);

$exportOptions = new PdfExportOptions();
$exportOptions->setSlidesLayoutOptions($slidesLayoutOptions);

$result = $api->downloadPresentation(self::fileName, "pdf", $exportOptions, self::password, self::folderName);
print("The converted file was saved to " . $result->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

slides_layout_options = AsposeSlidesCloud::HandoutLayoutingOptions.new
slides_layout_options.handout = "Handouts2"
slides_layout_options.print_slide_numbers = True

export_options = AsposeSlidesCloud::PdfExportOptions.new
export_options.slides_layout_options = slides_layout_options

result = api.download_presentation("MyPresentation.pptx", AsposeSlidesCloud::ExportFormat::PDF, export_options)
File.binwrite("MyPresentation.pdf", result)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.export_format import ExportFormat
from asposeslidescloud.models.image_export_options import ImageExportOptions
from asposeslidescloud.models.font_fallback_rule import FontFallbackRule

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

slides_layout_options = HandoutLayoutingOptions()
slides_layout_options.handout = "Handouts2"
slides_layout_options.print_slide_numbers = True

export_options = PdfExportOptions()
export_options.slides_layout_options = slides_layout_options

result = api.download_presentation("MyPresentation.pptx", ExportFormat.PDF, export_options)
print('The converted file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const slidesLayoutOptions = new CloudSdk.HandoutLayoutingOptions();
slidesLayoutOptions.handout = CloudSdk.HandoutLayoutingOptions.HandoutEnum.Handouts2;
slidesLayoutOptions.printSlideNumbers = true;

const exportOptions = new CloudSdk.PdfExportOptions();
exportOptions.slidesLayoutOptions = slidesLayoutOptions;

api.downloadPresentation("MyPresentation.pptx", CloudSdk.ExportFormat.Pdf, exportOptions).then(response => {
    fs.writeFile("MyPresentation.pdf", response.body, (err) => {
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

slideLayoutOptions := slidescloud.NewHandoutLayoutingOptions()
slideLayoutOptions.SetHandout("Handouts2")
slideLayoutOptions.SetPrintSlideNumbers(true)

exportOptions := slidescloud.NewPdfExportOptions()
exportOptions.SetSlidesLayoutOptions(slideLayoutOptions)

result, _, e := api.SlidesApi.DownloadPresentation("MyPresentation.pptx", "pdf", exportOptions, "", "", "", "", nil)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The converted file was saved to  %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::FontFallbackRule;
use AsposeSlidesCloud::Object::ImageExportOptions;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $slides_layout_options = AsposeSlidesCloud::Object::HandoutLayoutingOptions->new();
$slides_layout_options->{handout} = "Handouts2";
$slides_layout_options->{print_slide_numbers} = 1;

my $export_options = AsposeSlidesCloud::Object::PdfExportOptions -> new();
$export_options->{slides_layout_options} = $slides_layout_options;

my %params = ('name' => "MyPresentation.pptx", 'format' => 'Pdf', 'options' => $export_options);
my $result = $api->download_presentation(%params);
my $zip = "MyPresentation.pdf";
open my $fh, '>', $zip;
binmode $fh;
print $fh $result;
close $fh;
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}