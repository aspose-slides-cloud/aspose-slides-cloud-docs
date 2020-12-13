---
title: "Delete Slides from a PowerPoint Presentation"
type: docs
url: /delete-slides-from-a-powerpoint-presentation/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud allows you to delete slides from a PowerPoint Presentation. 
### **API Information**
Aspose.Slides Cloud proides two resources to achive this. You can either delete a single slide or delete all slides in the Presentation

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}|DELETE|Delete the slide at the index|[DeleteSlideByIndex](https://apireference.aspose.cloud/slides/#/Slides/DeleteSlideByIndex)|
|/slides/{name}/slides/|DELETE|Delete all slides |[DeleteSlidesCleanSlidesList](https://apireference.aspose.cloud/slides/#/Slides/DeleteSlidesCleanSlidesList)|


#### **HTTP DELETE**
Removes slide by its position.

{{< tabs tabTotal="3" tabID="11" tabName1="Example 1" tabName2="Example 2" tabName3="Example 3" >}}

{{< tab tabNum="1" >}}

##### **Removes first slide.**

###### **Request**
```
DELETE https://api.aspose.cloud/v3.0/slides/genericPpt.ppt/slides/1
```

###### **Response**
{{< expand-list title="XML/JSON representation the presentation slides." >}}

{{< tabs tabTotal="2" tabID="1" tabName1="JSON" tabName2="XML" >}}

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
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
DeleteSlideByIndexRequest request = new DeleteSlideByIndexRequest
{
    Name = "genericPpt.ppt",
    SlideIndex = 1
};
Slides response = api.DeleteSlideByIndex(request);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/genericPpt.ppt/slides/1 etc.
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

##### **Removes all slides from presentation and adds one blank slide.**

###### **Request**
```
DELETE https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides
```

###### **Response**
{{< expand-list title="XML/JSON representation the presentation slides." >}}

{{< tabs tabTotal="2" tabID="12" tabName1="JSON" tabName2="XML" >}}

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
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
DeleteSlidesCleanSlidesListRequest request = new DeleteSlidesCleanSlidesListRequest
{
    Name = "myPresentation.pptx"
};
Slides response = api.DeleteSlidesCleanSlidesList(request);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

##### **Removes the first, fouth and sixth slides from the presentation.**

###### **Request**
```
DELETE https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?slides=1,4,6
```

###### **Response**
{{< expand-list title="XML/JSON representation the presentation slides." >}}

{{< tabs tabTotal="2" tabID="14" tabName1="JSON" tabName2="XML" >}}

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
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
DeleteSlidesCleanSlidesListRequest request = new DeleteSlidesCleanSlidesListRequest
{
    Name = "myPresentation.pptx",
    Slides = new List<int> { 1, 4, 6 }
};
Slides response = api.DeleteSlidesCleanSlidesList(request);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1 etc.
}
```

{{< /tab >}}

{{< /tabs >}}


### **cURL Example**
{{% alert color="primary" %}}

By omitting the slide index parameter you can clean the presentation of all slides

{{% /alert %}}

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs_V7PkVhz_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke

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

## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.

### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "DeleteSlides.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "DeleteSlides.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "DeleteSlides.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "DeleteSlides.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "DeleteSlides.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "DeleteSlides.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "DeleteSlides.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
