---
title: "Working with a slides background in a PowerPoint Presentation"
type: docs
url: /working-with-a-slides-background-in-a-powerpoint-presentation/
weight: 70
---

## **Introduction**
Aspose.Slides Cloud allows you to easily read and update the background for any slide in a PowerPoint presentation
### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/background|PUT|Update the background for the given slide. To get more information about the UpdateBackground DTO, please refer to [API Specification](https://apireference.aspose.cloud/slides/#/) and search for the **UpdateBackground** object|[PutSlidesSlideBackground](https://apireference.aspose.cloud/slides/#/Slides/PutSlidesSlideBackground)|
|/slides/{name}/slides/{slideIndex}/background|GET|Read the background information from a given slide|[GetSlidesSlideBackground](https://apireference.aspose.cloud/slides/#/Slides/GetSlidesSlideBackground)|
|/slides/{name}/slides/{slideIndex}/background|DELETE |Delete the background from the slide at the given index|[DeleteSlidesSlideBackground](https://apireference.aspose.cloud/slides/#/Slides/DeleteSlidesSlideBackground)|

{{< expand-list title="Properties" >}}

| ** Property Name ** | **Type** | **Description** | 
| :- | :- | :- | :- | :- |
|Type  |  NotDefined / NoFill / Solid / Gradient / Pattern / Picture | Presentation password. |
|FillFormat  | [FillFormat](/slides/fill-format-type/) |  The fill format of background.  |
|EffectFormat  | [EffectFormat](/slides/effect-format-type/) | The effect format of background.  |

{{< /expand-list >}}

{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
| password|GET/POST/DELETE|string|Optional|Presentation password |
| folder|GET/PUT/DELETE|string|Optional|Presentation folder |
| storage|GET/PUT/DELETE|string|Optional|Presentation storage |

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< /expand-list >}}

#### **HTTP GET**
Returns a JSON/XML representation of the resource.

{{< tabs tabTotal="1" tabID="2" tabName1="Example 1">}}

{{< tab tabNum="1" >}}

##### **Get background type of first slide.**

###### **Request**
```
GET https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/background?folder=myFolder
```

###### **Response**

{{< expand-list title="Full resource response" >}}

{{< tabs tabTotal="2" tabID="3" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Type": "NoFill",
    "FillFormat": {
        "Type": "NoFill"
    },
    "SelfUri": {
        "Href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/background?folder=myFolder",
        "Relation": "self"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<SlideBackground xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/background?folder=myFolder" rel="self" />
    <Type>NoFill</Type>
    <FillFormat xsi:type="NoFill"/>
</SlideBackground>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}


###### **.Net SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
SlideBackground response = api.GetBackground("myPresentation.pptx", 1, folder: "myFolder");
Console.WriteLine(response.Type); //NoFill
```

{{< /tab >}}

{{< /tabs >}}


#### **HTTP POST**
Not supported.

#### **HTTP PUT**
Updates background.

{{< tabs tabTotal="1" tabID="4" tabName1="Example 1">}}

{{< tab tabNum="1" >}}

##### **Set image to background. Image is encodded in base64 format.**

###### **Request**
```
PUT https://api.aspose.cloud/v3.0/slides/ImageContentShape.pptx/slides/1/background
```

{{< expand-list title="Request body:" >}}

{{< tabs tabTotal="2" tabID="6" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
  "FillFormat": {
    "Type": "Picture",
    "Base64Data": "iVBORw0KGgoAAAANSUhEUgAAAIwAAACMCAYAAACuwEE+...",
    "PictureFillMode": "Stretch"
  }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<SlideBackground xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >
  <FillFormat xsi:type="PictureFill">
<Base64Data>iVBORw0KGgoAAAANSUhEUgAAAIwAAACMCAYAAACuwEE+...</Base64Data>
    <PictureFillMode>Stretch</PictureFillMode>
  </FillFormat>
</SlideBackground>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}

###### **Response**

{{< expand-list title="Full resource response" >}}

{{< tabs tabTotal="2" tabID="7" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Type": "Picture",
    "FillFormat": {
        "Type": "Picture",
        "CropBottom": 0.0,
        "CropLeft": 0.0,
        "CropRight": 0.0,
        "CropTop": 0.0,
        "Dpi": 0,
        "Image": {
            "Href": "https://api.aspose.cloud/v3.0/slides/ImageContentShape.pptx/images/3",
            "Relation": "self"
        },
        "Base64Data": null,
        "PictureFillMode": "Stretch"
    },
    "SelfUri": {
        "Href": "https://api.aspose.cloud/v3.0/slides/ImageContentShape.pptx/slides/1/background",
        "Relation": "self"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<Background>
    <link href="https://api.aspose.cloud/v3.0/slides/ImageContentShape.pptx/slides/1/background" rel="self" />
    <Type>Picture</Type>
    <FillFormat xsi:type="PictureFill">
        <CropBottom>0</CropBottom>
        <CropLeft>0</CropLeft>
        <CropRight>0</CropRight>
        <CropTop>0</CropTop>
        <Dpi>0</Dpi>
        <Image href="https://api.aspose.cloud/v3.0/slides/ImageContentShape.pptx/images/3" rel="self" />
        <PictureFillMode>Stretch</PictureFillMode>
    </FillFormat>
</Background>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}


###### **.Net SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
PictureFill fill = new PictureFill
{
    Base64Data = "/9j/4AAQSkZJRgABAQAASABIAAD...",
    PictureFillMode = PictureFill.PictureFillModeEnum.Stretch
};
SlideBackground background = new SlideBackground { FillFormat = fill };
SlideBackground response = api.SetBackground("ImageContentShape.pptx", 1, background);
Console.WriteLine(response.Type); //Picture
```

{{< /tab >}}

{{< /tabs >}}

#### **HTTP DELETE**
Removes  background of slide.

{{< tabs tabTotal="1" tabID="8" tabName1="Example 1">}}

{{< tab tabNum="1" >}}

##### **Removes  background of slide.**

###### **Request**
```
DELETE https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/background
```

###### **Response**

{{< expand-list title="Full resource response" >}}

{{< tabs tabTotal="2" tabID="9" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Type": "NoFill",
    "FillFormat": {
        "Type": "NoFill"
    },
    "SelfUri": {
        "Href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/background",
        "Relation": "self",
        "LinkType": null,
        "Title": null
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<Background>
    <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1/background" rel="self" />
    <Type>NoFill</Type>
    <FillFormat xsi:type="NoFill"/>
</Background>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}


###### **.Net SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
SlideBackground response = api.DeleteBackground("NewPresentation.pptx", 1, folder: "TempSlidesSDK");
Console.WriteLine(response.Type); //NoFill
```

{{< /tab >}}

{{< /tabs >}}

### **cURL Example**
{{% alert color="primary" %}} 

We demonstrate the PUT example below. The GET example is intuitive

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/background" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs_V7PkVhz_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke -d "{'FillFormat': {'Type': 'Picture', 'Base64Data': '{base 64 image data}', 'PictureFillMode': 'Stretch'} }"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{
    "Type": "Picture",
    "FillFormat": {
        "Type": "Picture",
        "CropBottom": 0.0,
        "CropLeft": 0.0,
        "CropRight": 0.0,
        "CropTop": 0.0,
        "Dpi": 0,
        "Image": {
            "Uri": {
                "Href": "https://api.aspose.cloud/v3.0/slides/ImageContentShape.pptx/images/3",
                "Relation": "self",
                "LinkType": null,
                "Title": null
            }
        },
        "Base64Data": null,
        "PictureFillMode": "Stretch"
    },
    "SelfUri": {
        "Href": "https://api.aspose.cloud/v3.0/slides/ImageContentShape.pptx/slides/1/background",
        "Relation": "self"
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

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "WorkingWithSlideBackground.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "WorkingWithSlideBackground.java" >}}

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
        $slideBackground = new Model\SlideBackground();
        $slideBackground->setType(Model\SlideBackground::TYPE_SOLID);

        // Upload original document to storage
        $fileStream = fopen(realpath(__DIR__ . '/../..') . '\resources\\' . $fileName, 'r');
        $slidesApi->uploadFile($fileName,  $fileStream, CommonUtils::$MyStorage);
        
        $request = new Requests\PutSlidesSlideBackgroundRequest($fileName, $index, $slideBackground);
        $result = $slidesApi->putSlidesSlideBackground($request);
        print_r($result);

    } catch (Exception $e) {
        echo "Something went wrong: ", $e->getMessage(), "\n";
    }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "WorkingWithSlideBackground.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "WorkingWithSlideBackground.java" >}}

{{< /tab >}}

{{< /tabs >}}
