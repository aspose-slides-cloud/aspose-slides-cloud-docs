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
### **cURL Example**
{{% alert color="primary" %}} 

You can also append the Placeholder index using the resource **/slides/{name}/slides/{slideIndex}/placeholders/{placeholderIndex}** for getting the information for a particular Placeholder

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/placeholders" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ\_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl\_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd\_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs\_V7PkVhz\_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA\_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "placeholderLinks":[

      {

         "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/placeholders/1",

         "relation":"self"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/placeholders/2",

         "relation":"self"

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/placeholders",

      "relation":"self"

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

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidePlaceholderInformation.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidePlaceholderInformation.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetSlidePlaceholderInformation.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidePlaceholderInformation.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlidePlaceholderInformation.java" >}}

{{< /tab >}}

{{< /tabs >}}
