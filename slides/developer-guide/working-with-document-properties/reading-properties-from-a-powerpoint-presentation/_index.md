---
title: "Reading Properties from a PowerPoint Presentation"
type: docs
url: /reading-properties-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud allows reading of document properties from a PowerPoint Presentation. 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties|GET|Read all document properties from a presentation|[GetSlidesDocumentProperties](https://apireference.aspose.cloud/slides/#/Properties/GetSlidesDocumentProperties)|
|/slides/{name}/documentproperties/{propertyName}|GET|Read a document property by name|[GetSlidesDocumentProperty](https://apireference.aspose.cloud/slides/#/Properties/GetSlidesDocumentProperty)|
### **cURL Example**
{{% alert color="primary" %}}

In this example we are querying about the documents author using the resource **/slides/destination.pptx/documentProperties/Author.** You can read all properties at once using the **/slides/{name}/documentproperties** resource instead

{{% /alert %}}

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Token**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d84119"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Author" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "name":"Author",

   "value":"Xander Cage",

   "builtIn":true,

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Author",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}


## **SDK Source**
The Aspose.Slide Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidesThemeFonts.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidesThemeFonts.java" >}}

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
      
      $request = new Requests\GetSlidesThemeFontSchemeRequest($fileName, $index);
      $result = $slidesApi->getSlidesThemeFontScheme($request);
      print_r($result);

   } catch (Exception $e) {
      echo "Something went wrong: ", $e->getMessage(), "\n";
   }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "GetSlidesThemeFonts.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "GetSlidesThemeFonts.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidesThemeFonts.js" >}}

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
