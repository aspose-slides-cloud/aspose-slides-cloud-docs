---
title: "Get Image Information from a PowerPoint Document"
type: docs
url: /get-image-information-from-a-powerpoint-document/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud API allows you to easily read image information from a Power Point Document
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/images|GET|Get all image information from a Power Point Document|[GetSlidesImages](https://apireference.aspose.cloud/slides/#/Images/GetSlidesImages)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NDY0NTQsImV4cCI6MTU1OTkzMjg1NCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.jeWJiVCVWeRJ_1Uux9PP701XZ7inSf2g1gotFTBkb76tWBOJf7cASswVUM7gXhMKSZ7suYwRl_ZC0KmGHUiVjCBQZrjsAAAvwZsFIHLZMd_H-hbZti4XPjRSChUYzTF1kJ1vnvLEABXPf4yybZqNdbqe5zBMtsWuVFtaNs_V7PkVhz_e3v1L6nYKw84VbINMOCwqMXd2EwRilzt7VsKWBL47A1AY1D3b-Mp4xrKoc5ICWUAA_qqEOaPmp1V8GF0OzjFgn6FKeeSa13pIbD7Xt6qVZDpK2mm11vGnlGE3FMgSUz7HWempfsNyo1KpAiDhQG4VS6wl3QYdyVB7EzwyPA" --ssl-no-revoke

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

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/1",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/1/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/1/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/1/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":299,

         "height":168,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/2",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/2/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/2/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/2/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":275,

         "height":183,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/3",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/3/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/3/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/3/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":275,

         "height":183,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/4",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/4/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/4/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/4/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":273,

         "height":184,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/5",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/5/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/5/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/5/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":183,

         "height":275,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/6",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/6/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/6/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/6/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":300,

         "height":168,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/7",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/7/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/7/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/7/gif",

               "relation":"alternate"

            }

         ]

      },

      {

         "width":355,

         "height":142,

         "contentType":"image/jpeg",

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/8",

            "relation":"self"

         },

         "alternateLinks":[

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/8/jpeg",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/8/png",

               "relation":"alternate"

            },

            {

               "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images/8/gif",

               "relation":"alternate"

            }

         ]

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/images",

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

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidesImageWithDefaultFormats.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidesImageWithDefaultFormats.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetSlidesImageWithDefaultFormats.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidesImageWithDefaultFormats.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlidesImageWithDefaultFormats.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}

### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
