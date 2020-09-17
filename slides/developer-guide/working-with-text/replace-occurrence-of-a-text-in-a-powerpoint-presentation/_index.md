---
title: "Replace occurrence of a Text in a PowerPoint Presentation"
type: docs
url: /replace-occurrence-of-a-text-in-a-powerpoint-presentation/
weight: 20
---

## **Introduction**
Using Aspose.Slides Cloud you can you easily replace all occurrences of a Text. Aspose.Slides Cloud provides you methods to replace text in a individual slide or a presentation as a whole
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/replaceText|POST|Replace text within a presentation|[PostSlidesPresentationReplaceText](https://apireference.aspose.cloud/slides/#/Text/PostSlidesPresentationReplaceText)|
|/slides/{name}/slides/{slideIndex}/replaceText|POST|Replace text within a individual slide|[PostSlidesSlideReplaceText](https://apireference.aspose.cloud/slides/#/Text/PostSlidesSlideReplaceText)|
### **cURL Example**
{{% alert color="primary" %}} 

We are using the **/slides/{name}/slides/{slideIndex}/replaceText** resource as an example below. You can use **/slides/{name}/replaceText** with the same query parameters to replace all matching occurrences of the text items in the whole power point presentation

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/destination.pptx/replaceText?oldValue=banana&newValue=orange&ignoreCase=true" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzA4ODMsImV4cCI6MTU2MDExNzI4MywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.bhURwSdcASMrRj4ukvG5rWTT_O2JpzVKH436ekU1CW6ZO7wOqGnE8wtkMdq6oivVzazs8xwbeuJmluFpHLNBco7A0vU56_UXZ5cIsfNCIpTOp6e_lmeHYgOD1rnW8f6y9jWLRoerup2vzqppjbF-8KXZ2HgCOXpos4lzy7GLqWmElW9TGd2uOd3cFEu1rXmkiJzuyjEi1dFdZtvRPvNyqon5R9ZS5rxQ09GhaiRA6DW4HwFTS-jTAPQo0QGfv87b4Gg_DvnUu_JjWlAhIeqWIM72-xmvFQ_20mk-s6H7foiyvJSC65w-XN5AqUyAyE8rAZduIwcS7BuYiQuOqqen4w" --ssl-no-revoke -d {}

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "matches":0,

   "documentProperties":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties",

         "relation":"self"

      }

   },

   "slides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides",

         "relation":"self"

      }

   },

   "images":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/images",

         "relation":"self"

      }

   },

   "layoutSlides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/layoutSlides",

         "relation":"self"

      }

   },

   "masterSlides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/masterSlides",

         "relation":"self"

      }

   },

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx",

      "relation":"self"

   },

   "alternateLinks":[

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/odp",

         "relation":"alternate",

         "linkType":"application/vnd.oasis.opendocument.presentation",

         "title":"Download as Odp"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/ppt",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint",

         "title":"Download as Ppt"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/pdf",

         "relation":"alternate",

         "linkType":"application/pdf",

         "title":"Download as Pdf"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/tiff",

         "relation":"alternate",

         "linkType":"image/tiff",

         "title":"Download as Tiff"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/xps",

         "relation":"alternate",

         "linkType":"application/vnd.ms-xpsdocument",

         "title":"Download as Xps"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/pps",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint",

         "title":"Download as Pps"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/ppsx",

         "relation":"alternate",

         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",

         "title":"Download as Ppsx"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/pptm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",

         "title":"Download as Pptm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/ppsm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",

         "title":"Download as Ppsm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/potx",

         "relation":"alternate",

         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.template",

         "title":"Download as Potx"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/potm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",

         "title":"Download as Potm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/otp",

         "relation":"alternate",

         "linkType":"application/vnd.oasis.opendocument.presentation-template",

         "title":"Download as Otp"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/html",

         "relation":"alternate",

         "linkType":"text/html",

         "title":"Download as Html"

      }

   ]

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
