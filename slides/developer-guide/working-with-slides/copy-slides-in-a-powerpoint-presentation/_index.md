---
title: "Copy Slides in a PowerPoint Presentation"
type: docs
url: /copy-slides-in-a-powerpoint-presentation/
weight: 50
---

## **Introduction**
Aspose.Slides Cloud lets you easily copy a slide with its content to create a new slide within a PowerPoint presentation
### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/copy|POST|Copy a slide to create a new slide|[PostSlidesCopy](https://apireference.aspose.cloud/slides/#/Slides/PostSlidesCopy)|

{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|password | POST | string | Optional | Presentation password |
|folder | POST | string | Optional | Presentation folder |
|storage | POST | string | Optional | Presentation storage |
|position | POST | int | Optional | New slide position. Copy to the end by default |
|slideToCopy | POST | int | Required | Position of slide to copy |
|source | POST | string | Optional | The presentation to copy the slide from. If not specified, the slide is copied from the current presentation |
|sourcePassword | POST | string | Optional | Source presentation password. Ignored if source parameter is not specified |

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< /expand-list >}}

#### **HTTP POST**
Copies a presentation slide.

{{< tabs tabTotal="3" tabID="2" tabName1="Example 1" tabName2="Example 2" tabName3="Example 3">}}

{{< tab tabNum="1" >}}

##### **Adds copy of first slide to the end of slides list.**

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/copy?slideToCopy=1
```

###### **Response**

{{< expand-list title="Full resource response that includes cloned slide" >}}

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
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
Slides response = api.CopySlide("myPresentation.pptx", 1);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/1 etc.
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

##### **Creates copy of second slide and insert to third position.**

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/copy?position=3&slideToCopy=2
```

###### **Response**

{{< expand-list title="Full resource response that includes cloned slide" >}}

{{< tabs tabTotal="2" tabID="4" tabName1="JSON" tabName2="XML" >}}

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
Slides response = api.CopySlide("myPresentation.pptx", 2, 3);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/1 etc.
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

##### **Adds copy of second slide from presentation "reports/sales.pptx" at position 3**

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/copy?position=3&source=reports/sales.pptx&slideToCopy=2
```

###### **Response**

{{< expand-list title="Full resource response that includes cloned slide" >}}

{{< tabs tabTotal="2" tabID="6" tabName1="JSON" tabName2="XML" >}}

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
Slides response = api.CopySlide("myPresentation.pptx", 2, 3, "reports/sales.pptx");
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/1 etc.
}
```

{{< /tab >}}

{{< /tabs >}}


### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/copy?slideToCopy=1&position=2" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs_V7PkVhz_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke -d {

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
      },
      {
         "uri":{
            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/4",
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
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "CopySlides.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "CopySlides.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
<?php 
    // For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

    include(dirname(__DIR__) . '\CommonUtils.php');
    use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
    use Aspose\Slides\Cloud\Sdk\Api\Configuration;
    use Aspose\Slides\Cloud\Sdk\Model;
    use Aspose\Slides\Cloud\Sdk\Model\Requests;

    try {
        // Create SlidesApi instance
        $config = new Configuration();
        $config->setAppSid(CommonUtils::$AppSid);
        $config->setAppKey(CommonUtils::$AppKey);
        $slidesApi = new SlidesApi(null, $config);

        $fileName = "test-unprotected.ppt";
        $index = 1;
        $possition = 2;

        // Upload original document to storage
        $fileStream = fopen(realpath(__DIR__ . '/../..') . '\resources\\' . $fileName, 'r');
        $slidesApi->uploadFile($fileName,  $fileStream, CommonUtils::$MyStorage);
        
        $request = new Requests\PostSlidesCopyRequest($fileName, $index, $possition);
        $result = $slidesApi->postSlidesCopy($request);
        print_r($result);

    } catch (Exception $e) {
        echo "Something went wrong: ", $e->getMessage(), "\n";
    }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "CopySlides.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "CopySlides.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "CopySlides.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "CopySlides.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
