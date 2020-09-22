---
title: "Get a Particular Shape from the Slide"
type: docs
url: /get-a-particular-shape-from-the-slide/
weight: 20
---


## **Introduction**
This example allows you to get a particular shape from the slide using Aspose.Slides for Cloud API in your applications. You can use our REST API with any language NET, Java, PHP, Ruby, Rails, Python, jQuery and many more.
## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Slides](https://apireference.aspose.cloud/slides/#!/SlidesShapes/SlidesShapes_GetSlidesSlideShapes).
## **REST Methods References**
We are referring some common methods in the REST examples to perform general operations. These methods can be found at the following page: [REST API Methods](https://apireference.aspose.cloud/slides/) 
## **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d84119"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl -v "http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/2/shapes/1?from=1&to=2"

-X GET

-H "Content-Type: application/json"

-H "Accept: application/json"

 -H "Accept: application/json"-H "Authorization: Bearer -Ou_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw_c8cAuk3qoag3g7bghMHw_pe_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR_hOD8Doqk5SBi_j-efODJK_PmGUxj0onOrUUx8Tj_GuUKrG6DcBnpl84_UykdOP87IeHnT2_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS_q3lthTDRMg2LuZ6s0r9MKlwVJ_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "Shape":{

      "Type":"Shape",

      "Text":"Aspose Sample 2",

      "Paragraphs":{

         "Uri":{

            "Href":"http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/2/shapes/1/paragraphs",

            "Relation":"self",

            "LinkType":null,

            "Title":null

         }

      },

      "GeometryShapeType":"NotDefined",

      "ShapeType":-1,

      "Name":"Title 1",

      "Width":612.0,

      "Height":115.75,

      "AlternativeText":"",

      "Hidden":false,

      "X":54.0,

      "Y":167.75,

      "ZOrderPosition":0,

      "Shapes":null,

      "FillFormat":{

         "Type":"NoFill"

      },

      "LineFormat":{

         "Alignment":"Center",

         "CapStyle":"Flat",

         "DashStyle":"Solid",

         "JoinStyle":"Miter",

         "Style":"Single",

         "BeginArrowHead":{

            "Length":"Medium",

            "Style":"None",

            "Width":"Medium"

         },

         "EndArrowHead":{

            "Length":"Medium",

            "Style":"None",

            "Width":"Medium"

         },

         "CustomDashPattern":null,

         "FillFormat":{

            "Type":"NoFill"

         },

         "MiterLimit":8.0,

         "Width":0.75

      },

      "SelfUri":{

         "Href":"http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/2/shapes/1",

         "Relation":"self",

         "LinkType":null,

         "Title":null

      },

      "AlternateLinks":[

      ],

      "Links":[

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/2/shapes/1",

            "Relation":"s\* Connection #0 to host api.aspose.cloud left intact

elf",

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
## **SDK Examples**

{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidesSlideShape.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidesSlideShape.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetSlidesSlideShape.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidesSlideShape.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlidesSlideShape.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
