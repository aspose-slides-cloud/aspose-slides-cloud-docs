---
title: "Extract Shapes from a Slide"
type: docs
url: /extract-shapes-from-a-slide/
weight: 10
---

## **Introduction**
This article shows how to retrieve all shapes or shapes of the specified type from the slide.
### **API Information**
|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{slideIndex}/shapes|GET|Read slide shapes info|[GetShapes](https://apireference.aspose.cloud/slides/#/Shapes/GetShapes)|

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Header**

```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```
**Get all shapes**
```sh

curl -v "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes" -d "" -H "Authorization: Bearer MyAuthToken"

```
**Get shapes of the specified type**
```sh

curl -v "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?shapeType=chart" -d "" -H "Authorization: Bearer MyAuthToken"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

The shape info.

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Shapes result = api.GetShapes("MyPresentation.pptx", 1, null, null, null);
```

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Shapes result = api.GetShapes("MyPresentation.pptx", 1, ShapeType.Chart, null, null);
```
{{< /tab >}}

{{< tab tabNum="2" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}