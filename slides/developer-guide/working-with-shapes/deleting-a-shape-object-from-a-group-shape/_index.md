---
title: "Deleting a Shape object from a Group Shape"
type: docs
url: /deleting-a-shape-object-from-a-group-shape/
weight: 50
---


## **Introduction**
This example allows you to delete a shape object from a presentation using Aspose.Slides for Cloud API in your applications. You can use our REST API with any language: .NET, Java, PHP, Ruby, Rails, Python, jQuery and much more.
## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Slides](https://apireference.aspose.cloud/slides/#!/SlidesDocument/SlidesDocument_PutSlidesConvert).
## **REST Methods References**
We are referring some common methods in the REST examples to perform general operations. These methods can be found at the following page: [REST API Methods](https://apireference.aspose.cloud/slides/) 
## **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java



```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java



```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**

{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "DeleteShapeObjectToGroupShape.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "DeleteShapeObjectToGroupShape.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
<?php 
    // For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

    include(dirname(__DIR__) . '\CommonUtils.php');
    use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
    use Aspose\Slides\Cloud\Sdk\Api\Configuration;
    use Aspose\Slides\Cloud\Sdk\Model;
    use Aspose\Slides\Cloud\Sdk\Model\Requests;

    try {
        // Create SlidesApi instance
        $config = new Configuration();
        $config->setAppSid(CommonUtils::$AppSid);
        $config->setAppKey(CommonUtils::$AppKey);
        $slidesApi = new SlidesApi(null, $config);

        $fileName = "test-unprotected.ppt";
        $index = 2;
        $shapes = array(1,3);

        // Upload original document to storage
        $fileStream = fopen(realpath(__DIR__ . '/../..') . '\resources\\' . $fileName, 'r');
        $slidesApi->uploadFile($fileName,  $fileStream, CommonUtils::$MyStorage);
        
        $request = new Requests\DeleteSlideShapesRequest($fileName, $index, null, $shapes);
        $result = $slidesApi->deleteSlideShapes($request);
        print_r($result);

    } catch (Exception $e) {
        echo "Something went wrong: ", $e->getMessage(), "\n";
    }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "DeleteShapeObjectToGroupShape.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "DeleteShapeObjectToGroupShape.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "DeleteShapeObjectToGroupShape.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "DeleteShapeObjectToGroupShape.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
