---
title: "Get Placeholder Information from a PowerPoint Slide"
type: docs
url: /get-placeholder-information-from-a-powerpoint-slide/
weight: 30
---

## **Introduction**
Aspose.Slides Cloud allows you to read placeholder information from a PowerPoint Document. 
### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/placeholders|GET|Get list of all placeholders from the PowerPoint Presentation|[GetSlidesPlaceholders](https://apireference.aspose.cloud/slides/#/Placeholders/GetSlidesPlaceholders)|
|/slides/{name}/slides/{slideIndex}/placeholders/{placeholderIndex}|GET|Read placeholder information for the particular index|[GetSlidesPlaceholder](https://apireference.aspose.cloud/slides/#/Placeholders/GetSlidesPlaceholder)|

{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
| password | GET | string | Optional | Presentation password |
| folder | GET | string | Optional | Presentation folder |
| storage | GET | string | Optional | Presentation storage |

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< /expand-list >}}

#### **HTTP GET**
Gets placeholders information from a presentation.

{{< tabs tabTotal="2" tabID="2" tabName1="Example 1" tabName2="Example 2">}}

{{< tab tabNum="1" >}}

##### **Read placeholders information from `myPresentation.pptx`.**

###### **Request**
```
GET https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders
```

###### **Response** 

{{< expand-list title="JSON/XML representation of the Placeholders resource" >}}

{{< tabs tabTotal="2" tabID="3" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "placeholderLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/1",
            "relation": "self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/2",
            "relation": "self"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders",
        "relation": "self"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<Placeholders>
    <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders" rel="self"/>
    <Placeholder href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/1" rel="self"/>
    <Placeholder href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/2" rel="self"/>
</Placeholders>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}


###### **.Net SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");

Placeholders response = api.GetPlaceholders("myPresentation.pptx", 1);
foreach (ResourceUri uri in response.PlaceholderLinks)
{
    Console.WriteLine(uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/1 etc.
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

##### **Read placeholders information from `myPresentation.pptx` using storage parameters.**

###### **Request**
```
GET https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders?folder=SomeBucket/SomeFolder&storage=SomeAmazonS3Storage
```

###### **Response** 

{{< expand-list title="JSON/XML representation of the Placeholders resource" >}}

{{< tabs tabTotal="2" tabID="4" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "placeholderLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/1",
            "relation": "self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/2",
            "relation": "self"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders",
        "relation": "self"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<Placeholders>
    <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders" rel="self"/>
    <Placeholder href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/1" rel="self"/>
    <Placeholder href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/placeholders/2" rel="self"/>
</Placeholders>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}

{{< /tab >}}

{{< /tabs >}}

#### **HTTP PUT**
Not supported.

#### **HTTP POST**
Not supported.

#### **HTTP DELETE**
Not supported.


### **cURL Example**
{{% alert color="primary" %}} 

You can also append the Placeholder index using the resource **/slides/{name}/slides/{slideIndex}/placeholders/{placeholderIndex}** for getting the information for a particular Placeholder

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/placeholders" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs_V7PkVhz_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "placeholderLinks":[
      {
         "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/placeholders/1",
         "relation":"self"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/placeholders/2",
         "relation":"self"
      }
   ],
   "selfUri":{
      "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/placeholders",
      "relation":"self"
   }
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
### **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidePlaceholderInformation.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidePlaceholderInformation.java" >}}

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
        $placeholderIndex = 1;

        // Upload original document to storage
        $fileStream = fopen(realpath(__DIR__ . '/../..') . '\resources\\' . $fileName, 'r');
        $slidesApi->uploadFile($fileName,  $fileStream, CommonUtils::$MyStorage);
        
        $request = new Requests\GetSlidesPlaceholderRequest($fileName, $index, $placeholderIndex);
        $result = $slidesApi->getSlidesPlaceholder($request);
        print_r($result);

    } catch (Exception $e) {
        echo "Something went wrong: ", $e->getMessage(), "\n";
    }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidePlaceholderInformation.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlidePlaceholderInformation.java" >}}

{{< /tab >}}

{{< /tabs >}}
