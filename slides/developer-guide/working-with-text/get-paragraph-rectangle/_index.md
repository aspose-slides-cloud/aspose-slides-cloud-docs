---
title: "Get Paragraph Rectangle"
type: docs
url: /get-paragraph-rectangle/
weight: 110
---
## **Introduction**
The article shows how to obtain coordinates of the rectangle that bounds paragraph using Aspose.Slides Cloud.
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/bounds|GET|Returns coordinates of rect that bounds paragraph|[GetParagraphRectangle]()|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```
```sh

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/1/bounds" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```
{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns rectangle info.

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
TextBounds response = api.GetParagraphRectangle("MyPresentation.pptx", 1, 2, 1, null, null);
            
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

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}