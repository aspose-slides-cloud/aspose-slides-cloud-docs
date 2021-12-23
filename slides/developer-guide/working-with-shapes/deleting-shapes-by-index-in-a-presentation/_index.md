---
title: "Deleting shapes by Index in a Presentation"
type: docs
url: /deleting-shapes-by-index-in-a-presentation/
weight: 70
---


## **Introduction**
This example allows you to format a text portion with a Slide. You can use our REST API with any language: NET, Java, PHP, Ruby, Rails, Python, jQuery and many more.
## **cURL Examples**
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

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "DeletShapeByIndex.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "DeletShapeByIndex.java" >}}

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
        $shapeIndex = 1;

        // Upload original document to storage
        $fileStream = fopen(realpath(__DIR__ . '/../..') . '\resources\\' . $fileName, 'r');
        $slidesApi->uploadFile($fileName,  $fileStream, CommonUtils::$MyStorage);
        
        $request = new Requests\DeleteSlideShapeRequest($fileName, $index, $shapeIndex);
        $result = $slidesApi->deleteSlideShape($request);
        print_r($result);

    } catch (Exception $e) {
        echo "Something went wrong: ", $e->getMessage(), "\n";
    }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "DeletShapeByIndex.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "DeletShapeByIndex.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "DeletShapeByIndex.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "DeletShapeByIndex.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
