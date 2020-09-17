---
title: "Add a New Slide in a PowerPoint Presentation"
type: docs
url: /add-a-new-slide-in-a-powerpoint-presentation/
weight: 40
---

## **Introduction**
This example allows you to add new slides in a presentation using Aspose.Slides for Cloud API in your applications. You can use our REST API with any language: .NET, Java, PHP, Ruby, Rails, Python, jQuery and much more.
## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Slides](https://apireference.aspose.cloud/slides/).
## **REST Methods References**
We are referring to some common methods in the REST examples to perform general operations. These methods can be found on the following page: [REST API Methods](https://apireference.aspose.cloud/slides/) 
## **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers** 

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant_type=client_credentials&client_id=XXX&client_secret=XXXX-XX"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl -v "http://api.aspose.cloud/v1.1/slides/sample.pptx/slides"-X POST -H "Content-Type: application/json"-H "Accept: application/json" -H "Authorization: Bearer -Ou_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw_c8cAuk3qoag3g7bghMHw_pe_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR_hOD8Doqk5SBi_j-efODJK_PmGUxj0onOrUUx8Tj_GuUKrG6DcBnpl84_UykdOP87IeHnT2_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS_q3lthTDRMg2LuZ6s0r9MKlwVJ_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "Slides":{

      "SlideList":[

         {

            "Uri":{

               "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/slides/1",

               "Relation":"self",

               "LinkType":null,

               "Title":null

            }

         }

      ],

      "SelfUri":{

         "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/slides",

         "Relation":"self",

         "LinkType":null,

         "Title":null

      },

      "AlternateLinks":[

      ],

      "Links":[

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/slides",

            "Relation":"self",

            "LinkType":null,

            "Title":null

         }

      ]

   },

   "Code":200,

   "Status":"OK"

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
### **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "AddNewSlide.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "AddNewSlide.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "AddNewSlide.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "AddNewSlide.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "AddNewSlide.java" >}}

{{< /tab >}}

{{< /tabs >}}
