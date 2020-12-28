---
title: "Move a slide to a new position in a PowerPoint Presentation"
type: docs
url: /move-a-slide-to-a-new-position-in-a-powerpoint-presentation/
weight: 60
---

## **Introduction**
Aspose.Slides Cloud lets you move a slide to a new position within a PowerPoint Presentation
### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/move|POST|Move a slide to a new position defined by the newPosition parameter|[PostSlidesReorder](https://apireference.aspose.cloud/slides/#/Slides/PostSlidesReorder)|

{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|password | POST | string | Optional | Presentation password |
|folder | POST | string | Optional | Presentation folder |
|storage | POST | string | Optional | Presentation storage |
|newPosition|POST|int|Required|New position of the slide. |

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< /expand-list >}}
#### **HTTP GET**
Not supported.

#### **HTTP PUT**
Not supported.

#### **HTTP POST**
Moves a slide to another position.

{{< tabs tabTotal="3" tabID="2" tabName1="Example 1">}}

{{< tab tabNum="1" >}}

##### **Move the 3rd slide to the 1st position.**

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3/move?newPosition=1 
```

###### **Response**

{{< expand-list title="Full resource response" >}}

{{< tabs tabTotal="2" tabID="3" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "slideList": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/4?folder=myFolder",
            "relation":"self"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder",
        "relation":"self"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<Slides xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/4?folder=myFolder" rel="self" />
</Slides>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}


###### **.Net SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
PostSlidesReorderRequest request = new PostSlidesReorderRequest
{
    Name = "myPresentation.pptx",
    SlideIndex = 3,
    NewPosition = 1
};
Slides response = api.PostSlidesReorder(request);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/1 etc.
}
```

{{< /tab >}}

{{< /tabs >}}

#### **HTTP DELETE**
Not supported.


### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers** 

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/move?newPosition=3" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs_V7PkVhz_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke 

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "slideList":[
      {
         "uri":{
            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1",
            "relation":"self"
         }
      },
      {
         "uri":{
            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/2",
            "relation":"self"
         }
      },
      {
         "uri":{
            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/3",
            "relation":"self"
         }
      }
   ],
   "selfUri":{
      "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides",
      "relation":"self"
   }
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
### **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "MoveSlides.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "MoveSlides.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "MoveSlides.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "MoveSlides.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "MoveSlides.java" >}}

{{< /tab >}}

{{< /tabs >}}
