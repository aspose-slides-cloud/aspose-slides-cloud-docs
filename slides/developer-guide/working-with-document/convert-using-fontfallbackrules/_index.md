---
title: "Convert Using FontFallbackRules"
type: docs
url: /convert-using-fontfallbackrules/
weight: 50
---
## **Introduction**
Aspose.Slides Cloud allows specifying the rules to apply a fallback font. **FontFallbackRule** represents an association between the specified Unicode range, used for searching missed glyphs, and a list of fonts that may contain proper glyphs. The order of fonts in the list reflects priority.
### **API Information**
FontFallbackRule is a part of ExportOptions and can be applied in any feature that assumed conversion.  For example:
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/{format}|POST|Save a presentation to a specified format|[DownloadPresentation](https://apireference.aspose.cloud/slides/#/Document/DownloadPresentation)|
/slides/{name}/{format}|PUT|Save presentation to a specified format|[SavePresentation](https://apireference.aspose.cloud/slides/#/Document/SavePresentation)|
/slides/convert/format|POST|Convert presentation from request content to format specified|[Convert](https://apireference.aspose.cloud/slides/#/Document/Convert)|
/slides/convert/format|PUT|Convert presentation from request content to format specified|[ConvertAndSave](https://apireference.aspose.cloud/slides/#/Document/ConvertAndSave)|
/slides/{name}/split|POST|Splitting presentations|[Split](https://apireference.aspose.cloud/slides/#/Document/Split)
/sldies/split/{format}|POST|Splitting presentations from request|[SplitOnline](https://apireference.aspose.cloud/slides/#/Document/SplitOnline)|
/sldies/split/{format}|PUT|Splitting presentations from request|[SplitAndSaveOnline](https://apireference.aspose.cloud/slides/#/Document/SplitAndSaveOnline)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```sh

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/png" -d @"options.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```

options.json file:
```javascript
{
    "format":"image",
    "FontFallbackRules":[
        {"RangeStartIndex": 0x0B80,
        "RangeEndIndex": 0x0BFF,
        FallbackFontList: ["Arial"]}
    ]
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
List<FontFallbackRule> fontRules = new List<FontFallbackRule>();
fontRules.Add(new FontFallbackRule()
{
    RangeStartIndex = c_startUnicodeIndex,
    RangeEndIndex = c_endUnicodeIndex,
    FallbackFontList = new List<string>() { "Vijaya" }
});

fontRules.Add(new FontFallbackRule()
{
    RangeStartIndex = c_startUnicodeIndex,
    RangeEndIndex = c_endUnicodeIndex,
    FallbackFontList = new List<string>() { "Segoe UI Emoji, Segoe UI Symbol", "Arial" }
});

ImageExportOptions exportOptions = new ImageExportOptions()
{
    FontFallbackRules = fontRules
};
            
using Stream response = api.DownloadPresentation("MyPresentation.pptx", ExportFormat.Png, exportOptions);
using Stream outFile = File.Create("MyPresentation.zip");
response.CopyTo(outFile);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
List<FontFallbackRule> fontRules = new ArrayList<FontFallbackRule>();

FontFallbackRule rule1 = new FontFallbackRule();
rule1.setRangeStartIndex(0x42B);
rule1.setRangeEndIndex(0x42B);
List<String> fonts1 = new ArrayList<string>();
fonts1.add("Vijaya");
rule1.setFallbackFontList(fonts1);
fontRules.add(rule1);

FontFallbackRule rule2 = new FontFallbackRule();
rule2.setRangeStartIndex(0x42E);
rule2.setRangeEndIndex(0x42E);
List<String> fonts2 = new ArrayList<string>();
fonts2.add("Segoe UI Emoji");
fonts2.add("Segoe UI Symbol");
fonts2.add("Arial");
rule2.setFallbackFontList(fonts2);
fontRules.add(rule2);

ImageExportOptions exportOptions = new ImageExportOptions();
exportOptions.setFontFallbackRules(fontRules);
            
File response = api.DownloadPresentation("MyPresentation.pptx", ExportFormat.Png, exportOptions, null, null, null, null);
System.out.println("The converted file was saved to " + response.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;
use Aspose\Slides\Cloud\Sdk\Model\ImageExportOptions;
use Aspose\Slides\Cloud\Sdk\Model\FontFallbackRule;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$rule1 = new FontFallbackRule();
$rule1->setRangeStartIndex($startUnicodeIndex);
$rule1->setRangeEndIndex($endUnicodeIndex);
$fonts1 = [ "Vijaya" ];
$rule1->setFallbackFontList($fonts1);

$rule2 = new FontFallbackRule();
$rule2->setRangeStartIndex($startUnicodeIndex);
$rule2->setRangeEndIndex($endUnicodeIndex);
$fonts2 = [ "Segoe UI Emoji", "Segoe UI Symbol", "Arial" ];
$rule2->setFallbackFontList($fonts2);

$fontRules = [ $rule1, $rule2 ];
$exportOptions = new ImageExportOptions();
$exportOptions->setFontFallbackRules($fontRules);
            
$result = $api->DownloadPresentation("MyPresentation.pptx", ExportFormat::PDF, $exportOptions);
print("The converted file was saved to " . $result->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

rule1 = AsposeSlidesCloud::FontFallbackRule.new
rule1.range_start_index = start_unicode_index
rule1.range_end_index = end_unicode_index
rule1.fallback_font_list = ["Vijaya"]

rule2 = AsposeSlidesCloud::FontFallbackRule.new
rule2.range_start_index = start_unicode_index
rule2.range_end_index = end_unicode_index
rule2.fallback_font_list = ["Segoe UI Emoji", "Segoe UI Symbol", "Arial"]

export_options = AsposeSlidesCloud::ImageExportOptions.new
export_options.font_fallback_rules([rule1, rule2])

result = api.download_presentation("MyPresentation.pptx", AsposeSlidesCloud::ExportFormat::PNG, export_options)
File.binwrite("MyPresentation.zip", result)
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

rule1 = FontFallbackRule()
rule1.range_start_index = start_unicode_index
rule1.range_end_index = end_unicode_index
rule1.fallback_font_list = ["Vijaya"]

rule2 = FontFallbackRule()
rule2.range_start_index = start_unicode_index
rule2.range_end_index = end_unicode_index
rule2.fallback_font_list = ["Segoe UI Emoji", "Segoe UI Symbol", "Arial"]

export_options = ImageExportOptions()
export_options.font_fallback_rules([rule1, rule2])

result = api.download_presentation("MyPresentation.pptx", ExportFormat.PNG, export_options)
print('The converted file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const rule1 = new CloudSdk.FontFallbackRule();
rule1.rangeStartIndex = c_startUnicodeIndex;
rule1.rangeEndIndex = c_endUnicodeIndex;
rule1.fallbackFontList = [ "Vijaya" ];

const rule2 = new CloudSdk.FontFallbackRule();
rule2.rangeStartIndex = c_startUnicodeIndex;
rule2.rangeEndIndex = c_endUnicodeIndex;
rule2.fallbackFontList = [ "Segoe UI Emoji, Segoe UI Symbol", "Arial" ];

const exportOptions = new CloudSdk.ImageExportOptions();
exportOptions.fontFallbackRules = [ rule1, rule2 ];
api.downloadPresentation("MyPresentation.pptx", "png", exportOptions).then(() => {
    fs.writeFile("MyPresentation.zip", response.body, (err) => {
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

rule1 := NewFontFallbackRule()
rule1.RangeStartIndex = c_startUnicodeIndex
rule1.RangeEndIndex = c_endUnicodeIndex
fonts1 := []string> { "Vijaya" }
rule1.FallbackFontList = fonts1

rule2 := NewFontFallbackRule()
rule2.RangeStartIndex = c_startUnicodeIndex
rule2.RangeEndIndex = c_endUnicodeIndex
fonts2 := []string> { "Segoe UI Emoji", "Segoe UI Symbol", "Arial" }
rule2.FallbackFontList = fonts2

fontRules := []FontFallbackRule { rule1, rule2 }

exportOptions := NewImageExportOptions()
exportOptions.FontFallbackRules = fontRules

result, _, e := c.SlidesApi.DownloadPresentation("MyPresentation.pptx", "png", exportOptions, null, null, null, null)
if e != nil {
    fmt.Printf("Error: %v.", e)
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
use AsposeSlidesCloud::Object::ExportOptions;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $rule1 = AsposeSlidesCloud::Object::FontFallbackRule->new();
$rule1->{range_start_index} = $c_startUnicodeIndex;
$rule1->{range_end_index} = $c_endUnicodeIndex;
my @fonts1 = ( "Vijaya" );
$rule1->{fallback_font_list} = \@fonts1;

my $rule2 = AsposeSlidesCloud::Object::FontFallbackRule->new();
$rule2->{range_start_index} = $c_startUnicodeIndex;
$rule2->{range_end_index} = $c_endUnicodeIndex;
my @fonts2 = ( "Segoe UI Emoji", "Segoe UI Symbol", "Arial" );
$rule2->{fallback_font_list} = \@fonts2;

my $exportOptions = AsposeSlidesCloud::Object::ImageExportOptions->new();
my @fontRules := ( $rule1, $rule2 );
$exportOptions->{font_fallback_rules} = \@fontRules;

my %params = ('name' => 'MyPresentation.pptx', 'format' => 'png', 'options' => $exportoptions);
my $result = $api->download_presentation(%params);
my $zip = "MyPresentation.zip";
open my $fh, '>>', $zip;
binmode $fh;
print $fh $result;
close $fh;
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}