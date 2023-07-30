---
title: "Remove a Paragraph by Index"
type: docs
url: /remove-a-paragraph-by-index/
weight: 60
---

## **Introduction**
This article shows how you can remove a paragraph by index in PowerPoint presentations using Aspose.Slides for Cloud API. You can use our REST API with any language: .NET, Java, PHP, Ruby, Python, С++, and much more.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|DELETE|Removes a paragraph in a shape.|[DeleteParagraph](https://apireference.aspose.cloud/slides/#/Shapes/DeleteParagraph)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The presentation file name.|
|slideIndex|integer|path|true|The 1-based index of the presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|paragraphIndex|integer|path|true|The 1-based index of the paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|
|subShape|string|query|false|Sub-shape path (e.g. "3", "3/shapes/2)

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **cURL Example**
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
