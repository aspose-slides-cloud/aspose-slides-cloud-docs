---
title: "Download a Slide from a PowerPoint Presentation"
type: docs
url: /download-a-slide-from-a-powerpoint-presentation/
weight: 10
---

## **Download**

## **Introduction**
Aspose.Slides Cloud allows you to easily export a particular slide from a PowerPoint Document. Aspose.Slides Cloud supports downloading in ppt, ppt, ppt, ppsx, pps, ppsm, potx, otm, odp, otp, pdf, html, xps, SWF, SVG, tiff, jpeg, png, gif, and BMP image formats. 

**Use GET or POST methods to download data in response body. Use PUT method to save the file on storage.**

### **API Information**
|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/{format}|POST|Save a presentation to a specified format.|[PostSlidesSaveAs](https://apireference.aspose.cloud/slides/#/Document/PostSlidesSaveAs)|
|/slides/{name}/{format}|PUT|Save a presentation to a specified format.|[PutSlidesSaveAs](https://apireference.aspose.cloud/slides/#/Document/PutSlidesSaveAs)|
|/slides/{name}/slides/{slideIndex}/{format}|POST|Save a slide to a specified format.|[PostSlideSaveAs](https://apireference.aspose.cloud/slides/#/Slides/PostSlideSaveAs)|
|/slides/{name}/slides/{slideIndex}/{format}|PUT|Save a slide to a specified format.|[PutSlideSaveAs](https://apireference.aspose.cloud/slides/#/Slides/PutSlideSaveAs)|
|/slides/slides/{slideIndex}/notesSlide/{format}|POST|Convert notes slide to the specified image format.|[PostGetNotesSlideWithFormat](https://apireference.aspose.cloud/slides/#/NotesSlide/PostGetNotesSlideWithFormat)|
|/slides/{name}/slides/{slideIndex}/notesSlide/{format}|GET|Convert notes slide to the specified image format.|[GetNotesSlideWithFormat](https://apireference.aspose.cloud/slides/#/NotesSlide/GetNotesSlideWithFormat)|
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/{format}|POST|Render shape to specified picture format.|[PostShapeSaveAs](https://apireference.aspose.cloud/slides/#/Shapes/PostShapeSaveAs)|
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/{format}|PUT|Render shape to specified picture format.|[PutShapeSaveAs](https://apireference.aspose.cloud/slides/#/Shapes/PutShapeSaveAs)|

- **slide-index** - index of slide starting from 1
- **shape-index** - index of shape starting from 1
- **format** - format of the saved the presentation

{{< expand-list title="Valid format values:" >}}
| **Format** | **Presentation** | **Slide** | **Notes slide** | **Shape** | 
| :- | :- | :- | :- | :- |
| pptx |**yes** |**yes** | no | no |
| ppt |**yes** |**yes** | no | no |
| pptm |**yes** |**yes** | no | no |
| ppsx |**yes** |**yes** | no | no |
| pps |**yes** |**yes** | no | no |
| ppsm |**yes** |**yes** | no | no |
| pot |**yes** |**yes** | no | no |
| potx |**yes** |**yes** | no | no |
| potm |**yes** |**yes** | no | no |
| odp |**yes** |**yes** | no | no |
| fodp |**yes** |**yes** | no | no |
| otp |**yes** |**yes** | no | no |
| pdf |**yes** |**yes** | no | no |
| html |**yes** |**yes** | no | no |
| xps |**yes** |**yes** | no | no |
| swf |**yes** | no | no | no |
| svg |**yes** |**yes** | no |**yes** |
| tiff |**yes** |**yes** |**yes** |**yes** |
| jpeg |**yes** |**yes** |**yes** |**yes** |
| png |**yes** |**yes** |**yes** |**yes** |
| gif |**yes** |**yes** |**yes** |**yes** |
| bmp |**yes** |**yes** |**yes** |**yes** |
{{< /expand-list >}}

{{< expand-list title="Request Parameters" >}}
| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
| password | GET/POST/PUT | any | string | Optional | Presentation password |
| folder | GET/POST/PUT | any | string | Optional | Presentation folder |
| storage | GET/POST/PUT | any | string | Optional | Presentation storage |
| outPath | PUT | any | string | Required | Save output file to storage instead of return it to HTTP-response |
| fontsFolder | GET/POST/PUT | any | string | Optional | Storage folder containing custom fonts to be used with the presentation |
| height | GET/POST/PUT | slide, notesSlide | integer | Optional | Height of resulting image in pixels. Default value is slide height |
| width | GET/POST/PUT | slide, notesSlide | integer | Optional | Width of resulting image in pixels. Default value is slide width |
| scaleX | GET/POST/PUT | shape | float | Optional | X scale ratio |
| scaleY | GET/POST/PUT | shape | float | Optional | Y scale ratio |
| bounds | GET/POST/PUT | shape | Slide / Shape / Appearance | Optional | Shape thumbnail bounds type | 

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*
{{< /expand-list >}}

{{< expand-list title="Export options" >}}
**Depending on the parameter "format" service can receive export options in the request body**

{{< expand-list title="All formats" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| DefaultRegularFont | string | Specifies default font to be used if a custom font is not available. |
{{< /expand-list >}}

{{< expand-list title="PPTX format" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| Conformance | Ecma3762006 / Iso295002008Transitional / Iso295002008Strict | Specifies conformance class to which the PresentationML document conforms. |
{{< /expand-list >}}

{{< expand-list title="PDF format" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| TextCompression | None / Flat | Specifies compression type to be used for all textual content in the document. |
| EmbedFullFonts | bool | Determines if all characters of font should be embedded or only used subset. |
| Compliance | Pdf15 / PdfA1a / PdfA1b / PdfUa | Desired conformance level for generated PDF document. |
| SufficientResolution | float | Value determining the resolution of images inside PDF document. Property affects file size, time of export, and image quality. The default value is 96. |
| JpegQuality | byte | Value determining the quality of the JPEG images inside PDF document. Has an effect only when a document contains JPEG images. The value may vary from 0 to 100 where 0 means the worst quality but maximum compression and 100 means the best quality but minimum compression. The default value is 100. |
| DrawSlidesFrame | bool | True to draw a black frame around each slide. Default is false. |
| ShowHiddenSlides | bool | Specifies whether the generated document should include hidden slides or not. Default is false. |
| SaveMetafilesAsPng | bool | True to convert all metafiles used in a presentation to the PNG images. Default is true. |
| PdfPassword | string | Setting user password to protect the PDF document. |
| EmbedTrueTypeFontsForASCII | bool | Determines service will embed common fonts for ASCII. Default is true. |
| ImageTransparentColor | string | Image transparent color. |
| ApplyImageTransparent | bool | True to apply specified ImageTransparentColor to an image. |
| NotesPosition | None / BottomFull / BottomTruncated | Determines the rule to render notes into exported document. Default is None. |
| CommentsPosition | None / Bottom / Right | The position of the comments on the page. Default is None. |
| CommentsAreaWidth | int | The width of the comment output area in pixels. Applies only if comments are displayed on the right. Minimal and the default value is 150. |
| CommentsAreaColor | string | The color of comments area. Applies only if comments are displayed on the right. The default is sky blue. |
| ShowCommentsByNoAuthor | bool | True if comments that have no author are displayed. (Applies only if comments are displayed). | 
| AccessPermissions | flags | A comma-separated list containing some of the following options: PrintDocument, ModifyContent, CopyTextAndGraphics, AddOrModifyFields, FillExistingFields, ExtractTextAndGraphics, AssembleDocument, HighQualityPrint; None to disallow all.|

**Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.**

{{< /expand-list >}}

{{< expand-list title="HTML format" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| SaveAsZip | bool | Html file with external resources will be packed into zip file. |
| SubDirectoryName | string | Subdirectory in zip-file for store external files (images, SVG, etc.). Can be empty for store external files in the root of zip-file. |
| ShowHiddenSlides | bool | Specifies whether the generated document should include hidden slides or not. Default is false. |
| JpegQuality | byte | Value determining the quality of the JPEG images. Has an effect only when a document contains JPEG images. The value may vary from 0 to 100 where 0 means the worst quality but maximum compression and 100 means the best quality but minimum compression. The default value is 95. |
| PicturesCompression | Dpi330 / Dpi220 / Dpi150 / Dpi96 / Dpi72 / DocumentResolution | Represents the pictures compression level. |
| DeletePicturesCroppedAreas | bool | Indicates whether the cropped parts remain as part of the document. If true the cropped parts will be removed, if false they will be serialized in the document (which can possibly lead to a larger file). |
| NotesPosition | None / BottomFull / BottomTruncated | Determines the rule to render notes into exported document. Default is None. |
| CommentsPosition | None / Bottom / Right | The position of the comments on the page. Default is None. |
| CommentsAreaWidth | int | The width of the comment output area in pixels. Applies only if comments are displayed on the right. Minimal and the default value is 150. |
| CommentsAreaColor | string | The color of comments area. Applies only if comments are displayed on the right. The default is sky blue. |
| ShowCommentsByNoAuthor | bool | True if comments that have no author are displayed. (Applies only if comments are displayed). | 
| SvgResponsiveLayout | bool | True to make layout responsive by excluding width and height attributes from SVG container. | 

**Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.**
{{< /expand-list >}}

{{< expand-list title="TIFF format" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| TiffCompressionType | Default / None / CCITT3 / CCITT4 / LZW / RLE | Specifies the compression scheme. 
| Width | Int | Specifies the width of the picture in pixels. |
| Height | Int | Specifies the height of the picture in pixels. |
| DpiX | Int | Specifies horizontal resolution of the picture. |
| DpiY | Int | Specifies vertical resolution of the picture. |
| NotesPosition | None / BottomFull / BottomTruncated | Determines the rule to render notes into exported document. |
| ShowHiddenSlides | bool | Specifies whether the generated document should include hidden slides or not. Default is false. |
| PixelFormat | Format1bppIndexed / Format4bppIndexed / Format8bppIndexed / Format24bppRgb / Format32bppArgb | Pixel format for the generated images. |
| NotesPosition | None / BottomFull / BottomTruncated | Determines the rule to render notes into exported document. Default is None. |
| CommentsPosition | None / Bottom / Right | The position of the comments on the page. Default is None. |
| CommentsAreaWidth | int | The width of the comment output area in pixels. Applies only if comments are displayed on the right. Minimal and the default value is 150. |
| CommentsAreaColor | string | The color of comments area. Applies only if comments are displayed on the right. The default is sky blue. |
| ShowCommentsByNoAuthor | bool | True if comments that have no author are displayed. (Applies only if comments are displayed). | 

**Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.**
{{< /expand-list >}}

{{< expand-list title="SWF format" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| ShowHiddenSlides | bool | True if the generated document should include hidden slides. Default is false. |
| Compressed | bool | True if the generated SWF document should be compressed. Default is true. |
| ViewerIncluded | bool | True if the generated SWF document should include the integrated document viewer. Default is true. |
| ShowPageBorder | bool | True if the border around pages should be shown. Default is true. |
| ShowFullScreen | bool | True to show or hide the fullscreen button. Default is true. |
| ShowPageStepper | bool | True to show or hide page stepper. Default is true. |
| ShowSearch | bool | True to show or hide search section. Default is true. |
| ShowTopPane | bool | True to show or hide the top pane. Default is true. |
| ShowBottomPane | bool | True to show or hide the bottom pane. Default is true. |
| ShowLeftPane | bool | True to show or hide the left pane. Default is true. |
| StartOpenLeftPane | bool | True to start with opened left pane. Default is false. |
| EnableContextMenu | bool | True to enable context menu. Default is true. |
| LogoImage | string | Image that will be displayed as a logo in the top right corner of the viewer. The image data is a base 64 string. The image should be a 32x64 pixels PNG image, otherwise the logo can be displayed improperly. |
| LogoLink | string | Gets or sets the full hyperlink address for a logo. Has an effect only if a LogoImage is specified. |
| JpegQuality | byte | Specifies the quality of JPEG images. Default is 95. |
| NotesPosition | None / BottomFull / BottomTruncated | Determines the rule to render notes into exported document. Default is None. |
| CommentsPosition | None / Bottom / Right | The position of the comments on the page. Default is None. |
| CommentsAreaWidth | int | The width of the comment output area in pixels. Applies only if comments are displayed on the right. Minimal and the default value is 150. |
| CommentsAreaColor | string | The color of comments area. Applies only if comments are displayed on the right. The default is sky blue. |
| ShowCommentsByNoAuthor | bool | True if comments that have no author are displayed. (Applies only if comments are displayed). | 

**Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.**
{{< /expand-list >}}

{{< expand-list title="SVG format" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| VectorizeText | bool | True if the text on a slide will be saved as graphics. |
| MetafileRasterizationDpi | int | The lower resolution limit for metafile rasterization. Default is 72. |
| Disable3DText | bool | True if the 3D text is disabled in SVG. |
| DisableGradientSplit | bool | True to disable splitting FromCornerX and FromCenter gradients. |
| DisableLineEndCropping | bool | True to disable line end cropping. |
| JpegQuality | int | The quality of JPEG images. Default is 85. |
| PicturesCompression | Dpi330 / Dpi220 / Dpi150 / Dpi96 / Dpi72 / DocumentResolution | Picture compression level. |
| DeletePicturesCroppedAreas | bool | True if the cropped parts of the document are removed. |
| ExternalFontsHandling | AddLinksToFontFiles / Embed / Vectorize | The way of handling externally loaded fonts. |
{{< /expand-list >}}

{{< expand-list title="XPS format" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| ShowHiddenSlides | bool | True if the generated document should include hidden slides. Default is false. |
| SaveMetafilesAsPng | bool | True to convert all metafiles used in a presentation to the PNG images. Default is true. |
| DrawSlidesFrame | bool | True to draw a black frame around each slide. Default is false. |
{{< /expand-list >}}

{{< expand-list title="Image format (JPG, PNG, GIF and BMP formats)" >}}
| **Option** | **Type** | **Description**|
| :- | :- | :- |
| NotesPosition | None / BottomFull / BottomTruncated | Determines the rule to render notes into exported document. Default is None. |
| CommentsPosition | None / Bottom / Right | The position of the comments on the page. Default is None. |
| CommentsAreaWidth | int | The width of the comment output area in pixels. Applies only if comments are displayed on the right. Minimal and the default value is 150. |
| CommentsAreaColor | string | The color of comments area. Applies only if comments are displayed on the right. The default is sky blue. |
| ShowCommentsByNoAuthor | bool | True if comments that have no author are displayed. (Applies only if comments are displayed). | 

**Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.**
{{< /expand-list >}}

{{< /expand-list >}}

#### **HTTP GET**
Download presentation, slide, or shape in the requested format.


{{< tabs tabTotal="3" tabID="1" tabName1="Example 1" tabName2="Example 2" tabName3="Example 3" >}}

{{< tab tabNum="1" >}}

**Save presentation as ppt.**

```
GET https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/ppt
```

*Response* contains the conversion operation result.

{{< /tab >}}

{{< tab tabNum="2" >}}

**Save the second slide of the presentation as JPG with size 720x480.**

```
GET https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2/jpeg?width=720&height=480
```

*Response* contains the conversion operation result.

{{< /tab >}}

{{< tab tabNum="3" >}}

**Save the first shape of second slide of the presentation as PNG.**

```
GET https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2/shapes/1/png
```

*Response* contains the conversion operation result.

{{< /tab >}}

{{< /tabs >}}


#### **HTTP POST**
Saves presentation in requested format using the export options, if specified.

##### **Example 1.**
Save presentation as pdf with custom setting.

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pdf
```
{{< expand-list title="Request body:" >}}
**JSON**
```
{
    "TextCompression": 1,
    "EmbedFullFonts": true,
    "Compliance": 0,
    "JpegQuality": 50,
    "SaveMetafilesAsPng": false,
    "Password": null,
    "EmbedTrueTypeFontsForASCII": true
}
```

**XML**
```
<PdfExportOptions>
  <TextCompression>Flate</TextCompression>
  <EmbedFullFonts>True</EmbedFullFonts>
  <Compliance>Pdf15</Compliance>
  <JpegQuality>50</JpegQuality>
  <SaveMetafilesAsPng>False</SaveMetafilesAsPng>
  <Password/>
  <EmbedTrueTypeFontsForASCII>True</EmbedTrueTypeFontsForASCII>
</PdfExportOptions>
```
{{< /expand-list >}}

###### **Response**
Response contains the conversion operation result.

###### **.NET SDK code**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PdfExportOptions options = new PdfExportOptions
{
    TextCompression = PdfExportOptions.TextCompressionEnum.Flate,
    EmbedFullFonts = true,
    Compliance = PdfExportOptions.ComplianceEnum.Pdf15,
    JpegQuality = 50,
    SaveMetafilesAsPng = false,
    EmbedTrueTypeFontsForASCII = true
};
Stream response = api.DownloadPresentation("myPresentation.pptx", ExportFormat.Pdf, options, folder: "TempSlidesSDK");
response.CopyTo(File.Create("myPresentation.pdf"));
```

##### **Example 2.**
Save presentation as html and pack all external html-resources in zip.

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/html
```

{{< expand-list title="Request body:" >}}

**JSON**
```
{
    "SaveAsZip": true,
    "SubDirectoryName": null
}
```

**XML**
```
<HtmlExportOptions>
  <SaveAsZip>True</SaveAsZip>
  <SubDirectoryName/>
</HtmlExportOptions>
```

{{< /expand-list >}}

###### **Response**
Response contains the conversion operation result.

###### **.NET SDK code**
```csharp
Stream response = api.PostSlidesSaveAs(request);
response.CopyTo(File.Create("myPresentation.pdf"));
PostSlidesSaveAsRequest request = new PostSlidesSaveAsRequest
{
    Name = "myPresentation.pptx",
    Format = ExportFormat.Html,
    Options = new HtmlExportOptions
    {
        SaveAsZip = true
    }
};
Stream response = api.PostSlidesSaveAs(request);
response.CopyTo(File.Create("myPresentation.zip"));
```


##### **Example 3.**
Save presentation as tiff with custom save options.

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/tiff
```

{{< expand-list title="Request body:" >}}

**JSON**
```
{
    "Compression": 0,
    "Width": 1024,
    "Height": 768,
    "DpiX": 72,
    "DpiY": 72
}
```

**XML**
```
<TiffExportOptions>
  <Compression>Default</Compression>
  <Width>1024</Width>
  <Height>768</Height>
  <DpiX>72</DpiX>
  <DpiY>72</DpiY>
</TiffExportOptions>
```
{{< /expand-list >}}

###### **Response**
Response contains the conversion operation result.

###### **.NET SDK code**
```csharp
PostSlidesSaveAsRequest request = new PostSlidesSaveAsRequest
{
    Name = "NewPresentation.pptx",
    Folder = "TempSlidesSDK",
    Format = ExportFormat.Tiff,
    Options = new TiffExportOptions
    {
        Compression = TiffExportOptions.CompressionEnum.Default,
        Width = 1024,
        Height = 768,
        DpiX = 72,
        DpiY = 72
    }
};
Stream response = api.PostSlidesSaveAs(request);
response.CopyTo(File.Create("NewPresentation.tiff"));
```

```csharp
PostSlideSaveAsRequest request2 = new PostSlideSaveAsRequest
{
    Name = "NewPresentation.pptx",
    Folder = "TempSlidesSDK",
    Format = SlideExportFormat.Tiff,
    SlideIndex = 2,
    Options = new TiffExportOptions
    {
        Compression = TiffExportOptions.CompressionEnum.Default,
        Width = 1024,
        Height = 768,
        DpiX = 72,
        DpiY = 72
    }
};
Stream response2 = api.PostSlideSaveAs(request2);
response2.CopyTo(File.Create("NewPresentation-Slide2.tiff"));
```

```csharp
PostShapeSaveAsRequest request3 = new PostShapeSaveAsRequest
{
    Name = "NewPresentation.pptx",
    Folder = "TempSlidesSDK",
    Format = ShapeExportFormat.Png,
    SlideIndex = 2,
    ShapeIndex = 3
};
Stream response3 = api.PostShapeSaveAs(request3);
response3.CopyTo(File.Create("NewPresentation-Slide2-Shape3.png"));
```

#### **HTTP PUT**
Use for saving the exported file to Storage.

##### **Example**
Save the presentation as pdf to folder/myPresentation.pdf file on storage.

###### **Request**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pdf?outPath=folder/myPresentation.pdf
```

###### **Response**
Response is empty.

###### **.NET SDK code**
```csharp
const string outPath = "folder/myPresentation.pdf";
PutSlidesSaveAsRequest request = new PutSlidesSaveAsRequest
{
    Name = "myPresentation.pptx",
    Format = ExportFormat.Pdf,
    OutPath = outPath,
    Options = new PdfExportOptions
    {
        TextCompression = PdfExportOptions.TextCompressionEnum.Flate,
        EmbedFullFonts = true,
        Compliance = PdfExportOptions.ComplianceEnum.Pdf15,
        JpegQuality = 50,
        SaveMetafilesAsPng = false,
        EmbedTrueTypeFontsForASCII = true
    }
};
api.PutSlidesSaveAs(request);
Stream file = api.DownloadFile(new DownloadFileRequest { Path = outPath });
file.CopyTo(File.Create("myPresentation.pdf"));

const string outPath2 = "folder/myPresentation-slide2.pdf";
PutSlideSaveAsRequest request2 = new PutSlideSaveAsRequest
{
    Name = "myPresentation.pptx",
    Format = SlideExportFormat.Pdf,
    SlideIndex = 2,
    OutPath = outPath2,
    Options = new PdfExportOptions
    {
        TextCompression = PdfExportOptions.TextCompressionEnum.Flate,
        EmbedFullFonts = true,
        Compliance = PdfExportOptions.ComplianceEnum.Pdf15,
        JpegQuality = 50,
        SaveMetafilesAsPng = false,
        EmbedTrueTypeFontsForASCII = true
    }
};
api.PutSlideSaveAs(request2);
Stream file2 = api.DownloadFile(new DownloadFileRequest { Path = outPath2 });
file2.CopyTo(File.Create("myPresentation-Slide2.pdf"));

const string outPath3 = "folder/myPresentation-slide2-shape3.png";
PutShapeSaveAsRequest request3 = new PutShapeSaveAsRequest
{
    Name = "NewPresentation.pptx",
    Folder = "TempSlidesSDK",
    Format = ShapeExportFormat.Png,
    SlideIndex = 2,
    OutPath = outPath3
};
api.PutShapeSaveAs(request3);
Stream file3 = api.DownloadFile(new DownloadFileRequest { Path = outPath3 });
file3.CopyTo(File.Create("myPresentation-slide2-shape3.png"));
```

#### **HTTP DELETE**
Not Supported.


#### **cURL Example**
{{% alert color="primary" %}} 

This request returns the slide in the response with the desired export format. You can use the **--output** flag for **cURL** to write response data to a file

{{% /alert %}} 

**Create Authentication Headers** 
```java
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Save first slide of the presenatation as pdf document**
```java
curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/pdf" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer []Access Token" --ssl-no-revoke --output test_export_pdf.pdf
```

**Save first slide of the presenatation to Storage as pdf document**
```java
curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/pdf?outPath=myFile.pdf" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer [Access Token]
```


## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="5" tabID="7" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "DownloadSlide.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "DownloadSlide.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
<?php 
    // For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

    include(dirname(__DIR__) . '\CommonUtils.php');
    use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
    use Aspose\Slides\Cloud\Sdk\Api\Configuration;
    use Aspose\Slides\Cloud\Sdk\Model;
    use Aspose\Slides\Cloud\Sdk\Model\Requests;

    try {
        // Create SlidesApi instance
        $config = new Configuration();
        $config->setAppSid(CommonUtils::$AppSid);
        $config->setAppKey(CommonUtils::$AppKey);
        $slidesApi = new SlidesApi(null, $config);

        $fileName = "test-unprotected.ppt";
        $index = 1;

        // Upload original document to storage
        $fileStream = fopen(realpath(__DIR__ . '/../..') . '\resources\\' . $fileName, 'r');
        $slidesApi->uploadFile($fileName,  $fileStream, CommonUtils::$MyStorage);
        
        $request = new Requests\PostSlideSaveAsRequest($fileName, $index, Model\SlideExportFormat::PDF);
        $result = $slidesApi->postSlideSaveAs($request);
        print_r($result);

    } catch (Exception $e) {
        echo "Something went wrong: ", $e->getMessage(), "\n";
    }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "DownloadSlide.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "DownloadSlide.java" >}}

{{< /tab >}}

{{< /tabs >}}
### **SDK Source**
The Aspose  Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)


