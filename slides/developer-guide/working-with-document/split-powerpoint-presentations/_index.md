---
title: "Split PowerPoint Presentations"
type: docs
url: /split-powerpoint-presentations/
weight: 30
---

## **Introduction**
The article explains how to split a PowerPoint Presentation and export the resultant splits into various formats. 
### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/split|POST|Splits a file and stores the resultant parts on Storage|[PostSlidesSplit](https://apireference.aspose.cloud/slides/#/Document/PostSlidesSplit)|



{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|password|POST|string|Optional|Presentation password |
|folder|POST|string|Optional|The document folder. |
|storage|POST|string|Optional|The document storage. |
|format|POST|string|Optional 	See a table below for valid formats. Default value is jpeg. |
|from|POST|int|Optional|The start slide number for splitting, if is not specified splitting starts from the first slide of the presentation. |
|to|POST|int|Optional|The last slide number for splitting, if is not specified splitting ends at the last slide of the document. |
|height|POST|int|Optional|The height of slide in created file.  Not affected to html format. |
|width|POST|int|Optional|The width of slide in created file.  Not affected to html format. |
|destFolder|POST|string|Optional|Folder on storage where files are going to be uploaded. If not specified then files are uploaded to same folder as presentation. |
|fontsFolder|PUT|string|Optional|Storage folder containing custom fonts to be used with the presentation. |

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< expand-list title="Available values for format parameter" >}}

| **Parameter Value** | **Format of the returned Page** | 
| :- | :- |
|tiff|Tagged Image File Format |
|jpeg|Joint Photographic Experts Group Image Format |
|png|Portable Networks Graphic Image Format |
|bmp|Bitmap Picture |
|gif|Graphics Interchange Format |
|svg|Scalable Vector Graphics Format |
|html|HyperText Markup Language |
|pdf|Portable Document Format |
|xps|XML Paper Specification Format |
|pptx|Powerpoint 2007 2010 file format |
|odp|OpenDocument Presentation Format |
|ppt|Powerpoint 1997 2003 file format |
|pps|Powerpoint 1997 2003 Show|
|ppsx|PowerPoint Show |
|pptm|PowerPoint Macro-Enabled Presentation |
|ppsm|PowerPoint Macro-Enabled Show |
|potx|PowerPoint Design Templates |
|potm|PowerPoint Macro-Enabled Design Template |

{{< /expand-list >}}

{{< /expand-list >}}

#### **HTTP GET**
Not supported.

#### **HTTP POST**

##### **Example 1**

Splits the whole presentation into a set of jpeg images.

```
POST https://api.aspose.cloud/v3.0/slides/ShapeTest.pptx/split?folder=test
```

###### **Response:**

{{< expand-list title="JSON" >}}
```
{
    "slides": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/test/ShapeTest_1.jpeg",
            "relation": "self",
            "linkType": "image/jpeg",
            "title": "Slide 1"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/test/ShapeTest_2.jpeg",
            "relation": "self",
            "linkType": "image/jpeg",
            "title": "Slide 2"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/test/ShapeTest_3.jpeg",
            "relation": "self",
            "linkType": "image/jpeg",
            "title": "Slide 3"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/test.ppt?folder=test",
        "relation": "self"
    }
}
```
{{< /expand-list >}}
	
	
{{< expand-list title="XML" >}}
```
<SplitResult xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <link href="https://api.aspose.cloud/v3.0/slides/ShapeTest.pptx?folder=test" rel="self" />
    <Slides>
        <Slide href="https://api.aspose.cloud/v3.0/slides/storage/file/test/ShapeTest_1.jpeg" rel="self" type="image/jpeg" title="Slide 1" />
        <Slide href="https://api.aspose.cloud/v3.0/slides/storage/file/test/ShapeTest_2.jpeg" rel="self" type="image/jpeg" title="Slide 2" />
        <Slide href="https://api.aspose.cloud/v3.0/slides/storage/file/test/ShapeTest_3.jpeg" rel="self" type="image/jpeg" title="Slide 3" />
    </Slides>
</SplitResult>
```
{{< /expand-list >}}


###### **.Net SDK Code:**
``` csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSlidesSplitRequest request = new PostSlidesSplitRequest
{
    Name = "ShapeTest.pptx",
    Folder = "test"
};
SplitDocumentResult response = api.PostSlidesSplit(request);
foreach (ResourceUri slide in response.Slides)
{
    Console.WriteLine(slide.Href); //https://api.aspose.cloud/v3.0/slides/storage/file/test/ShapeTest_1.jpeg etc.
}
```

##### **Example 2**
Converts 2nd and 3rd slides of the presentation to PNG format and uploads them to "images" folder.

```
POST https://api.aspose.cloud/v3.0/slides/ShapeTest.pptx/split?from=2&to=3&format=png&destFolder=images
```

###### **Response:**

{{< expand-list title="JSON" >}}
```
{
    "slides": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/images/ShapeTest_2.png",
            "relation": "self",
            "linkType": "image/png",
            "title": "Slide 2"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/images/ShapeTest_2.png",
            "relation": "self",
            "linkType": "image/png",
            "title": "Slide 3"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/test.ppt",
        "relation": "self"
    }
}
```
{{< /expand-list >}}

{{< expand-list title="XML" >}}
```
<SplitResult xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <link href="https://api.aspose.cloud/v3.0/slides/ShapeTest.pptx" rel="self" />
    <Slides>
        <Slide href="https://api.aspose.cloud/v3.0/slides/storage/file/images/ShapeTest_2.png" rel="self" type="image/png" title="Slide 2" />
        <Slide href="https://api.aspose.cloud/v3.0/slides/storage/file/images/ShapeTest_3.png" rel="self" type="image/png" title="Slide 3" />
    </Slides>
</SplitResult>
```
{{< /expand-list >}}

###### **.Net SDK Code:**
``` csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSlidesSplitRequest request = new PostSlidesSplitRequest
{
    Name = "ShapeTest.pptx",
    Folder = "test",
    From = 2,
    To = 3,
    Format = SlideExportFormat.Png,
    DestFolder = "Images"
};
SplitDocumentResult response = api.PostSlidesSplit(request);
foreach (ResourceUri slide in response.Slides)
{
    Console.WriteLine(slide.Href); //https://api.aspose.cloud/v3.0/slides/storage/file/Images/ShapeTest_2.png etc.
}
```

#### **HTTP PUT**
Not supported.

#### **HTTP DELETE**
Not supported.

### **cURL Example**
{{% alert color="primary" %}}

By skipping the **to** and **from** parameters in the request URL, the whole document is split page by page into the desired format.

{{% /alert %}}

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authetication Code**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/source.pptx/split?from=1&to=2&format=png" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3Njc2NjYsImV4cCI6MTU1OTg1NDA2NiwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.ostZtFSAtDFwvFygXzgg9optoSgYcrZWu2K2YPordXS7MRCbpSVV0wBuUPineb__3VdobkasIL5WGavlVTLa4d1R1_MxjZ5Wcv6Uth_lMir5bvngnECv3SREE3e0XHEtZQWy4uh23UmWnqu1UTM60NS-onYRLQ0-eqXYmMSts7yl8oTq_P1gepffW8oVssD6TZvcNqcUIPUCtC5sQXCEy7edlEsHOR611N_772RJZaZ-yd6BDUkBLZGrek9POLQvcM85uGK4uQ53uuzoV_5iYXE73jrYOXHgUIfcX1UDHhoJ4utt06sKH0FtugU5jT6rGqRuEi6LbahI2_63IVE7LQ" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "slides":[
      {
         "href":"https://api.aspose.cloud/v3.0/slides/storage/file/source_1.png",
         "relation":"self",
         "linkType":"image/png",
         "title":"Slide 1"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/storage/file/source_2.png",
         "relation":"self",
         "linkType":"image/png",
         "title":"Slide 2"
      }
   ],
   "selfUri":{
      "href":"https://api.aspose.cloud/v3.0/slides/source.pptx",
      "relation":"self"
   }
}

```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "SplitPresentations.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "SplitPresentations.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "SplitPresentations.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "SplitPresentations.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "SplitPresentations.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
