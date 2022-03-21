---
title: "Add Chart Series"
type: docs
url: /convert-using-fontfallbackrules/
weight: 10
---
## **Introduction**
Aspose.Slides Cloud allows specifying the rules to apply a fallback font. **FontFallbackRule** represents an association between the specified Unicode range, used for searching missed glyphs, and a list of fonts that may contain proper glyphs.
### **API Information**
FontFallbackRule is a part of ExportOptions and can be applied in any feature that assumed conversion.  For example:
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/{format}|POST|Save a presentation to a specified format|[DownloadPresentation](https://apireference.aspose.cloud/slides/#/Document/DownloadPresentation)|
/slides/{name}/{format}|PUT|Save presentation to a specified format|[SavePresentation](https://apireference.aspose.cloud/slides/#/Document/SavePresentation)|
/slides/convert/format|POST|Convert presentation from request content to format specified|[Convert](https://apireference.aspose.cloud/slides/#/Document/Convert)|
/slides/convert/format|PUT|Convert presentation from request content to format specified|[ConvertAndSave](https://apireference.aspose.cloud/slides/#/Document/ConvertAndSave)|
/slides/{name}/split|POST|Splitting presentations|[Split](https://apireference.aspose.cloud/slides/#/Document/Split)
/sldies/split/{format}|POST|Splitting presentations from request|[SplitOnline](https://apireference.aspose.cloud/slides/#/Document/SplitOnline)|
/sldies/split/{format}|PUT|Splitting presentations from request|[SplitAndSaveOnline](https://apireference.aspose.cloud/slides/#/Document/SplitAndSaveOnline)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/png" -d @"options.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```

options.json file:
```javascript
{
    "format":"image",
    "FontFallbackRules":[
        {"RangeStartIndex": 0x0B80,
        "RangeEndIndex": 0x0BFF,
        FallbackFontList: ["Arial"]}
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns the document.

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
List<FontFallbackRule> fontRules = new List<FontFallbackRule>();
fontRules.Add(new FontFallbackRule()
{
    RangeStartIndex = c_startUnicodeIndex,
    RangeEndIndex = c_endUnicodeIndex,
    FallbackFontList = new List<string>() { "Vijaya" }
});

fontRules.Add(new FontFallbackRule()
{
    RangeStartIndex = c_startUnicodeIndex,
    RangeEndIndex = c_endUnicodeIndex,
    FallbackFontList = new List<string>() { "Segoe UI Emoji, Segoe UI Symbol", "Arial" }
});

ImageExportOptions exportOptions = new ImageExportOptions()
{
    FontFallbackRules = fontRules
};
            
Stream response = api.DownloadPresentation("MyPresentation.pptx", ExportFormat.Png, exportOptions, null, null);
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