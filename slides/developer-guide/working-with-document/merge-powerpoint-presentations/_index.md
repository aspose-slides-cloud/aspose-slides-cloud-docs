---
title: "Merge PowerPoint Presentations"
type: docs
url: /merge-powerpoint-presentations/
weight: 40
---

## **Introduction**
This example allows you to merge multiple presentation files using Aspose.Slides for Cloud API in your applications. You can use our REST API with any language:  NET, Java, PHP, Ruby, Rails, Python, jQuery, and much more.
## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Merge Presentations](https://apireference.aspose.cloud/slides/#!/SlidesMergeDocument/SlidesMergeDocument_PostPresentationMerge).
## **REST Methods References**
We are referring to some common methods in the REST examples to perform general operations. These methods can be found on the following page: [REST API Methods](https://apireference.aspose.cloud/slides/) 
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slidescloud/available-sdks/)
## **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Auth Header**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXXX&client\_secret=XXXX-XX"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl -v "http://api.aspose.cloud/v1.1/slides/sample.pptx/merge" -d '{"PresentationPaths": ["merge1.pptx","merge2.pptx"]}' -X POST -H "Content-Type: application/json" -H "Accept: application/json"-H "Accept:application/json" -H "Authorization: Bearer -Ou\_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw\_c8cAuk3qoag3g7bghMHw\_pe\_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR\_hOD8Doqk5SBi\_j-efODJK\_PmGUxj0onOrUUx8Tj\_GuUKrG6DcBnpl84\_UykdOP87IeHnT2\_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS\_q3lthTDRMg2LuZ6s0r9MKlwVJ\_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "Document":{

      "DocumentProperties":{

         "Uri":{

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/documentProperties",

            "Relation":"self",

            "LinkType":null,

            "Title":null

         }

      },

      "Slides":{

         "Uri":{

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/slides",

            "Relation":"self",

            "LinkType":null,

            "Title":null

         }

      },

      "Images":{

         "Uri":{

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/images",

            "Relation":"self",

            "LinkType":null,

            "Title":null

         }

      },

      "LayoutSlides":{

         "Uri":{

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/layoutSlides",

            "Relation":"self",

            "LinkType":null,

            "Title":null

         }

      },

      "MasterSlides":{

         "Uri":{

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/masterSlides",

            "Relation":"self",

            "LinkType":null,

            "Title":null

         }

      },

      "SelfUri":{

         "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx",

         "Relation":"self",

         "LinkType":null,

         "Title":null

      },

      "AlternateLinks":[

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=odp",

            "Relation":"alternate",

            "LinkType":"application/vnd.oasis.opendocument.presentation",

            "Title":"Download as Odp"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppt",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint",

            "Title":"Download as Ppt"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pdf",

            "Relation":"alternate",

            "LinkType":"application/pdf",

            "Title":"Download as Pdf"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=tiff",

            "Relation":"alternate",

            "LinkType":"image/tiff",

            "Title":"Download as Tiff"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=xps",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-xpsdocument",

            "Title":"Download as Xps"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pps",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint",

            "Title":"Download as Pps"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppsx",

            "Relation":"alternate",

            "LinkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",

            "Title":"Download as Ppsx"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pptm",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",

            "Title":"Download as Pptm"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppsm",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",

            "Title":"Download as Ppsm"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=potx",

            "Relation":"alternate",

            "LinkType":"application/vnd.openxmlformats-officedocument.presentationml.template",

            "Title":"Download as Potx"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=potm",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",

            "Title":"Download as Potm"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=html",

            "Relation":"alternate",

            "LinkType":"text/html",

            "Title":"Download as Html"

         }

      ],

      "Links":[

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx",

            "Relation":"self",

            "LinkType":null,

            "Title":null

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=odp",

            "Relation":"alternate",

            "LinkType":"application/vnd.oasis.opendocument.presentation",

            "Title":"Download as Odp"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppt",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint",

            "Title":"Download as Ppt"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pdf",

            "Relation":"alternate",

            "LinkType":"application/pdf",

            "Title":"Download as Pdf"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=tiff",

            "Relation":"alternate",

            "LinkType":"image/tiff",

            "Title":"Download as Tiff"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=xps",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-xpsdocument",

            "Title":"Download as Xps"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pps",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint",

            "Title":"Download as Pps"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppsx",

            "Relation":"alternate",

            "LinkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",

            "Title":"Download as Ppsx"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pptm",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",

            "Title":"Download as Pptm"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppsm",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",

            "Title":"Download as Ppsm"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=potx",

            "Relation":"alternate",

            "LinkType":"application/vnd.openxmlformats-officedocument.presentationml.template",

            "Title":"Download as Potx"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=potm",

            "Relation":"alternate",

            "LinkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",

            "Title":"Download as Potm"

         },

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=html",

            "Relation":"alternate",

            "LinkType":"text/html",

            "Title":"Download\* Connection #0 to host api.aspose.cloud left intact

 as Html"

         }

      ]

   },

   "Code":200,

   "Status":"OK"

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slidescloud/available-sdks/) article to learn how to add an SDK to your project.


### **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "MergePresentations.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "MergePresentations.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "MergePresentations.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "MergePresentations.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "MergePresentations.java" >}}

{{< /tab >}}

{{< /tabs >}}
