---
title: "Create a New Paragraph in a PowerPoint Presentation"
type: docs
url: /create-a-new-paragraph-in-a-powerpoint-presentation/
weight: 20
---

## **Introduction**
This article shows how you can create a new paragraph in PowerPoint presentations using Aspose.Slides for Cloud API. You can use our REST API with any language: .NET, Java, PHP, Ruby, Python, С++, and much more.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs|POST|Creates a new paragraph in a shape.|[CreateParagraph](https://apireference.aspose.cloud/slides/#/Shapes/CreateParagraph)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The presentation file name.|
|slideIndex|integer|path|true|The 1-based index of the presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|dto|object|body|true|The data transfer object of the paragraph.|
|position|integer|query|false|The position of the new paragraph in the list. Default is at the end of the list.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **cURL Example**
Add a new paragraph to the end of a shape (Text Box) at index 2 on the first slide. The paragraph text must be "Best regards, John" and spacing above the paragraph must be 24 pt. The storage is 'Main'. The folder is 'Data'.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](https://docs.aspose.cloud/slides/available-sdks/).

## **SDK Examples**
{{< tabs tabTotal="11" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php

```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python

```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js

```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java

```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp

```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go

```

{{< /tab >}}

{{< /tabs >}}
