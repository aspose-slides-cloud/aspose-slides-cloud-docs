---
title: "Extract Shapes from a Slide Using Third Party Storage"
type: docs
url: /extract-shapes-from-a-slide-using-third-party-storage/
weight: 10
---


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
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidesSlideShapesStorage.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidesSlideShapesStorage.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetSlidesSlideShapesStorage.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidesSlideShapesStorage.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlidesThemeFonts.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
