---
title: "Get comments of a slide in a PowerPoint Presentation"
type: docs
url: /get-comments-of-a-slide-in-a-powerpoint-presentation/
weight: 80
---

## **Introduction**
Aspose.Slides Cloud lets you easily read comment information from a PowerPoint Presentation
### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/comments|GET|Read comment information for the given slide in PowerPoint Presentation|[GetSlidesSlideComments](https://apireference.aspose.cloud/slides/#/Slides/GetSlidesSlideComments)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/comments" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk4NjA5ODcsImV4cCI6MTU1OTk0NzM4NywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.syoUePcSLvXUVSXIYO7hYdG6Xuw2DyY8rv08JhnklMHBbZml9j6zXOZtUVp73L7F1if53zDipDwqjbwdZcbooxU6jwftPt8DX1jW4YDV6kaGzV1VU1neOm6b8D3vd26K1Mg_5sN5jeeCvN7cNo64NTDVAkEqgiUiNsdQ3xh16nJ9HPmnzIUnxGHNnQI-RxtJCm_WkQOQqtK3mieRi9MXgfwjP2tacgL_14O2vSvBN3kBXBb-R_gqw9w3c3OcF2KGZ1f26dNk_gYQw31Cz95bSY_5rg959IHC90t5NUbtthliBB1Hyhy5HWOZM4_hSKsvqBM9wwubwrHNl3CjDp0PVg" --ssl-no-revoke 

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "list":[

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/comments",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
### **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlideComments.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlideComments.java" >}}

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
      $index = 3;

      // Upload original document to storage
      $fileStream = fopen(realpath(__DIR__ . '/../..') . '\resources\\' . $fileName, 'r');
      $slidesApi->uploadFile($fileName,  $fileStream, CommonUtils::$MyStorage);
      
      $request = new Requests\GetSlidesSlideCommentsRequest($fileName, $index);
      $result = $slidesApi->getSlidesSlideComments($request);
      print_r($result);

   } catch (Exception $e) {
      echo "Something went wrong: ", $e->getMessage(), "\n";
   }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlideComments.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlideComments.java" >}}

{{< /tab >}}

{{< /tabs >}}
