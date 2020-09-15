---
title: "Extract Shapes from a Slide"
type: docs
url: /extract-shapes-from-a-slide/
weight: 10
---

## **Introduction**
This example allows you to extract shapes from a particular slide using Aspose.Slides for Cloud API in your applications. You can use our REST API with any language  .NET, Java, PHP, Ruby, Rails, Python, jQuery and many more.
## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Slides](https://apireference.aspose.cloud/slides/#!/SlidesShapes/SlidesShapes_GetSlidesSlideShapes).
## **REST Methods References**
We are referring to some common methods in the REST examples to perform general operations. These methods can be found on the following page: [REST API Methods](https://apireference.aspose.cloud/slides/) 
## **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant\_type=client\_credentials&client\_id=&client\_secret="-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl -v "http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/1/shapes?from=1&to=2"-X GET -H "Content-Type: application/json"-H "Accept: application/json"-H "Authorization: Bearer -Ou\_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw\_c8cAuk3qoag3g7bghMHw\_pe\_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR\_hOD8Doqk5SBi\_j-efODJK\_PmGUxj0onOrUUx8Tj\_GuUKrG6DcBnpl84\_UykdOP87IeHnT2\_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS\_q3lthTDRMg2LuZ6s0r9MKlwVJ\_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

 {

   "ShapeList":{

      "ShapesLinks":[

         {

            "Uri":{

               "Href":"http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/1/shapes/1",

               "Relation":"self",

               "LinkType":null,

               "Title":null

            }

         },

         {

            "Uri":{

               "Href":"http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/1/shapes/2",

               "Relation":"self",

               "LinkType":null,

               "Title":null

            }

         },

         {

            "Uri":{

               "Href":"http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/1/shapes/3",

               "Relation":"self",

               "LinkType":null,

               "Title":null

            }

         }

      ],

      "SelfUri":{

         "Href":"http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/1/shapes",

         "Relation":"self",

         "LinkType":null,

         "Title":null

      },

      "AlternateLinks":[

      ],

      "Links":[

         {

            "Href":"http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/1/shapes",

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
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slidescloud/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Objective C" tabName8="Android" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "9bc8522e2e3c9bc1323b9ce413dd3dbc" "Examples-DotNET-CSharp-Shapes-ExtractShapes-1.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "aspose-slides" "74de7640c8f072fe50c273602772094b" "Examples-JAVA-SDK-src-main-java-com-aspose-slides-cloud-examples-shapes-ExtractShapeFromSlide-1.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "51dc0ddaa7b2a43dfb0423bf806de1f4" "Examples-PHP-Shapes-GetSlideShapes-.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "553f01b949bcc9b9e502f93bcb733638" "Examples-Ruby-Shapes-get\_slide\_shapes-.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "aspose-slides" "95a1eec70765177679d02f656365f1da" "ExtractShapeFromSlide.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "0e4b22863aaa595f9c6c9e370c0b7792" "Examples-Node.js-Shapes-ExtractShapes-1.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "aspose-slides" "30c37de1e8d2221a42041040c9224f66" "Examples-Android-app-src-main-java-com-aspose-slides-cloud-examples-shapes-ExtractShapeFromSlide-1.java" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "be8ff26063bd02327ae8b4dff8512fab" "Examples-Perl-Shapes-ExtractShapes-1.pl" >}}

{{< /tab >}}

{{< /tabs >}}
