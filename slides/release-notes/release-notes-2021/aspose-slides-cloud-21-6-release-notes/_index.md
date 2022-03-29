---
title: "Aspose.Slides Cloud 21.6 Release Notes"
type: docs
url: /aspose-slides-cloud-21-6-release-notes/
weight: 70
---

## **Important Changes and Enhancements**
- **SLIDESCLOUD-1125** Methods to add & remove comments

## **Other Improvements and Changes**
- **SLIDESCLOUD-1210** PostSlidesConvert method doesn't allow getting result through API Reference
- **SLIDESCLOUD-1208** How to get consumed credits and data in Docker Container

## **Public API changes**
### **Add/remove comments**
POST & DELETE methods for **comments** resource allow to add and delete comments to/from presentations.

#### **Example 1 - add a comment to a presentation using the storage**

```
POST https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/comments
```

***Request body:***

```json
{
  "author": "John Doe",
  "text": "Here is my comment"
}
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
SlideComment comment = new SlideComment { Author = "John Doe", Text = "Here is my comment" };
api.CreateComment("MyPresentation.pptx", 2, comment);
```


#### **Example 2 - add a comment to a presentation not using the storage**

```
POST https://api.aspose.cloud/v3.0/slides/slides/2/comments
```

***Request body:***

Presentation file and comment JSON:

```json
{
  "author": "John Doe",
  "text": "Here is my comment"
}
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream inputFile = File.OpenRead("MyPresentation.pptx");
SlideComment comment = new SlideComment { Author = "John Doe", Text = "Here is my comment" };
Stream outputFile = api.CreateCommentOnline(inputFile, 2, comment);
outputFile.CopyTo(File.Create("MyPresentationWithNewComment.pptx"));
```

#### **Example 3 - Delete all comments from a presentation on the storage**

```
DELETE https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/comments
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.DeleteComments("MyPresentation.pptx");
```

#### **Example 4 - Delete all comments by a specific author from a presentation in request body**

```
POST https://api.aspose.cloud/v3.0/slides/comments/delete?author=John%20Doe
```

***Request body:***

Presentation file.

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream inputFile = File.OpenRead("MyPresentation.pptx");
Stream outputFile = api.DeleteCommentsOnline(inputFile, "John Doe");
outputFile.CopyTo(File.Create("MyPresentationWithNoComments.pptx"));
```

#### **Example 5 - delete comments from a specific slide & author in a presentation on the storage**

```
DELETE https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/comments?author=John%20Doe
```

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
api.DeleteSlideComments("MyPresentation.pptx", 2, "John Doe");
```

#### **Example 6 - delete all comments from a specific slide in a presentation from request body**

```
POST https://api.aspose.cloud/v3.0/slides/slides/2/comments/delete
```

***Request body:***

Presentation file

**SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream inputFile = File.OpenRead("MyPresentationWithWatermarks.pptx");
Stream outputFile = api.DeleteSlideCommentsOnline(inputFile, 2);
outputFile.CopyTo(File.Create("MyPresentationWithNoCommentsOnSlide2.pptx"));
```

### **Removed Duplicate Resources**

**GET {name}/{format}** method is removed. Instead, use **POST {name}/{format}** method to retrive presentations in a specific format instead.

**GET {name}/slides/{slideIndex}/{format}** method is removed. Instead, use **POST {name}/slides/{slideIndex}/{format}** method to retrieve slides in a specific format instead.

**GET {name}/slides/{slideIndex}/shapes/{shapeIndex}/{format}** method is removed. Instead, use **POST {name}/slides/{slideIndex}/shapes/{shapeIndex}/{format}** method to retrieve shapes in a specific format.

### **Removed SDK Methods**

SDK methods no longer use Request parameters. Also, many method names are changed.
The old method declarations, as well as Request classes, have been deleted.
For a list of renamed methods, see [21.3 release notes](/slides/aspose-slides-cloud-21-3-release-notes).