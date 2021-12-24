---
title: "Aspose.Slides Cloud 21.1 Release Notes"
type: docs
url: /aspose-slides-cloud-21-1-release-notes/
weight: 10
---

## **Important Changes and Enhancements**
- **SLIDESCLOUD-1066** Enable PDF Import
- **SLIDESCLOUD-939** Support ProtectionManager properties
- **SLIDESCLOUD-1073** Remove password field from request query string

## **Other Improvements and Changes**
- **SLIDESCLOUD-1026** NullReferenceException is thrown when not all shape properties are provided
- **SLIDESCLOUD-1036** Export to SVG with VectorizeText option fails in linux image

## **Public API changes**
### **PDF Import**
The new **fromPdf** POST method allows to create presentations or append slides to existing ones using PDF files.
#### **Example**

```
POST https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/fromPdf?folder=myFolder
```

***Request body:***

Contains the PDF document.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream file = File.OpenRead("input.pdf");
PostSlidesDocumentFromPdfRequest request = new PostSlidesDocumentFromPdfRequest { Name = "Sales.pptx", Pdf = file };
Document response = api.PostSlidesDocumentFromPdf(request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/Sales.pptx
```

### **SlideProperties and ProtectionProperties**
The new **slideProperties** and **protectionProperties** allow to get and set a number of presentation-level properties like slide size, orientation, read-only etc.
#### **Example 1 (get slide properties)**

```
GET https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slideProperties?folder=myFolder
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
GetSlidesSlidePropertiesRequest request = new GetSlidesSlidePropertiesRequest { Name = "myPresentation.pptx" };
SlideProperties slideProperties = api.GetSlidesSlideProperties(request);
Console.WriteLine(response.FirstSlideNumber);
Console.WriteLine(response.Orientation);
```

#### **Example 2 (set custom slide size)**

```
PUT https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slideProperties?folder=myFolder
```

***Request body:***

```
{ "width": 900, "height": 600 }
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
PutSlidesSlidePropertiesRequest request = new PutSlidesSlidePropertiesRequest
{
    Name = "myPresentation.pptx",
    Dto = new SlideProperties { Width = 900, Height = 600 }
};
SlideProperties response = api.PutSlidesSlideProperties(request);
Console.WriteLine(response.Width);
Console.WriteLine(response.Height);
```

### **Password Field Moved to Header**
Password fields (**password**, **sourcePassword**, **templatePassword** etc.) used with protected presentations should now be supplied in the request header instead of query string.

Nothing is changed in the API if you use SDK.

### **Deprecated Methods**
**PUT fromHtml** method is deprecated and will be deleted in 21.4 release. Use **POST fromHtml** method for both creating presentations and adding slides to it.

**slideSize** resource is deprecated and will be deleted in 21.4 release. Use **slideProperties** resource instead.
