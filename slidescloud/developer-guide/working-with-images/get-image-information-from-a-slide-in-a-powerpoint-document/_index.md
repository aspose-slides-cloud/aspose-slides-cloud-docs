---
title: "Get Image Information from a Slide in a PowerPoint Document"
type: docs
url: /get-image-information-from-a-slide-in-a-powerpoint-document/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud API allows you to easily read image information from a slide in a Power Point Doucument
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/images|GET|Get all image for a slide by a index|[GetSlidesSlideImages](https://apireference.aspose.cloud/slides/#/Images/GetSlidesSlideImages)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client\_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/images" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ\_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl\_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd\_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs\_V7PkVhz\_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA\_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke 

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "list":[

      {

         "width":275,

         "height":183,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/1",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/1/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/1/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/1/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":299,

         "height":168,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/2",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/2/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/2/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/2/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":275,

         "height":183,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/3",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/3/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/3/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/images/3/gif",

               "relation":"alternate"

            }

         ]

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/images",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidesImageWithFormats.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidesImageWithFormats.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetSlidesImageWithFormats.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidesImageWithFormats.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlidesImageWithFormats.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/available-sdks-html/)
