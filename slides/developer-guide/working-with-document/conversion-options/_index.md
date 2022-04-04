---
title: "Conversion Options"
type: docs
url: /conversion-options/
weight: 30
---

## **Introduction**

You can use various options with the [conversion](/slides/convert-powerpoint-documents-to-other-file-formats/) features. The options are provided as JSON data in the request body and can be used with all conversion methods (for presentations, slides, or shapes).

{{% alert color="primary" %}} 

Value enumerations for some options describe parameter values with names for .NET SDK. The member names may differ for other Aspose.Slides SDKs based on their naming convention.

{{% /alert %}} 

## **Common Export Options**

The following options may be used with any file format that a presentation is converted to:

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|DefaultRegularFont|string|Specifies the default regular font used when a presentation font is not found.|
|Height|double|Specifies the height of pages or images in an output document.|
|Width|double|Specifies the width of pages or images in an output document.|

## **Format Export Options**

The options below are format-specific. Check the tables to see what options can be used with the file format in your conversion operation. 

### **BMP Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|CommentsAreaColor|integer|Specifies the color of the comment area. Applies only when comments are displayed on the right.|
|CommentsAreaWidth|integer|Specifies the width of the comment area in pixels. Applies only when comments are displayed on the right.|
|CommentsPosition|CommentsPositionEnum|Specifies the position of slide comments.|
|NotesPosition|NotesPositionEnum|Specifies the position of slide notes.|

{{< expand-list title="CommentsPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Bottom|Comments should be displayed at the bottom of pages.|
|None|Comments should not be displayed at all. The default value.|
|Right|Comments should be displayed to the right of pages.|
{{< /expand-list >}}

{{< expand-list title="NotesPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|BottomFull|Notes should be fully displayed using additional pages when necessary.|
|BottomTruncated|Notes should be displayed on a single page.|
|None|Notes should not be displayed at all. The default value.|
|{{< /expand-list >}}||

### **GIF Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|CommentsAreaColor|integer|Specifies the color of the comment area. Applies only when comments are displayed on the right.|
|CommentsAreaWidth|integer|Specifies the width of the comment area in pixels. Applies only when comments are displayed on the right.|
|CommentsPosition|CommentsPositionEnum|Specifies the position of slide comments.|
|NotesPosition|NotesPositionEnum|Specifies the position of slide notes.|

{{< expand-list title="CommentsPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Bottom|Comments should be displayed at the bottom of pages.|
|None|Comments should not be displayed at all. The default value.|
|Right|Comments should be displayed to the right of pages.|
{{< /expand-list >}}

{{< expand-list title="NotesPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|BottomFull|Notes should be fully displayed using additional pages when necessary.|
|BottomTruncated|Notes should be displayed on a single page.|
|None|Notes should not be displayed at all. The default value.|
|{{< /expand-list >}}||

### **HTML Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|CommentsAreaColor|integer|Specifies the color of the comment area. Applies only when comments are displayed on the right.|
|CommentsAreaWidth|integer|Specifies the width of the comment area in pixels. Applies only when comments are displayed on the right.|
|CommentsPosition|CommentsPositionEnum|Specifies the position of slide comments.|
|DeletePicturesCroppedAreas|boolean|Specifies whether the cropped parts remain as part of the document or not. When `true`, the cropped parts are removed. When `false`, they are serialized in the document (and this may result in a larger file).|
|JpegQuality|integer|Specifies the quality of JPEG images. The default value is 95.|
|NotesPosition|NotesPositionEnum|Specifies the position of slide notes.|
|PicturesCompression|PicturesCompressionEnum|Specifies the compression level for pictures.|
|SaveAsZip|boolean|Specifies whether the output document is saved as a zip file or not.|
|ShowCommentsByNoAuthor|boolean|Specifies whether comments without an author are displayed or not.|
|ShowHiddenSlides|boolean|Specifies whether the generated document should include hidden slides or not.|
|SubDirectoryName|string|Specifies the subdirectory name in the output zip file to store external files.|
|SvgResponsiveLayout|boolean|Specifies whether the layout is made responsive (by excluding the width and height attributes from an SVG container) or not.|

{{< expand-list title="CommentsPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Bottom|Comments should be displayed at the bottom of pages.|
|None|Comments should not be displayed at all. The default value.|
|Right|Comments should be displayed to the right of pages.|
{{< /expand-list >}}

{{< expand-list title="NotesPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|BottomFull|Notes should be fully displayed using additional pages as it is needed.|
|BottomTruncated|Notes should be displayed on a single page.|
|None|Notes should not be displayed at all. The default value.|
|{{< /expand-list >}}||

{{< expand-list title="PicturesCompressionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|DocumentResolution|Use document resolution. Pictures will not be compressed and used in the output document as-is.|
|Dpi150|Good quality for web pages and projectors.|
|Dpi220|Excellent quality on most printers and screens.|
|Dpi330|Good quality for high-definition (HD) displays.|
|Dpi72|Default compression level.|
|Dpi96|Minimize document size for sharing.|
{{< /expand-list >}}

### **HTML5 Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|AnimateTransitions|boolean|Specifies whether slide transitions are animated or not.|
|AnimateShapes|boolean|Specifies whether shapes are animated or not.|

### **JPG Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|CommentsAreaColor|integer|Specifies the color of the comment area. Applies only when comments are displayed on the right.|
|CommentsAreaWidth|integer|Specifies the width of the comment area in pixels. Applies only when comments are displayed on the right.|
|CommentsPosition|CommentsPositionEnum|Specifies the position of slide comments.|
|NotesPosition|NotesPositionEnum|Specifies the position of slide notes.|

{{< expand-list title="CommentsPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Bottom|Comments should be displayed at the bottom of pages.|
|None|Comments should not be displayed at all. The default value.|
|Right|Comments should be displayed to the right of pages.|
{{< /expand-list >}}

{{< expand-list title="NotesPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|BottomFull|Notes should be fully displayed using additional pages when necessary.|
|BottomTruncated|Notes should be displayed on a single page.|
|None|Notes should not be displayed at all. The default value.|
|{{< /expand-list >}}||

### **PDF Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|AccessPermissions|AccessPermissionsEnum|Specifies the access permissions that will be granted when the document is opened with user access.|
|AdditionalCommonFontFamilies|List\<string\>|Specifies an array of user-defined names of font families to be considered common.|
|ApplyImageTransparent|boolean|Specifies whether the `ImageTransparentColor` option should be applied to images or not.|
|CommentsAreaColor|integer|Specifies the color of the comment area. Applies only if comments are displayed on the right.|
|CommentsAreaWidth|integer|Specifies the width of the comment area in pixels. Applies only if comments are displayed on the right.|
|CommentsPosition|CommentsPositionEnum|Specifies the position of slide comments on pages.|
|Compliance|ComplianceEnum|Specifies a desired conformance level for the generated document.|
|DrawSlidesFrame|boolean|Specifies whether each slide is enclosed with a black frame or not.|
|EmbedFullFonts|boolean|Specifies whether all characters of fonts or only a used subset should be embedded.|
|EmbedTrueTypeFontsForASCII|boolean|Specifies whether common fonts for ASCII (33..127 code range) text should be embedded or not. Fonts for character codes greater than 127 are always embedded. The list of common fonts includes the base 14 PDF fonts and additional user-specified fonts.|
|ImageTransparentColor|string|Specifies a transparent color for images.|
|JpegQuality|integer|Specifies the quality of JPEG images. The default value is 95.|
|NotesPosition|NotesPositionEnum|Specifies the position of slide notes on pages.|
|Password|string|Specifies the user password to protect the output document.|
|SaveMetafilesAsPng|boolean|Specifies whether all metafiles used in a presentation should be converted to PNG images or not.|
|ShowCommentsByNoAuthor|boolean|Specifies whether comments without an author are displayed or not.|
|ShowHiddenSlides|boolean|Specifies whether the generated document should include hidden slides or not.|
|SufficientResolution|double|Specifies the resolution of images. Affects the output file size, export time, and image quality. The default value is 96.|
|TextCompression|TextCompressionEnum|Specifies compression type to be used for all text content.|

{{< expand-list title="AccessPermissionsEnum" >}}

{{% alert color="primary" %}}

The following values may be used together as a combination of choices.

{{% /alert %}} 

|**Value**|**Description**|
| :- | :- |
|AddOrModifyFields|A user may add or modify text annotations, fill in interactive form fields, and, if the bit `ModifyContent` is also set, create or modify interactive form fields (including signature fields).|
|AssembleDocument|A user may assemble the document (insert, rotate, or delete pages and create bookmarks or thumbnail images), even if the bit `ModifyContent` is clear.|
|CopyTextAndGraphics|A user may copy or otherwise extract text and graphics from the document by operations other than that controlled by the bit `ExtractTextAndGraphics`.|
|ExtractTextAndGraphics|A user may extract text and graphics in support of accessibility to users with disabilities or for other purposes.|
|FillExistingFields|A user may fill in existing interactive form fields (including signature fields), even if the bit `AddOrModifyFields` is clear.|
|HighQualityPrint|A user may print the document to a representation from which a faithful digital copy of the PDF content could be generated. When this bit is clear (and the bit `PrintDocument` is set), printing is limited to a low-level representation of the appearance, possibly of degraded quality.|
|ModifyContent|A user may modify the contents of the document by operations other than those controlled by the bits `AddOrModifyFields`, `FillExistingFields`, `AssembleDocument`.|
|None|A user does not have access permissions.|
|PrintDocument|A user may print the document (perhaps not at the highest quality level, depending on whether the bit `HighQualityPrint` is also set).|
{{< /expand-list >}}

{{< expand-list title="CommentsPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Bottom|Comments should be displayed at the bottom of pages.|
|None|Comments should not be displayed at all. The default value.|
|Right|Comments should be displayed to the right of pages.|
{{< /expand-list >}}

{{< expand-list title="ComplianceEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Pdf15|Comply with the PDF 1.5 standard.|
|PdfA1a|Comply with the PDF/A-1a standard.|
|PdfA1b|Comply with the PDF/A-1b standard.|
|PdfUa|Comply with the PDF/UA standard.|
{{< /expand-list >}}

{{< expand-list title="NotesPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|BottomFull|Notes should be fully displayed using additional pages when necessary.|
|BottomTruncated|Notes should be displayed on a single page.|
|None|Notes should not be displayed at all. The default value.|
|{{< /expand-list >}}||

{{< expand-list title="TextCompressionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Flate|Use flate (ZIP) compression.|
|None|Compression is not applied.|
{{< /expand-list >}}

### **PNG Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|CommentsAreaColor|integer|Specifies the color of the comment area. Applies only if comments are displayed on the right.|
|CommentsAreaWidth|integer|Specifies the width of the comment area in pixels. Applies only if comments are displayed on the right.|
|CommentsPosition|CommentsPositionEnum|Specifies the position of slide comments.|
|NotesPosition|NotesPositionEnum|Specifies the position of slide notes.|

{{< expand-list title="CommentsPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Bottom|Comments should be displayed at the bottom of pages.|
|None|Comments should not be displayed at all. The default value.|
|Right|Comments should be displayed to the right of pages.|
{{< /expand-list >}}

{{< expand-list title="NotesPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|BottomFull|Notes should be fully displayed using additional pages when necessary.|
|BottomTruncated|Notes should be displayed on a single page.|
|None|Notes should not be displayed at all. The default value.|
|{{< /expand-list >}}||

### **PPTX Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|Conformance|ConformanceEnum|Specifies the conformance class to which the PresentationML document conforms.|

{{< expand-list title="ConformanceEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Ecma3762006|The document conforms to the ECMA376:2006.|
|Iso295002008Transitional|The document conforms to the ISO/IEC 29500:2008 Transitional conformance class.|
|Iso295002008Strict|The document conforms to the ISO/IEC 29500:2008 Strict conformance class.|
{{< /expand-list >}}

### **SVG Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|DeletePicturesCroppedAreas|boolean|Specifies whether the cropped parts remain as part of the document or not. When `true`, the cropped parts will be removed. When `false`, they are serialized in the document (and this may result in a larger file).|
|Disable3DText|boolean|Specifies whether the 3D text is disabled in the output SVG image or not.|
|DisableGradientSplit|boolean|Specifies whether to disable splitting FromCornerX and FromCenter gradients or not.|
|DisableLineEndCropping|boolean|SVG 1.1 lacks the ability to define insets for markers. Aspose.Slides SVG writing engine has a workaround for that problem: it crops the end of the line with an arrow so that the line doesn't overlap the markers. This option specifies whether this behavior is disabled or not.|
|ExternalFontsHandling|ExternalFontsHandlingEnum|Specifies how externally loaded fonts are handled.|
|JpegQuality|integer|Specifies the quality of JPEG images. The default value is 95.|
|MetafileRasterizationDpi|integer|Specifies the lower resolution limit for metafile rasterization.|
|PicturesCompression|PicturesCompressionEnum|Specifies the compression level for pictures.|
|VectorizeText|boolean|Specifies whether the text on slides will be saved as graphics or not.|

{{< expand-list title="ExternalFontsHandlingEnum" >}}
|**Value**|**Description**|
| :- | :- |
|AddLinksToFontFiles|Add links to separate font files to the style section of the output SVG file.|
|Embed|Save font data directly to the output SVG file. Please check all license agreements for external fonts before using this option.|
|Vectorize|Save all text using external fonts as graphics.|
{{< /expand-list >}}

{{< expand-list title="PicturesCompressionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|DocumentResolution|Use document resolution. Pictures will not be compressed and used in the output document as-is.|
|Dpi150|Good quality for web pages and projectors.|
|Dpi220|Excellent quality on most printers and screens.|
|Dpi330|Good quality for high-definition (HD) displays.|
|Dpi72|Default compression level.|
|Dpi96|Minimize document size for sharing.|
{{< /expand-list >}}

### **SWF Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|CommentsAreaColor|integer|Specifies the color of the comment area. Applies only when comments are displayed on the right.|
|CommentsAreaWidth|integer|Specifies the width of the comment area in pixels. Applies only when comments are displayed on the right.|
|CommentsPosition|CommentsPositionEnum|Specifies the position of slide comments.|
|Compressed|boolean|Specifies whether the generated SWF document should be compressed or not. The default value is true.|
|EnableContextMenu|boolean|Specifies whether the context menu is enabled. The default value is true.|
|JpegQuality|integer|Specifies the quality of JPEG images. The default value is 95.|
|LogoImage|string|Specifies the image that will be displayed as a logo at the top-right corner of the viewer. The image data is a Base64 string. The image should be 32x64 pixels in the PNG format. Otherwise, the logo may be displayed improperly.|
|LogoLink|string|Specifies the full hyperlink address for a logo. Has effect only when `LogoImage` is specified.|
|NotesPosition|NotesPositionEnum|Specifies the position of slide notes.|
|ShowBottomPane|boolean|Specifies whether to show the bottom pane or not. Can be overridden in flashvars. The default value is true.|
|ShowCommentsByNoAuthor|boolean|Specifies whether comments without an author are displayed or not.|
|ShowFullScreen|boolean|Specifies whether to show the fullscreen button or not. Can be overridden in flashvars. The default value is true.|
|ShowHiddenSlides|boolean|Specifies whether the generated document should include hidden slides or not.|
|ShowLeftPane|boolean|Specifies whether to show the left pane or not. Can be overridden in flashvars. The default value is true.|
|ShowPageBorder|boolean|Specifies whether a border around pages is shown or not. The default value is true.|
|ShowPageStepper|boolean|Specifies whether to show the page stepper or not. Can be overridden in flashvars. The default value is true.|
|ShowSearch|boolean|Specifies whether to show the search section or not. Can be overridden in flashvars. The default value is true.|
|ShowTopPane|boolean|Specifies whether to show the whole top pane or not. Can be overridden in flashvars. The default value is true.|
|StartOpenLeftPane|boolean|Specifies whether to start with the opened left pane. Can be overridden in flashvars.|
|ViewerIncluded|boolean|Specifies whether the generated SWF document should include the integrated document viewer or not. The default value is true.|

{{< expand-list title="CommentsPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Bottom|Comments should be displayed at the bottom of pages.|
|None|Comments should not be displayed at all. The default value.|
|Right|Comments should be displayed to the right of pages.|
{{< /expand-list >}}

{{< expand-list title="NotesPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|BottomFull|Notes should be fully displayed using additional pages when necessary.|
|BottomTruncated|Notes should be displayed on a single page.|
|None|Notes should not be displayed at all. The default value.|
|{{< /expand-list >}}||

### **TIFF Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|CommentsAreaColor|integer|Specifies the color of the comment area. Applies only when comments are displayed on the right.|
|CommentsAreaWidth|integer|Specifies the width of the comment area in pixels. Applies only when comments are displayed on the right.|
|CommentsPosition|CommentsPositionEnum|Specifies the position of slide comments on pages.|
|Compression|CompressionEnum|Specifies a compression type.|
|DpiX|integer|Specifies the horizontal resolution in dots per inch.|
|DpiY|integer|Specifies the vertical resolution in dots per inch.|
|NotesPosition|NotesPositionEnum|Specifies the position of slide notes on images.|
|PixelFormat|PixelFormatEnum|Specifies a pixel format for the generated images.|
|ShowCommentsByNoAuthor|boolean|Specifies whether comments without an author are displayed or not.|
|ShowHiddenSlides|boolean|Specifies whether the generated document should include hidden slides or not.|

{{< expand-list title="CommentsPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Bottom|Comments should be displayed at the bottom of pages.|
|None|Comments should not be displayed at all. The default value.|
|Right|Comments should be displayed to the right of pages.|
{{< /expand-list >}}

{{< expand-list title="CompressionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|CCITT3|Use the CCITT3 compression scheme.|
|CCITT4|Use the CCITT4 compression scheme.|
|Default|Use the default compression scheme (LZW).|
|LZW|Use the LZW compression scheme.|
|None|Compression is not applied.|
|RLE|Use the RLE compression scheme.|
{{< /expand-list >}}

{{< expand-list title="NotesPositionEnum" >}}
|**Value**|**Description**|
| :- | :- |
|BottomFull|Notes should be fully displayed using additional pages when necessary.|
|BottomTruncated|Notes should be displayed on a single page.|
|None|Notes should not be displayed at all. The default value.|
|{{< /expand-list >}}||

{{< expand-list title="PixelFormatEnum" >}}
|**Value**|**Description**|
| :- | :- |
|Format1bppIndexed|1 bit per pixel, indexed.|
|Format24bppRgb|24 bits per pixel, RGB.|
|Format32bppArgb|32 bits per pixel, ARGB.|
|Format4bppIndexed|4 bits per pixel, indexed.|
|Format8bppIndexed|8 bits per pixel, indexed.|
{{< /expand-list >}}

### **XAML Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|ExportHiddenSlides|boolean|Specifies whether the generated document should include hidden slides or not.|

### **XPS Options**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|DrawSlidesFrame|boolean|Specifies whether each slide is enclosed with a black frame or not.|
|SaveMetafilesAsPng|boolean|Specifies whether all metafiles used in a presentation should be converted to PNG images or not.|
|ShowHiddenSlides|boolean|Specifies whether the generated document should include hidden slides or not.|

## **cURL Example**

Convert **MyPresentation.pptx** presentation to **MyPresentation.pdf** document. Draw a black frame around each slide. Set the quality for JPEG images to 90. The output PDF document must conform to the PDF/UA standard.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/convert/Pdf" \
     -H "authorization: Bearer <access_token>" \
     -H "accept: multipart/form-data" \
     -F "file=@MyPresentation.pptx" \
     -F "data=@PdfOptions.json;filename=" \
     -o MyPresentation.pdf
```

PdfOptions.json file:
```json
{
    "DrawSlidesFrame": "true",
    "JpegQuality": "90",
    "Compliance": "PdfUa"
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

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**

Convert **MyPresentation.pptx** presentation to a PDF document. Draw a black frame around each slide. Set the quality for JPEG images to 90. The output PDF document must conform to the PDF/UA standard.

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System.IO;

class Test
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        // Set options for the output PDF document.
        var pdfOptions = new PdfExportOptions
        {
            DrawSlidesFrame = true,
            JpegQuality = 90,
            Compliance = PdfExportOptions.ComplianceEnum.PdfUa
        };

        // Convert the presentation to PDF format.
        using var presentationStream = File.OpenRead("MyPresentation.pptx");
        using var pdfStream = slidesApi.Convert(presentationStream, ExportFormat.Pdf, options: pdfOptions);

        using var fileStream = File.Create("MyPresentation.pdf");
        pdfStream.CopyTo(fileStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws IOException, ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        // Set options for the output PDF document.
        var pdfOptions = new PdfExportOptions();
        pdfOptions.setDrawSlidesFrame(true);
        pdfOptions.setJpegQuality(90);
        pdfOptions.setCompliance(PdfExportOptions.ComplianceEnum.PDFUA);

        // Convert the presentation to PDF format.
        var presentationData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        var pdfFile = slidesApi.convert(presentationData, ExportFormat.PDF, null, null, null, null, pdfOptions);

        System.out.println("The converted document was saved to: " + pdfFile.toPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\PdfExportOptions;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

// Set options for the output PDF document.
$pdfOptions = new PdfExportOptions();
$pdfOptions->setDrawSlidesFrame(true);
$pdfOptions->setJpegQuality(90);
$pdfOptions->setCompliance("PdfUa");

// Convert the presentation to PDF format.
$presentationFile = fopen("MyPresentation.pptx", 'r');
$pdfFile = $slidesApi->convert($presentationFile, ExportFormat::PDF, null, null, null, null, $pdfOptions);

print("The converted document was saved to " . $pdfFile->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_key"

slides_api = SlidesApi.new(configuration)

# Set options for the output PDF document.
pdf_options = PdfExportOptions.new
pdf_options.draw_slides_frame = true
pdf_options.jpeg_quality = 90
pdf_options.compliance = "PDFUA"

# Convert the presentation to PDF format.
presentation_data = File.binread("MyPresentation.pptx")
pdf_data = slides_api.convert(presentation_data, ExportFormat::PDF, nil, nil, nil, nil, pdf_options)

File.binwrite("MyPresentation.pdf", pdf_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.pdf_export_options import PdfExportOptions
from asposeslidescloud.models.export_format import ExportFormat

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

# Set options for the output PDF document.
pdf_options = PdfExportOptions()
pdf_options.draw_slides_frame = True
pdf_options.jpeg_quality = 90
pdf_options.compliance = "PdfUa"

# Convert the presentation to PDF format.
with open("MyPresentation.pptx", "rb") as presentation_file:
    pdf_path = slides_api.convert(presentation_file.read(), ExportFormat.PDF, None, None, None, None, pdf_options)

print("The converted document was saved to: " + pdf_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require('fs')

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

// Set options for the output PDF document.
const pdfOptions = new cloud.PdfExportOptions()
pdfOptions.drawSlidesFrame = true
pdfOptions.jpegQuality = 90
pdfOptions.compliance = "PdfUa"

// Convert the presentation to PDF format.
const fileStream = fs.createReadStream("MyPresentation.pptx")
slidesApi.convert(fileStream, "pdf", null, null, null, null, pdfOptions).then((response) => {
    fs.writeFile("MyPresentation.pdf", response.body, (error) => {
        if (error) throw error
    })
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-go

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "my_client_id"
cfg.AppKey = "my_client_key"
api := asposeslidescloud.NewAPIClient(cfg)

source, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

// Set options for the output PDF document.
pdfOptions := NewPdfExportOptions()
pdfOptions.DrawSlidesFrame = true
pdfOptions.JpegQuality = 90
pdfOptions.Compliance = "PdfUa"

// Convert the presentation to PDF format.
result, _, e := c.SlidesApi.Convert(source, "pdf", "", "", "", nil, pdfOptions)
if e != nil {
    fmt.Printf("Error: %v.", e)
}

fmt.Printf("The converted document was saved to  %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/PdfExportOptions.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

    // Set options for the output PDF document.
    auto pdfOptions = std::make_shared<PdfExportOptions>();
    pdfOptions->setDrawSlidesFrame(true);
    pdfOptions->setJpegQuality(90);
    pdfOptions->setCompliance(to_string_t("PdfUa"));

    auto presentationStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto presentationContent = std::make_shared<HttpContent>();
    presentationContent->setData(presentationStream);

    // Convert the presentation to PDF format.
    auto responseContent = slidesApi->convert(
        presentationContent, to_string_t("pdf"), utility::string_t(), utility::string_t(), utility::string_t(), {}, pdfOptions).get();

    std::ofstream pdfStream("MyPresentation.pdf", std::ofstream::binary);
    responseContent.writeTo(pdfStream);

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
