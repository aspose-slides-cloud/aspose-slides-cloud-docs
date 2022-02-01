---
title: "Conversion Options"
type: docs
url: /conversion-options/
weight: 30
---

## **Conversion Options**

## **Introduction**
You can use options with [convert](/slides/convert-powerpoint-documents-to-other-file-formats/) feature. Options are provided as request body JSON.
You can use options with all conversion methods - for presentations, slides or shapes. The options are format-specific, so check the table below to see what options are appropriate for your conversion format.

|**Option**|**Type**|**Description**|**Output Format**|
| :- | :- | :- | :- |
|DefaultRegularFont|string|Default regular font for rendering the presentation.|all|
|Width|double|Output document width.|all|
|Height|double|Output document height.|all|
|NotesPosition|None / BottomFull / BottomTruncated|The position of the notes on the page.|PDF, SWF, TIFF, HTML, PNG, JPG, GIF, BMP|
|CommentsPosition|None / Bottom / Right|The position of the comments on the page.|PDF, SWF, TIFF, HTML, PNG, JPG, GIF, BMP|
|CommentsAreaWidth|integer|The width of the comment output area in pixels (Applies only if comments are displayed on the right).|PDF, SWF, TIFF, HTML, PNG, JPG, GIF, BMP|
|CommentsAreaColor|integer|The color of comments area (Applies only if comments are displayed on the right).|PDF, SWF, TIFF, HTML, PNG, JPG, GIF, BMP|
|ShowCommentsByNoAuthor|boolean|True if comments that have no author are displayed.|PDF, SWF, TIFF, HTML|
|ShowHiddenSlides|boolean|Specifies whether the generated document should include hidden slides or not.|PDF, SWF, TIFF, HTML, XPS|
|DrawSlidesFrame|boolean|True to draw black frame around each slide.|PDF, XPS|
|SaveMetafilesAsPng|boolean|True to convert all metafiles used in a presentation to the PNG images.|PDF, XPS|
|JpegQuality|integer|The quality of the JPEG images. Default is 95.|PDF, SWF, HTML, SVG|
|TextCompression|None / Flate|Compression type to be used for all textual content in the document.|PDF|
|Compliance|Pdf15 / PdfA1b / PdfA1a / PdfUa|Desired conformance level for generated PDF document.|PDF|
|AccessPermissions|None / PrintDocument / ModifyContent / CopyTextAndGraphics / AddOrModifyFields / FillExistingFields / ExtractTextAndGraphics / AssembleDocument / HighQualityPrint|Access permissions that should be granted when the document is opened with user access.|PDF|
|EmbedFullFonts|boolean|Determines whether all characters of font should be embedded or only used subset.|PDF|
|SufficientResolution|double|The resolution of images inside PDF document. Affects file size, export time and image quality. The default value is 96.|PDF|
|Password|string|User password to protect the PDF document.|PDF|
|EmbedTrueTypeFontsForASCII|boolean|Determines whether Aspose.Slides will embed common fonts for ASCII (33..127 code range) text. Fonts for character codes greater than 127 are always embedded. Common fonts list includes PDF's base 14 fonts and additional user specified fonts.|PDF|
|AdditionalCommonFontFamilies|List<string>|An array of user-defined names of font families which Aspose.Slides should consider common.|PDF|
|ImageTransparentColor|string|Image transparent color.|PDF|
|ApplyImageTransparent|boolean|True to apply specified ImageTransparentColor to an image.|PDF|
|Compressed|boolean|Specifies whether the generated SWF document should be compressed or not. Default is true.|SWF|
|ViewerIncluded|boolean|Specifies whether the generated SWF document should include the integrated document viewer or not. Default is true.|SWF|
|ShowPageBorder|boolean|Specifies whether border around pages should be shown. Default is true.|SWF|
|ShowFullScreen|boolean|Show/hide fullscreen button. Can be overridden in flashvars. Default is true.|SWF|
|ShowPageStepper|boolean|Show/hide page stepper. Can be overridden in flashvars. Default is true.|SWF|
|ShowSearch|boolean|Show/hide search section. Can be overridden in flashvars. Default is true.|SWF|
|ShowTopPane|boolean|Show/hide whole top pane. Can be overridden in flashvars. Default is true.|SWF|
|ShowBottomPane|boolean|Show/hide bottom pane. Can be overridden in flashvars. Default is true.|SWF|
|ShowLeftPane|boolean|Show/hide left pane. Can be overridden in flashvars. Default is true.|SWF|
|StartOpenLeftPane|boolean|Start with opened left pane. Can be overridden in flashvars.|SWF|
|EnableContextMenu|boolean|Enable/disable context menu. Default is true.|SWF|
|LogoImage|string|Image that will be displayed as logo in the top right corner of the viewer. The image data is a base 64 string. Image should be 32x64 pixels PNG image, otherwise logo can be displayed improperly.|SWF|
|LogoLink|string|The full hyperlink address for a logo. Has an effect only if a LogoImage is specified.|SWF|
|Compression|Default / None / CCITT3 / CCITT4 / LZW / RLE|Compression type.|TIFF|
|PixelFormat|Format1bppIndexed / Format4bppIndexed / Format8bppIndexed / Format24bppRgb / Format32bppArgb|The pixel format for the generated images.|TIFF|
|Width|integer|Width.|TIFF|
|Height|integer|Height.|TIFF|
|DpiX|integer|Horizontal resolution, in dots per inch.|TIFF|
|DpiY|integer|Vertical resolution, in dots per inch.|TIFF|
|PicturesCompression|Dpi330 / Dpi220 / Dpi150 / Dpi96 / Dpi72 / DocumentResolution|The pictures compression level|HTML, SVG|
|DeletePicturesCroppedAreas|boolean|Indicates whether the cropped parts remain as part of the document. If true the cropped  parts will removed, if false they will be serialized in the document (which can possible lead to a larger file).|HTML, SVG|
|SaveAsZip|boolean|True to save presentation as zip file.|HTML|
|SubDirectoryName|string|The name of subdirectory in zip-file for store external files.|HTML|
|SvgResponsiveLayout|boolean|True to make layout responsive by excluding width and height attributes from svg container.|HTML|
|AnimateTransitions|boolean|True to animate transitions.|HTML5|
|AnimateShapes|boolean|True to animate shapes.|HTML5|
|ExternalFontsHandling|AddLinksToFontFiles/Embed/Vectorize|Determines a way of handling externally loaded fonts.|SVG|
|VectorizeText|boolean|Determines whether the text on a slide will be saved as graphics.|SVG|
|MetafileRasterizationDpi|integer|The lower resolution limit for metafile rasterization.|SVG|
|Disable3DText|boolean|Determines whether the 3D text is disabled in SVG.|SVG|
|DisableGradientSplit|boolean|Disables splitting FromCornerX and FromCenter gradients.|SVG|
|DisableLineEndCropping|boolean|SVG 1.1 lacks ability to define insets for markers. Aspose.Slides SVG writing engine has workaround for that problem: it crops end of line with arrow, so, line doesn't overlap markers. This option switches off such behavior.|SVG|
|Conformance|Ecma3762006 / Iso295002008Transitional / Iso295002008Strict|The conformance class to which the PresentationML document conforms.|PPTX|

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

**Convert the Presentation**


```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/convert/pdf?slides=2,4" -F "file=@MyPresentation.pptx" -F "data=@options.json;filename=" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer CwEsXL_ddljbOuknQ2d-grMMRhNcAUhsDDEbBfORflhLt7zZZEVDIC15mmk99AjMBlSywCpPiFcvPqJ0dc2SJBEhdGNcDBTQ1rbuy08Wa6LGvcASPRXXmj04WxgC4nkzuoJN4UTTECNruH1n85P3V1s2hwFXqCVWxcushRupPXr1L9bpALlG9uEQq9_1OAF_m_REnrTSF51YKKr1NJkzcL0YuZqPsu4ER4qu9Y132ipP4SruqjrHWnkbgQ0JcE81Zuw7hmCXjb8SJDi0xsfKWBfhQOPT-Ff9-OnrmMJ1m6KyaqLTpGmhgrSMVYf5KXbRNspaBdTgKMToKH-rUOukIdMWOjV7VF8L0libDd2YaMzleJdo6DVRLQN12oBZDYDXPL3QDkD3doi9aq848rNSw_Mj_3aHQ1xaGehBMPk7ea_WuKMf" --ssl-no-revoke -o MyPresentation.pdf
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
using Stream file = File.OpenRead("MyPresentation.pptx");
PdfExportOptions options = new PdfExportOptions { DrawSlidesFrame = true };
using Stream response = api.Convert(file, ExportFormat.Pdf, slides: new List<int> { 2, 4 }, options: options);
using Stream outFile = File.Create("MyPresentation.pdf");
response.CopyTo(outFile);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
PdfExportOptions options = new PdfExportOptions();
options.setDrawSlidesFrame(true);
File response = api.convert(file, ExportFormat.PDF, null, null, null, Arrays.asList(2, 4), options);
System.out.println("The converted file was saved to " + response.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;
use Aspose\Slides\Cloud\Sdk\Model\PdfExportOptions;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$file = fopen("MyPresentation.pptx", 'r');
$options = new PdfExportOptions();
$options->setDrawSlidesFrame(true);
$result = $api->Convert($file, ExportFormat::PDF, null, null, null, [ 2, 4 ], $options);
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
from asposeslidescloud.models.pdf_export_options import PdfExportOptions

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

with open("MyPresentation.pptx", 'rb') as f:
    input_file = f.read()
options = PdfExportOptions()
options.draw_slides_frame = True
result = api.convert(input_file, ExportFormat.PDF, None, None, None, [ 2, 4 ], options)
print('The converted file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const file = fs.createReadStream("MyPresentation.pptx");
const options = new CloudSdk.PdfExportOptions();
options.drawSlidesFrame = true;
api.convert(file, "pdf", null, null, null, [ 2, 4 ], options).then(() => {
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

source, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

options := NewPdfExportOptions()
options.DrawSlidesFrame = true
result, _, e := c.SlidesApi.Convert(source, "pdf", "", "", "", [ 2, 4 ], options)
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
