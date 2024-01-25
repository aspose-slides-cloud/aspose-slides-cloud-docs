---
title: "Convert Shapes to Images"
type: docs
url: /convert-shapes-to-images/
weight: 200
---

## **Introduction**

Aspose.Slides Cloud API enables the export of shapes from PowerPoint documents into images. This feature has become a key tool for those looking to share their presentations in a more accessible format, such as in online publications, blogs, or social media.

Using the methods below, you can convert your shapes into popular image formats such as JPEG, PNG, SVG, and others without losing quality and detail. Additionally, you have the ability to choose the scale of the images.

## **DownloadShape**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/{format}|POST|Converts a shape to an image and returns the result.|[DownloadShape](https://reference.aspose.cloud/slides/#/Shapes/DownloadShape)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the presentation saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of the slide on which the shape is placed.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|format|`ShapeExportFormat`|path|true|The format of the output image.|
|options|???|body|false|The options for the output image.|
