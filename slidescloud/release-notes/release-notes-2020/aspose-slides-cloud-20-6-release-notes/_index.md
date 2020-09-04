---
title: "Aspose.Slides Cloud 20.6 Release Notes"
type: docs
url: /aspose-slides-cloud-20-6-release-notes/
weight: 20
---

{{% alert color="primary" %}} 

The page contains release notes for Aspose.Slides Cloud 20.6 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}} 
## **New features and enhancements**
- SLIDESCLOUD-952 - Add method to check that NotesSilde exists
- SLIDESCLOUD-944 - Create separate endpoints for shape resources with empty subshape paths
- SLIDESCLOUD-938 - Support Fodp save & load format
## **Other improvements and changes**
- SLIDESCLOUD-941 - Support PDF/A-1a and PDF/UA options for PdfCompliance enumeration
- SLIDESCLOUD-935 - PdfOptions.AccessPermissions option
- SLIDESCLOUD-953 - PutPresentationMerge API throws System.OutOfMemory Exception
## **Public API changes**
### **1. notesSlide/exist resource**
The new method (GET for storage files, POST for files in the request body) returns information about whether notes exist for a slide.
#### **Example 1 (storage file)**


```java

GET https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/notesSlide/exist?folder=myFolder

```

**SDK Code:**

```java

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");

GetNotesSlideExistsRequest request = new GetNotesSlideExistsRequest

{

    Name = "myPresentaion.pptx",

    Folder = "myFolder",

    SlideIndex = 1

code

EntityExists exists = api.GetNotesSlideExists(request);

Console.WriteLine(exists.Exists);

```


#### **Example 2 (no storage)**
```java

POST https://api.aspose.cloud/v3.0/slides/slides/1/notesSlide/exist

```

***Request body:***

Contains the presentation.

***SDK Code:***

```java

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");

PostGetNotesSlideExistsRequest request = new PostGetNotesSlideExistsRequest

{

    Document = File.OpenRead("myPresentaion.pptx"),

    SlideIndex = 1

};

EntityExists exists = api.PostGetNotesSlideExists(request);

Console.WriteLine(exists.Exists);

```
### **2. Methods for handling subshapes**
SDK Request classes related to shapes have no more Path property. You can no longer access subshapes (i.e. shapes inside a grouped shape or a SmartArt figure) using those classes. The affected classes are:

GetSlideShapeRequest, GetSlideShapesRequest, GetSlideShapeParagraphRequest, GetSlideShapeParagraphsRequest, GetParagraphPortionRequest, GetParagraphPortionsRequest, GetNotesSlideShapeRequest, GetNotesSlideShapesRequest, GetNotesSlideShapeParagraphRequest, GetNotesSlideShapeParagraphsRequest, GetNotesSlideShapePortionRequest, GetNotesSlideShapePortionsRequest, PostAddNewShapeRequest, PostAddNewParagraphRequest, PostAddNewPortionRequest, PostNotesSlideAddNewShapeRequest, PostNotesSlideAddNewParagraphRequest, PostNotesSlideAddNewPortionRequest, PutSlideShapeInfoRequest, PutSetParagraphPropertiesRequest, PutSetParagraphPortionPropertiesRequest, PutUpdateNotesSlideShapeRequest, PutUpdateNotesSlideShapeParagraphRequest, PutUpdateNotesSlideShapePortionRequestDeleteSlideShapeRequest, DeleteSlideShapesRequest, DeleteParagraphRequest, DeleteParagraphsRequest, DeletePortionRequest, DeletePortionsRequest, DeleteNotesSlideShapeRequest, DeleteNotesSlideShapesRequest, DeleteNotesSlideParagraphRequest, DeleteNotesSlideParagraphsRequest, DeleteNotesSlidePortionRequest, DeleteNotesSlidePortionsRequest, PostShapeSaveAsRequest, PostNotesSlideShapeSaveAsRequest, PutShapeSaveAsRequest, PutNotesSlideShapeSaveAsRequest.

To work with subshapes, use new SDK methods with a mandatory Path request property:

GetSlideSubshape, GetSlideSubshapes, GetSlideSubshapeParagraph, GetSlideSubshapeParagraphs, GetSubshapeParagraphPortion, GetSubshapeParagraphPortions, PostAddNewSubshape, PostAddNewSubshapeParagraph, PostAddNewSubshapePortion, PutSlideSubshapeInfo, PutSetSubshapeParagraphProperties, PutSetSubshapeParagraphPortionProperties, DeleteSlideSubshape, DeleteSlideSubshapes, DeleteSubshapeParagraph, DeleteSubshapeParagraphs, DeleteSubshapePortion, DeleteSubshapePortions, PostSubshapeSaveAs, PutSubshapeSaveAs.
#### **Example (Download a shape that is part of a shape group)**
CURL request remains unchanged:



```java

POST https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/4/shapes/1/png?folder=myFolder

```



**SDK Code:**

```java

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");

PostSubshapeSaveAsRequest request = new PostSubshapeSaveAsRequest

{

    Name = "myPresentaion.pptx",

    Folder = "myFolder",

    SlideIndex = 1,

    Path = "4/shapes",

    ShapeIndex = 1,

    Format = ShapeExportFormat.Png

};

Stream file = TestUtils.SlidesApi.PostSubshapeSaveAs(request);

file.CopyTo(File.Create("subshape.png"));

```
### **3. FODP export format**
You can export presentations and slide to FODP.
#### **Usage example (Download a shape that is part of a shape group)**
```java

POST https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/fodp?folder=myFolder

```

***SDK Code:***

```java

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");

PostSlidesSaveAsRequest request = new PostSlidesSaveAsRequest

{

    Name = "myPresentation.pptx",

    Format = ExportFormat.Fodp

};

Stream response = api.PostSlidesSaveAs(request);

response.CopyTo(File.Create("myPresentation.fodp"));

```
### **4. PdfExportOptions.AccessPermissions property**
A new **AccessPermissions** property has been added to **PdfExportOptions** class. It specifies access permissions that should be granted when the document is opened with user access.
### **5. New PdfCompliance options**
New **PdfA1a** and **PdfUa** options have been added to **ComplianceEnum** enumeration. It is used in the **Compliance** property of the **PdfExportOptions** class.
