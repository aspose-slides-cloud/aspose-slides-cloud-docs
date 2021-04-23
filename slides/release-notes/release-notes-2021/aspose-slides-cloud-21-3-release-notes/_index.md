---
title: "Aspose.Slides Cloud 21.3 Release Notes"
type: docs
url: /aspose-slides-cloud-21-3-release-notes/
weight: 60
---

## **Important Changes and Enhancements**
- **SLIDESCLOUD-943** Support shape alignment
- **SLIDESCLOUD-1116** Merge presentations without uploading to the storage
- **SLIDESCLOUD-1117** Split presentations without uploading to the storage
- **SLIDESCLOUD-1118** Export slides without using the storage
- **SLIDESCLOUD-1119** Export shapes without using the storage
- **SLIDESCLOUD-1120** Find & replace text in a presentation from request body
- **SLIDESCLOUD-1127** Method to extract all images from a presentation
- **SLIDESCLOUD-1128** Download images from presentation in request body

## **Other Improvements and Changes**
- **SLIDESCLOUD-1103** Simplify SDK method declarations
- **SLIDESCLOUD-1139** Packages conflict Aspose.Slides.Cloud.Sdk with Microsoft.Extensions.Logging.Debug in .NET Core Framework

## **Public API changes**
### **Merge presentations without uploading to storage**
A new **merge** POST & PUT methods allow to merge presentations from a multipart request body. You can optionally provide a JSON to specify merge details (like slides to merge). You can also merge presentations provided in request body with ones that exist on the storage.
#### **Example 1 - merge presentations**

```
POST https://api.aspose.cloud/v3.0/slides/merge
```

***Request body:***

Files to merge.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
FileInfo file1 = new FileInfo { Content = File.OpenRead("file1.pptx") };
FileInfo file2 = new FileInfo { Content = File.OpenRead("file2.pptx") };
Stream result = api.MergeOnline(new List<FileInfo> { file1, file2 });
result.CopyTo(File.Create("merged.pptx"));
```

#### **Example 2 - merge presentations and save the result to the storage**

```
PUT https://api.aspose.cloud/v3.0/slides/merge?outPath=OutputFolder/merged.pptx
```

***Request body:***

Files to merge.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
FileInfo file1 = new FileInfo { Content = File.OpenRead("file1.pptx") };
FileInfo file2 = new FileInfo { Content = File.OpenRead("file2.pptx") };
api.MergeAndSaveOnline("OutputFolder/merged.pptx", new List<FileInfo> { file1, file2 });
```

#### **Example 3 - merge a presentation with the second and third slides of another presentation**

```
POST https://api.aspose.cloud/v3.0/slides/merge
```

***Request body:***

Files to merge and the following JSON:
```json
{ "presentations": [{ "slides": [1, 2] }]}
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
FileInfo file1 = new FileInfo { Content = File.OpenRead("file1.pptx") };
FileInfo file2 = new FileInfo { Content = File.OpenRead("file2.pptx") };
OrderedMergeRequest request = new OrderedMergeRequest
{
    Presentations = new List<PresentationToMerge> { new PresentationToMerge { Slides = new List<int?> { 1, 2 } } }
};
Stream result = api.MergeOnline(new List<FileInfo> { file1, file2 }, request);
result.CopyTo(File.Create("merged.pptx"));
```

#### **Example 4 - merge a presentation in the request body with a presentation on the storage**

```
POST https://api.aspose.cloud/v3.0/slides/merge
```

***Request body:***

File to merge and the following JSON:
```json
{ "presentations": [{ "source": "Storage", "path": "myfolder/myfile.pptx" }]}
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
FileInfo file1 = new FileInfo { Content = File.OpenRead("file1.pptx") };
FileInfo file2 = new FileInfo { Content = File.OpenRead("file2.pptx") };
OrderedMergeRequest request = new OrderedMergeRequest
{
    Presentations = new List<PresentationToMerge>
    {
        new PresentationToMerge { Source = PresentationToMerge.SourceEnum.Storage, Path = "myfolder/myfile.pptx" }
    }
};
Stream result = api.MergeOnline(new List<FileInfo> { file1, file2 }, request);
result.CopyTo(File.Create("merged.pptx"));
```

### **Split presentation from request body**
A new **split** POST & PUT methods method allow to split (slide by slide) a presentation in request body, without uploading it to the storage. You can either save the result to the storage or download it as a ZIP archive.
#### **Example 1 - Split a presentation to PDF files**

```
POST https://api.aspose.cloud/v3.0/slides/split/pdf
```

***Request body:***

File to split.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream result = api.SplitOnline(File.OpenRead("inputFile.pptx"), SlideExportFormat.Pdf);
using (ZipArchive zip = new ZipArchive(result))
{
    foreach (ZipArchiveEntry entry in zip.Entries.Count)
    {
        Console.WtireLine(entry.FullName);
    }
}
```

#### **Example 2 - Split a presentation to PDF files and save the result to the storage**

```
PUT https://api.aspose.cloud/v3.0/slides/split/pdf?destFolder=OutputFolder
```

***Request body:***

File to split.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.SplitAndSaveOnline(File.OpenRead("inputFile.pptx"), SlideExportFormat.Pdf, "OutputFolder");
```

### **Download slides and shapes from a presentation in request body**
New POST & PUT methods method allow to download slides, shapes and images from a presentation in request body, without uploading it to the storage. You can either download or save the result to the storage.
#### **Example 1 - Convert the second slide of a presentation to SVG**

```
POST https://api.aspose.cloud/v3.0/slides/slides/2/svg
```

***Request body:***

Input file.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream converted = api.DownloadSlideOnline(File.OpenRead("inputFile.pptx"), 2, SlideExportFormat.Svg);
converted.CopyTo(File.Create("slide2.svg"));
```

#### **Example 2 - Convert the third shape of the first slide of a presentation to PNG**

```
POST https://api.aspose.cloud/v3.0/slides/slides/1/shapes/3/png
```

***Request body:***

Input file.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream converted = api.DownloadShapeOnline(File.OpenRead("inputFile.pptx"), 1, 3, SlideExportFormat.Png);
converted.CopyTo(File.Create("shape1-3.png"));
```

#### **Example 3 - Convert the third shape of the first slide of a presentation to PNG and save it to the storage**

```
PUT https://api.aspose.cloud/v3.0/slides/slides/1/shapes/3/png?outPath=OutputFolder/shape1-3.png
```

***Request body:***

Input file.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.SaveShapeOnline(File.OpenRead("inputFile.pptx"), 1, 3, SlideExportFormat.Png, "OutputFolder/shape1-3.png");
```

#### **Example 4 - Get the third image of the presentation in PNG format**

```
POST https://api.aspose.cloud/v3.0/slides/images/3/png
```

***Request body:***

Input file.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream image = api.DownloadImageOnline(File.OpenRead("inputFile.pptx"), 3, SlideExportFormat.Png);
image.CopyTo(File.Create("image.png"));
```

### **Replace text in a presentation from request body**
New **replaceText** POST method works just the same as the existing one, but does not require uploading the presentation to the storage. It takes the file from request body and returns the modidied version in the response.
#### **Example 1 - Replace all occurences of 'old' to 'new'**

```
POST https://api.aspose.cloud/v3.0/slides/replaceText?oldValue=old&newValue=new
```

***Request body:***

Input file.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream replaced = api.ReplacePresentationTextOnline(File.OpenRead("inputFile.pptx"), "old", "new");
replaced.CopyTo(File.Create("outputFile.pptx"));
```

#### **Example 2 - Replace all occurences of 'old' to 'new' in the second slide ignoring character case**

```
POST https://api.aspose.cloud/v3.0/slides/slides/2/replaceText?oldValue=old&newValue=new&ignoreCase=true
```

***Request body:***

Input file.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream replaced = api.ReplaceSlideTextOnline(File.OpenRead("inputFile.pptx"), 2, "old", "new", true);
replaced.CopyTo(File.Create("outputFile.pptx"));
```

### **Download presentation images**
New **download** POST methods allow to get all images of a presentation as a ZIP archive in one request. The feature can be used both with storage files and files provided in request body.
#### **Example 1 - Download all images of a presentation**

```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/images/download?folder=myFolder
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream images = api.DownloadImagesDefaultFormat("myPresentation.pptx", folder: "myFolder");
using (ZipArchive zip = new ZipArchive(images))
{
    foreach (ZipArchiveEntry entry in zip.Entries.Count)
    {
        Console.WtireLine(entry.FullName);
    }
}
```

#### **Example 2 - Download all images of a presentation in PNG format**

```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/images/download/png?folder=myFolder
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream images = api.DownloadImages("myPresentation.pptx", ImageExportFormat.Png, folder: "myFolder");
using (ZipArchive zip = new ZipArchive(images))
{
    foreach (ZipArchiveEntry entry in zip.Entries.Count)
    {
        Console.WtireLine(entry.FullName);
    }
}
```

#### **Example 3 - Download all images of a presentation provided in request body in PNG format**

```
POST https://api.aspose.cloud/v3.0/slides/images/download/png?folder=myFolder
```

***Request body:***

Input file.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream images = api.DownloadImagesOnline(File.OpenRead("inputFile.pptx"), ImageExportFormat.Png);
using (ZipArchive zip = new ZipArchive(images))
{
    foreach (ZipArchiveEntry entry in zip.Entries.Count)
    {
        Console.WtireLine(entry.FullName);
    }
}
```

### **Shape alignment**
New **align** POST method allows to align shapes in a slide.
#### **Example 1 - Align all shapes in a slide to the top-most shape**

```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/shapes/align/top?folder=myFolder
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.AlignShapes("myPresentation.pptx", 1, ShapesAlignmentType.AlignTop, folder: "myFolder");
```

#### **Example 2 - Align shapes 3-5 in a slide to the left edge of the slide**

```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/shapes/align/left?folder=myFolder&alignToSlide=true&shapes=3,4,5
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.AlignShapes("myPresentation.pptx", 1, ShapesAlignmentType.AlignLeft, true, new List<int> { 3, 4, 5 }, folder: "myFolder");
```

### **Simplified method declarations**
SDK methods no longer use Request parameters. Also, many method names are changed.
The old method declarations are deprecated and will be removed in 21.6 release.

|**Old (<21.3) Method Name**|**New (21.3) Method Name**|
| :- | :- |
|DeleteSlideAnimation|DeleteAnimation|
|DeleteSlideAnimationEffect|DeleteAnimationEffect|
|DeleteSlideAnimationInteractiveSequence|DeleteAnimationInteractiveSequence|
|DeleteSlideAnimationInteractiveSequenceEffect|DeleteAnimationInteractiveSequenceEffect|
|DeleteSlideAnimationInteractiveSequences|DeleteAnimationInteractiveSequences|
|DeleteSlideAnimationMainSequence|DeleteAnimationMainSequence|
|DeleteSlideByIndex|DeleteSlide|
|DeleteSlideShape|DeleteShape|
|DeleteSlideShapes|DeleteShapes|
|DeleteSlideSubshape|DeleteSubshape|
|DeleteSlideSubshapes|DeleteSubshapes|
|DeleteSlidesCleanSlidesList|DeleteSlides|
|DeleteSlidesDocumentProperties|DeleteDocumentProperties|
|DeleteSlidesDocumentProperty|DeleteDocumentProperty|
|DeleteSlidesSlideBackground|DeleteBackground|
|GetLayoutSlidesList|GetLayoutSlides|
|GetMasterSlidesList|GetMasterSlides|
|GetNotesSlideExists|NotesSlideExists|
|GetNotesSlideShapeParagraph|GetNotesSlideParagraph|
|GetNotesSlideShapeParagraphs|GetNotesSlideParagraphs|
|GetNotesSlideShapePortion|GetNotesSlidePortion|
|GetNotesSlideShapePortions|GetNotesSlidePortions|
|GetNotesSlideWithFormat|DownloadNotesSlide|
|GetParagraphPortion|GetPortion|
|GetParagraphPortions|GetPortions|
|GetSlideAnimation|GetAnimation|
|GetSlideShape|GetShape|
|GetSlideShapeParagraph|GetParagraph|
|GetSlideShapeParagraphs|GetParagraphs|
|GetSlideShapes|GetShapes|
|GetSlideSubshape|GetSubshape|
|GetSlideSubshapeParagraph|GetSubshapeParagraph|
|GetSlideSubshapeParagraphs|GetSubshapeParagraphs|
|GetSlideSubshapes|GetSubshapes|
|GetSlidesApiInfo|GetApiInfo|
|GetSlidesDocument|GetPresentation|
|GetSlidesDocumentProperties|GetDocumentProperties|
|GetSlidesDocumentProperty|GetDocumentProperty|
|GetSlidesImageWithDefaultFormat|DownloadImageDefaultFormat|
|GetSlidesImageWithFormat|DownloadImage|
|GetSlidesImages|GetPresentationImages|
|GetSlidesPlaceholder|GetPlaceholder|
|GetSlidesPlaceholders|GetPlaceholders|
|GetSlidesPresentationTextItems|GetPresentationTextItems|
|GetSlidesProtectionProperties|GetProtectionProperties|
|GetSlidesSlide|GetSlide|
|GetSlidesSlideBackground|GetBackground|
|GetSlidesSlideComments|GetComments|
|GetSlidesSlideImages|GetSlideImages|
|GetSlidesSlideProperties|GetSlideProperties|
|GetSlidesSlideTextItems|GetSlideTextItems|
|GetSlidesSlidesList|GetSlides|
|GetSlidesTheme|GetTheme|
|GetSlidesThemeColorScheme|GetColorScheme|
|GetSlidesThemeFontScheme|GetFontScheme|
|GetSlidesThemeFormatScheme|GetFormatScheme|
|GetSlidesViewProperties|GetViewProperties|
|GetSubshapeParagraphPortion|GetSubshapePortion|
|GetSubshapeParagraphPortions|GetSubshapePortions|
|PostAddNewParagraph|CreateParagraph|
|PostAddNewPortion|CreatePortion|
|PostAddNewShape|CreateShape|
|PostAddNewSubshape|CreateSubshape|
|PostAddNewSubshapeParagraph|CreateSubshapeParagraph|
|PostAddNewSubshapePortion|CreateSubshapePortion|
|PostAddNotesSlide|CreateNotesSlide|
|PostChartCategory|CreateChartCategory|
|PostChartDataPoint|CreateChartDataPoint|
|PostChartSeries|CreateChartSeries|
|PostCopyLayoutSlideFromSourcePresentation|CopyLayoutSlide|
|PostCopyMasterSlideFromSourcePresentation|CopyMasterSlide|
|PostExportImagesWithDefaultFormat|DownloadImagesDefaultFormat|
|PostExportImagesWithFormat|DownloadImages|
|PostGetNotesSlide|GetNotesSlideOnline|
|PostGetNotesSlideExists|NotesSlideExistsOnline|
|PostGetNotesSlideWithFormat|DownloadNotesSlideOnline|
|PostNotesSlideAddNewParagraph|CreateNotesSlideParagraph|
|PostNotesSlideAddNewPortion|CreateNotesSlidePortion|
|PostNotesSlideAddNewShape|CreateNotesSlideShape|
|PostNotesSlideShapeSaveAs|DownloadNotesSlideShape|
|PostPresentationMerge|Merge|
|PostSection|CreateSection|
|PostSectionMove|MoveSection|
|PostShapeSaveAs|DownloadShape|
|PostSlideAnimationEffect|CreateAnimationEffect|
|PostSlideAnimationInteractiveSequence|CreateAnimationInteractiveSequence|
|PostSlideAnimationInteractiveSequenceEffect|CreateAnimationInteractiveSequenceEffect|
|PostSlideSaveAs|DownloadSlide|
|PostSlidesAdd|CreateSlide|
|PostSlidesConvert|Convert|
|PostSlidesCopy|CopySlide|
|PostSlidesDocument|CreatePresentation|
|PostSlidesDocumentFromHtml|ImportFromHtml|
|PostSlidesDocumentFromPdf|ImportFromPdf|
|PostSlidesDocumentFromSource|CreatePresentationFromSource|
|PostSlidesDocumentFromTemplate|CreatePresentationFromTemplate|
|PostSlidesPipeline|Pipeline|
|PostSlidesPresentationReplaceText|ReplacePresentationText|
|PostSlidesReorder|MoveSlide|
|PostSlidesReorderMany|ReorderSlides|
|PostSlidesSaveAs|DownloadPresentation|
|PostSlidesSetDocumentProperties|SetDocumentProperties|
|PostSlidesSlideReplaceText|ReplaceSlideText|
|PostSlidesSplit|Split|
|PostSubshapeSaveAs|DownloadSubshape|
|PutChartCategory|UpdateChartCategory|
|PutChartDataPoint|UpdateChartDataPoint|
|PutChartSeries|UpdateChartSeries|
|PutLayoutSlide|UpdateLayoutSlide|
|PutNotesSlideHeaderFooter|SetNotesSlideHeaderFooter|
|PutNotesSlideShapeSaveAs|SaveNotesSlideShape|
|PutPresentationMerge|OrderedMerge|
|PutSection|UpdateSection|
|PutSections|SetSections|
|PutSetParagraphPortionProperties|UpdatePortion|
|PutSetParagraphProperties|UpdateParagraph|
|PutSetSubshapeParagraphPortionProperties|UpdateSubshapePortion|
|PutSetSubshapeParagraphProperties|UpdateSubshapeParagraph|
|PutShapeSaveAs|SaveShape|
|PutSlideAnimation|SetAnimation|
|PutSlideAnimationEffect|UpdateAnimationEffect|
|PutSlideAnimationInteractiveSequenceEffect|UpdateAnimationInteractiveSequenceEffect|
|PutSlideHeaderFooter|SetSlideHeaderFooter|
|PutSlideSaveAs|SaveSlide|
|PutSlideShapeInfo|UpdateShape|
|PutSlideSubshapeInfo|UpdateSubshape|
|PutSlidesConvert|ConvertAndSave|
|PutSlidesHeaderFooter|SetPresentationHeaderFooter|
|PutSlidesProtectionProperties|SetProtectionProperties|
|PutSlidesSaveAs|SavePresentation|
|PutSlidesSetDocumentProperty|SetDocumentProperty|
|PutSlidesSlide|UpdateSlide|
|PutSlidesSlideBackground|SetBackground|
|PutSlidesSlideBackgroundColor|SetBackgroundColor|
|PutSlidesSlideProperties|SetSlideProperties|
|PutSlidesViewProperties|SetViewProperties|
|PutSubshapeSaveAs|SaveSubshape|
|PutUpdateNotesSlide|UpdateNotesSlide|
|PutUpdateNotesSlideShape|UpdateNotesSlideShape|
|PutUpdateNotesSlideShapeParagraph|UpdateNotesSlideParagraph|
|PutUpdateNotesSlideShapePortion|UpdateNotesSlidePortion|

### **Deprecated Methods**
**PUT fromHtml** method is deprecated and will be deleted in 21.4 release. Use **POST fromHtml** method for both creating presentations and adding slides to it.

**slideSize** resource is deprecated and will be deleted in 21.4 release. Use **slideProperties** resource instead.
