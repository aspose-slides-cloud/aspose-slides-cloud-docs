---
title: "Create new PowerPoint Presentations"
type: docs
url: /create-new-powerpoint-presentations/
weight: 20
---

## **Introduction**
This example allows you to create a new empty presentation from scratch using Aspose.Slides Cloud API in your applications. Aspose.Slides Cloud API lets you create a new presentation from the following resources 
## **Using a Source**
Aspose.Slides Cloud allows you to create a PowerPoint Presentation using a source document as a starting point
### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/fromSource|POST|Create a new presentation from a Source Document in storage|[PostSlidesDocumentFromSource](https://apireference.aspose.cloud/slides/#/Document/PostSlidesDocumentFromSource)|
### **cURL Examples**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/new\_one\_source.pptx/fromSource?sourcePath=destination.pptx" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3NzMwMDQsImV4cCI6MTU1OTg1OTQwNCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.uz9tjVx3LddNa1POM2MEM6xGz5L4z4BaQgGQnLX55YT-\_5Dztj631qT19kWhLJcONgYDqMp-c8Tgv2lV0iGfoKs-ZLZsvjOlpv0Oq3QJywj17LoUWap8feZyRlIFZz6nxB-OQhdd8JHglHx3Fu\_l\_gEssp6TrhXX6wdOgPPmV3DOrNZJR8ylc-e8V2Fx8or47CVVJ21e35DVzVRJK2EM4W\_D7bh28jMSZqbVIS9FlA-INUD\_ZCjTG2ix7TlUcBxblkcMUykq-M6KbNk1rd34tS0wV3RopQ8YmL-xeDQyDu8KVqBoUUEwjzY5fI9Y5GvuvATW6PXLt\_5hGWmtlF874Q" --ssl-no-revoke -d {}

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "documentProperties":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/documentProperties",

         "relation":"self"

      }

   },

   "slides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/slides",

         "relation":"self"

      }

   },

   "images":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/images",

         "relation":"self"

      }

   },

   "layoutSlides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/layoutSlides",

         "relation":"self"

      }

   },

   "masterSlides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/masterSlides",

         "relation":"self"

      }

   },

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx",

      "relation":"self"

   },

   "alternateLinks":[

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/odp",

         "relation":"alternate",

         "linkType":"application/vnd.oasis.opendocument.presentation",

         "title":"Download as Odp"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/ppt",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint",

         "title":"Download as Ppt"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/pdf",

         "relation":"alternate",

         "linkType":"application/pdf",

         "title":"Download as Pdf"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/tiff",

         "relation":"alternate",

         "linkType":"image/tiff",

         "title":"Download as Tiff"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/xps",

         "relation":"alternate",

         "linkType":"application/vnd.ms-xpsdocument",

         "title":"Download as Xps"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/pps",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint",

         "title":"Download as Pps"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/ppsx",

         "relation":"alternate",

         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",

         "title":"Download as Ppsx"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/pptm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",

         "title":"Download as Pptm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/ppsm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",

         "title":"Download as Ppsm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/potx",

         "relation":"alternate",

         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.template",

         "title":"Download as Potx"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/potm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",

         "title":"Download as Potm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/otp",

         "relation":"alternate",

         "linkType":"application/vnd.oasis.opendocument.presentation-template",

         "title":"Download as Otp"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/html",

         "relation":"alternate",

         "linkType":"text/html",

         "title":"Download as Html"

      }

   ]

}

```

{{< /tab >}}

{{< /tabs >}}
## **Using an HTML Document**
Aspose.Slides Cloud allows you to create a PowerPoint Presentation using an HTML document in the request body
## **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/fromHtml|POST|Create a new presentation from a HTML Document is the request body|[PostSlidesDocumentFromHtml](https://apireference.aspose.cloud/slides/#/Document/PostSlidesDocumentFromHtml)|
### **cURL Examples**
{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/new\_one.pptx/fromHTML" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3NzMwMDQsImV4cCI6MTU1OTg1OTQwNCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.uz9tjVx3LddNa1POM2MEM6xGz5L4z4BaQgGQnLX55YT-\_5Dztj631qT19kWhLJcONgYDqMp-c8Tgv2lV0iGfoKs-ZLZsvjOlpv0Oq3QJywj17LoUWap8feZyRlIFZz6nxB-OQhdd8JHglHx3Fu\_l\_gEssp6TrhXX6wdOgPPmV3DOrNZJR8ylc-e8V2Fx8or47CVVJ21e35DVzVRJK2EM4W\_D7bh28jMSZqbVIS9FlA-INUD\_ZCjTG2ix7TlUcBxblkcMUykq-M6KbNk1rd34tS0wV3RopQ8YmL-xeDQyDu8KVqBoUUEwjzY5fI9Y5GvuvATW6PXLt\_5hGWmtlF874Q" --ssl-no-revoke -d "<html> <head></head> <body> <p>Html content</p> </body> </html>"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "documentProperties":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/documentProperties",

         "relation":"self"

      }

   },

   "slides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/slides",

         "relation":"self"

      }

   },

   "images":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/images",

         "relation":"self"

      }

   },

   "layoutSlides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/layoutSlides",

         "relation":"self"

      }

   },

   "masterSlides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/masterSlides",

         "relation":"self"

      }

   },

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx",

      "relation":"self"

   },

   "alternateLinks":[

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/odp",

         "relation":"alternate",

         "linkType":"application/vnd.oasis.opendocument.presentation",

         "title":"Download as Odp"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/ppt",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint",

         "title":"Download as Ppt"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/pdf",

         "relation":"alternate",

         "linkType":"application/pdf",

         "title":"Download as Pdf"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/tiff",

         "relation":"alternate",

         "linkType":"image/tiff",

         "title":"Download as Tiff"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/xps",

         "relation":"alternate",

         "linkType":"application/vnd.ms-xpsdocument",

         "title":"Download as Xps"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/pps",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint",

         "title":"Download as Pps"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/ppsx",

         "relation":"alternate",

         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",

         "title":"Download as Ppsx"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/pptm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",

         "title":"Download as Pptm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/ppsm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",

         "title":"Download as Ppsm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/potx",

         "relation":"alternate",

         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.template",

         "title":"Download as Potx"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/potm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",

         "title":"Download as Potm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/otp",

         "relation":"alternate",

         "linkType":"application/vnd.oasis.opendocument.presentation-template",

         "title":"Download as Otp"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one.pptx/html",

         "relation":"alternate",

         "linkType":"text/html",

         "title":"Download as Html"

      }

   ]

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="5" tabID="9" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "CreateNewPresentationFromHTML.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "CreateNewPresentationFromHTML.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "CreateNewPresentationFromHTML.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "CreateNewPresentationFromHTML.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "CreateNewPresentationFromHTML.java" >}}

{{< /tab >}}

{{< /tabs >}}
## **Using a Template**
Aspose.Slides Cloud allows you to create a PowerPoint Presentation Using a Template document in the request body
### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/Template?templatepath|POST|Create a new presentation from a template in storage|[PostSlidesDocumentFromTemplate](https://apireference.aspose.cloud/slides/#/Document/PostSlidesDocumentFromTemplate)|
### **cURL Example**
{{% alert color="primary" %}} 

You can download a sample template file from [TemplateCV.pptx](https://github.com/aspose-slides-cloud/aspose-slides-cloud-dotnet/blob/master/TestData/TemplateCV.pptx). The template is then populated with the below data. See the below cURL example to see how to use this information.

```java

<staff>

<person>

<name>John Doe</name>

<address>

<line1>10 Downing Street</line1>

<line2>London</line2>

</address>

<phone>+457 123456</phone>

<bio>Hi, I'm John and this is my CV</bio>

<skills>

<skill>

<title>C#</title>

<level>Excellent</level>

</skill>

<skill>

<title>C++</title>

<level>Good</level>

</skill>

<skill>

<title>Java</title>

<level>Average</level>

</skill>

</skills>

</person>

```

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="11" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/fromTemplate?templatePath=TemplateCV.pptx" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3NzMwMDQsImV4cCI6MTU1OTg1OTQwNCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.uz9tjVx3LddNa1POM2MEM6xGz5L4z4BaQgGQnLX55YT-\_5Dztj631qT19kWhLJcONgYDqMp-c8Tgv2lV0iGfoKs-ZLZsvjOlpv0Oq3QJywj17LoUWap8feZyRlIFZz6nxB-OQhdd8JHglHx3Fu\_l\_gEssp6TrhXX6wdOgPPmV3DOrNZJR8ylc-e8V2Fx8or47CVVJ21e35DVzVRJK2EM4W\_D7bh28jMSZqbVIS9FlA-INUD\_ZCjTG2ix7TlUcBxblkcMUykq-M6KbNk1rd34tS0wV3RopQ8YmL-xeDQyDu8KVqBoUUEwjzY5fI9Y5GvuvATW6PXLt\_5hGWmtlF874Q" --ssl-no-revoke -d "<staff> <person> <name>John Doe</name> <address> <line1>10 Downing Street</line1> <line2>London</line2> </address> <phone>+457 123456</phone> <bio>Hi, I'm John and this is my CV</bio> <skills> <skill> <title>C#</title> <level>Excellent</level> </skill> <skill> <title>C++</title> <level>Good</level> </skill> <skill> <title>Java</title> <level>Average</level> </skill> </skills> </person></staff>"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "documentProperties":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/documentProperties",

         "relation":"self"

      }

   },

   "slides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/slides",

         "relation":"self"

      }

   },

   "images":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/images",

         "relation":"self"

      }

   },

   "layoutSlides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/layoutSlides",

         "relation":"self"

      }

   },

   "masterSlides":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/masterSlides",

         "relation":"self"

      }

   },

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx",

      "relation":"self"

   },

   "alternateLinks":[

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/odp",

         "relation":"alternate",

         "linkType":"application/vnd.oasis.opendocument.presentation",

         "title":"Download as Odp"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/ppt",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint",

         "title":"Download as Ppt"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/pdf",

         "relation":"alternate",

         "linkType":"application/pdf",

         "title":"Download as Pdf"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/tiff",

         "relation":"alternate",

         "linkType":"image/tiff",

         "title":"Download as Tiff"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/xps",

         "relation":"alternate",

         "linkType":"application/vnd.ms-xpsdocument",

         "title":"Download as Xps"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/pps",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint",

         "title":"Download as Pps"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/ppsx",

         "relation":"alternate",

         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",

         "title":"Download as Ppsx"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/pptm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",

         "title":"Download as Pptm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/ppsm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",

         "title":"Download as Ppsm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/potx",

         "relation":"alternate",

         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.template",

         "title":"Download as Potx"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/potm",

         "relation":"alternate",

         "linkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",

         "title":"Download as Potm"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/otp",

         "relation":"alternate",

         "linkType":"application/vnd.oasis.opendocument.presentation-template",

         "title":"Download as Otp"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/new\_one\_template.pptx/html",

         "relation":"alternate",

         "linkType":"text/html",

         "title":"Download as Html"

      }

   ]

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="5" tabID="15" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "CreateNewPresentationFromTemplate.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "CreateNewPresentationFromTemplate.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "CreateNewPresentationFromTemplate.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "CreateNewPresentationFromTemplate.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "CreateNewPresentationFromTemplate.java" >}}

{{< /tab >}}

{{< /tabs >}}
### **SDK Source**
The Aspose  Cloud SDKs can be downloaded from the following page: [Available SDKs](/available-sdks/)
