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
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers** 

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/move?newPosition=3" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ\_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl\_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd\_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs\_V7PkVhz\_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA\_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke 

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
Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slidescloud/available-sdks/)
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
