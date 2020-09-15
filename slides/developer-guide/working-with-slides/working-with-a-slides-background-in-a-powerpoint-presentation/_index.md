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
|/slides/{name}/slides/{slideIndex}/background| |Delete the background from the slide at the given index|[DeleteSlidesSlideBackground](https://apireference.aspose.cloud/slides/#/Slides/DeleteSlidesSlideBackground)|
### **cURL Example**
{{% alert color="primary" %}} 

We demonstrate the PUT example below. The GET example is intuitive

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/background" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ\_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl\_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd\_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs\_V7PkVhz\_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA\_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke -d "{'FillFormat': {'Type': 'Picture', 'Base64Data': '{base 64 image data}', 'PictureFillMode': 'Stretch'} }"

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
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slidescloud/available-sdks/)
### **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "WorkingWithSlideBackground.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "WorkingWithSlideBackground.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "WorkingWithSlideBackground.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "WorkingWithSlideBackground.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "WorkingWithSlideBackground.java" >}}

{{< /tab >}}

{{< /tabs >}}
