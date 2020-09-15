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
### **cURL Example**
{{% alert color="primary" %}} 

By omitting the slide index parameter you can clean the presentation of all slides

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers** 

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ\_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl\_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd\_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs\_V7PkVhz\_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA\_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke 

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "slideList":[

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1",

            "relation":"self"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/2",

            "relation":"self"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/3",

            "relation":"self"

         }

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slidescloud/available-sdks/)
### **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

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

{{< gist "" "bc650902bdc45144b1727d329023dcba" "DeleteSlides.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "DeleteSlides.java" >}}

{{< /tab >}}

{{< /tabs >}}
