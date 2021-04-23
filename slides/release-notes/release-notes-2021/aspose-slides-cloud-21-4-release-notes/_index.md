---
title: "Aspose.Slides Cloud 21.3 Release Notes"
type: docs
url: /aspose-slides-cloud-21-3-release-notes/
weight: 60
---

## **Important Changes and Enhancements**
- **SLIDESCLOUD-1124** Method to add signatures to presentations
- **SLIDESCLOUD-1140** Unify protectionProperties, lock & unlock resources

## **Other Improvements and Changes**
- **SLIDESCLOUD-1155** Uploading file throws ApiException with default arguments

## **Public API changes**
### **Add/remove watermarks**
A new **watermark** resource allow to add and delete watermarks in presentations. You can specify watermark parameters using query string, JSON or image file.
#### **Example 1 - add a text watermark to a presentation**

```
POST https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/watermark?text=this%20%is%20%a%20%watermark&fontHeight=18
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.CreateWatermark("MyPresentation.pptx", text: "this is a watermark", fontHeight: 18);
```

#### **Example 2 - add a text watermark to a presentation from request body using JSON DTO**

```
POST https://api.aspose.cloud/v3.0/slides/watermark
```

***Request body:***

Presentation file and the following JSON:
```json
{
  "text": "this is a watermark",
  "x": "10",
  "y": "10",
  "width": "500",
  "height": "200"
}
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream inputFile = File.OpenRead("MyPresentation.pptx");
Shape watermark = new Shape
{
    Text = "this is a watermark",
    X = 10,
    Y = 10,
    Width = 500,
    Height = 200
};
Stream outputFile = api.CreateWatermarkOnline(document, watermark);
outputFile.CopyTo(File.Create("MyPresentationWithWatermark.pptx"));
```

#### **Example 3 - create an image watermark for a presentation**

```
POST https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/watermark/image
```

***Request body:***

Image file

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream watermarkFile = File.OpenRead("watermark.png");
api.CreateImageWatermark("MyPresentation.pptx", watermarkFile);
```

#### **Example 4 - create an image watermark for a presentation from request body using JSON DTO**

```
POST https://api.aspose.cloud/v3.0/slides/watermark/image
```

***Request body:***

Presentation file and the following JSON:
```json
{
    "type": "PictureFrame",
    "fillFormat": {
        "type": "Picture",
        "base64Data": "<Base64 image data>"
    }
}
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream inputFile = File.OpenRead("MyPresentation.pptx");
string base64Data = Convert.ToBase64String(File.ReadAllBytes("watermark.png"));
PictureFrame pictureFrame = new PictureFrame { FillFormat = new PictureFill { Base64Data = base64Data } };
Stream outputFile = api.CreateImageWatermarkOnline(inputFile, pictureFrame: pictureFrame);
outputFile.CopyTo(File.Create("MyPresentationWithWatermark.pptx"));
```

#### **Example 5 - delete watermarks from a presentation**

```
DELETE https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/watermark
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream outputFile = api.DeleteWatermark("MyPresentation.pptx");
```

#### **Example 6 - delete watermarks in a presentation from request body**
Watermarks are identified as shapes with name "custom_watermark" in this example (the default value is "watermark").

```
POST https://api.aspose.cloud/v3.0/slides/watermark/delete?shapeName=custom_watermark
```

***Request body:***

Presentation file

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream inputFile = File.OpenRead("MyPresentationWithWatermarks.pptx");
Stream outputFile = api.DeleteWatermarkOnline(inputFile, shapeName: "custom_watermark");
outputFile.CopyTo(File.Create("MyPresentation.pptx"));
```

### **Lock/unlock presentations**
A new **protection** resource allows to get, set or delete protection from a presentation.
#### **Example 1 - Protect a presentation with a password**

```
POST https://api.aspose.cloud/v3.0/slides/protection
```

***Request body:***

Presentation file and the following JSON:
```json
{ "readPassword": "newPassword" }
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream document = File.OpenRead("MyPresentation.pptx");
ProtectionProperties dto = new ProtectionProperties { ReadPassword = "newPassword" };
Stream outputDocument = api.SetProtectionOnline(document, dto);
outputDocument.CopyTo(File.Create("MyProtectedPresentation.pptx"));
```

#### **Example 2 - Remove password from a presentation on storage**
Removes read/write passwords, ReadOnlyRecommended & EncryptDocumentProperties flags.

```
DELETE https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/protection
```

***Request header:***

password: oldPassword

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
ProtectionProperties protectionProperties = api.DeleteProtection("MyPresentation.pptx", "oldPassword");
Console.WriteLine(protectionProperties.IsEncrypted); //false
```

#### **Example 3 - Remove password from a presentation in request body**

```
POST https://api.aspose.cloud/v3.0/slides/protection/delete
```

***Request header:***

password: oldPassword

***Request body:***

Presentation file

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream inputFile = File.OpenRead("MyProtectedPresentation.pptx");
Stream outputFile = api.DeleteProtectionOnline(inputFile, "oldPassword");
outputFile.CopyTo(File.Create("MyPresentation.pptx"));
```

### **Removed Methods**

**PUT fromHtml** method has been deleted. Use **POST fromHtml** method for both creating presentations and adding slides to it.

**slideSize** resource has been deleted. Use **slideProperties** resource instead.

### **Deprecated Methods**

SDK methods no longer use Request parameters. Also, many method names are changed.
The old method declarations are deprecated and will be removed in 21.6 release.
For a list of renamed methods, see [21.3 release notes](/slides/aspose-slides-cloud-21-3-release-notes).