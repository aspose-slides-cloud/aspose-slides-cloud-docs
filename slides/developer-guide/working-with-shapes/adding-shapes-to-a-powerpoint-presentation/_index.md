---
title: "Adding-Shapes-to-a-PowerPoint-Presentation"
type: docs
url: /adding-shapes-to-a-powerpoint-presentation/
weight: 25
---

## **Introduction**

The following API method allows you to add a shape to a PowerPoint document. You can use this method to add shapes of many types, such as text boxes, charts, WordArt objects, SmartArt objects, pictures, OLE objects, tables, etc. To add the shape to a presentation slide, you should prepare an appropriate data transfer object and pass it to the parameters or specify an index of the shape to be cloned.

## **CreateShape**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes|POST|Adds a shape to a presentation slide.|[CreateShape](https://apireference.aspose.cloud/slides/#/Shapes/CreateShape)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide where a shape will be added.|
|dto|object|body|true|The data transfer object with parameters for the new shape.|
|shapeToClone|integer|query|false|The 1-based index of a shape to be cloned.|
|position|integer|query|false|The 1-based index of a position for the new shape. By default, the shape is added to the end.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

For examples, see [Working with Shapes](/slides/working-with-shapes/).

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
