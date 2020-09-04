---
title: "Extract Shapes from a Slide Using Third Party Storage"
type: docs
url: /extract-shapes-from-a-slide-using-third-party-storage/
weight: 10
---

![todo:image\_alt\_text](/plugins/servlet/confluence/placeholder/unknown-macro)
## **Introduction**
This example allows you to extract shapes from a particular slide using third party Storage. You just need to use Aspose.Slides for Cloud API in any language: NET, Java, PHP, Ruby, Rails, Python, jQuery and much more.

**Note:** You need to configure Third Party Storage with Aspose for Cloud before using this example. Please follow the instructions at [this page](https://docs.aspose.cloud/display/storagecloud/How+to+Configure+3rd+Party+Cloud+Storages) to configure your required storage.
## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Slides](https://apireference.aspose.cloud/slides/).
## **REST Methods References**
We are referring some common methods in the REST examples to perform general operations. These methods can be found at the following page: [REST API Methods](https://apireference.aspose.cloud/slides/) 

## **cURLExample**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java

curl -v "http://api.aspose.cloud/v1.1/slides/sample-input.pptx/slides/1/shapes?appSid=xxxx&from=1&to=2&signature=xxxx&storage="mystorage" 

-X GET 

-H "Content-Type: application/json" 

-H "Accept: application/json"

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
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="9" tabID="4" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Objective C" tabName8="Perl" tabName9="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "9bc8522e2e3c9bc1323b9ce413dd3dbc" "Examples-DotNET-CSharp-Shapes-ExtractShapeUsingThirdPartyStorage-1.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "aspose-slides" "74de7640c8f072fe50c273602772094b" "Examples-JAVA-SDK-src-main-java-com-aspose-slides-cloud-examples-shapes-ExtractShapeUsingThirdPartyStorage-1.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "51dc0ddaa7b2a43dfb0423bf806de1f4" "Examples-PHP-Shapes-ExtractShapesFromASlideUsingThirdPartStorage-.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "553f01b949bcc9b9e502f93bcb733638" "Examples-Ruby-Shapes-extract\_shapes\_from\_a\_slide\_using\_third\_part\_storage-.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "aspose-slides" "95a1eec70765177679d02f656365f1da" "ExtractShapeFromSlideUsingThirdPartyStorage.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "0e4b22863aaa595f9c6c9e370c0b7792" "Examples-Node.js-Shapes-ExtractShapeUsingThirdPartyStorage-1.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "be8ff26063bd02327ae8b4dff8512fab" "Examples-Perl-Shapes-ExtractShapeUsingThirdPartyStorage-1.pl" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "aspose-slides" "30c37de1e8d2221a42041040c9224f66" "Examples-Android-app-src-main-java-com-aspose-slides-cloud-examples-shapes-ExtractShapeFromSlide-1.java" >}}

{{< /tab >}}

{{< /tabs >}}
