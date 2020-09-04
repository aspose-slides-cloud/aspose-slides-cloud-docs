---
title: "Clone MasterSlide Information from a PowerPoint Presentation"
type: docs
url: /clone-masterslide-information-from-a-powerpoint-presentation/
weight: 30
---

## **Introduction**
Aspose.Slides Cloud API allows you clone MasterSlide information from a source PowerPoint Presentation and apply to a destination presentation
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/masterSlides|GET|Clone MasterSlide information from a source and apply to a destination presentation|[PostCopyMasterSlideFromSourcePresentation](https://apireference.aspose.cloud/slides/#/MasterSlides/PostCopyMasterSlideFromSourcePresentation)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client\_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/destination.pptx/masterSlides?cloneFrom=presentation\_images.pptx&cloneFromPosition=1&applyToAll=true" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS\_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw" --ssl-no-revoke -d{}

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "name":"Slice",

   "layoutSlides":[

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/12",

            "relation":"self",

            "title":"Title Slide, Type: Title"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/13",

            "relation":"self",

            "title":"Title and Content, Type: TitleAndObject"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/14",

            "relation":"self",

            "title":"Section Header, Type: SectionHeader"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/15",

            "relation":"self",

            "title":"Two Content, Type: TwoObjects"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/16",

            "relation":"self",

            "title":"Comparison, Type: TwoTextAndTwoObjects"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/17",

            "relation":"self",

            "title":"Title Only, Type: TitleOnly"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/18",

            "relation":"self",

            "title":"Blank, Type: Blank"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/19",

            "relation":"self",

            "title":"Content with Caption, Type: TitleObjectAndCaption"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/20",

            "relation":"self",

            "title":"Picture with Caption, Type: PictureAndCaption"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/21",

            "relation":"self",

            "title":"Panoramic Picture with Caption, Type: Custom"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/22",

            "relation":"self",

            "title":"Title and Caption, Type: Custom"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/23",

            "relation":"self",

            "title":"Quote with Caption, Type: Custom"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/24",

            "relation":"self",

            "title":"Name Card, Type: Custom"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/25",

            "relation":"self",

            "title":"Quote Name Card, Type: Custom"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/26",

            "relation":"self",

            "title":"True or False, Type: Custom"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/27",

            "relation":"self",

            "title":"Title and Vertical Text, Type: VerticalText"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides/28",

            "relation":"self",

            "title":"Vertical Title and Text, Type: VerticalTitleAndText"

         }

      }

   ],

   "dependingSlides":[

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1",

            "relation":"self"

         }

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/2",

            "relation":"self"

         }

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/masterSlides/2",

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

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "CopyMasterSlideFromSourcePresentation.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "CopyMasterSlideFromSourcePresentation.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "CopyMasterSlideFromSourcePresentation.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "CopyMasterSlideFromSourcePresentation.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "CopyMasterSlideFromSourcePresentation.java" >}}

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


