---
title: "Removing properties from a PowerPoint Presentation"
type: docs
url: /removing-properties-from-a-powerpoint-presentation/
weight: 40
---

## **Introduction**
Aspose.Slides Cloud allows you remove one or all properties from PowerPoint Presentation
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties|DELETE|Wipe a document clean of all properties|[DeleteSlidesDocumentProperties](https://apireference.aspose.cloud/slides/#/Properties/DeleteSlidesDocumentProperties)|
|/slides/{name}/documentproperties/{propertyName}|DELETE|Delete a named property|[DeleteSlidesDocumentProperty](https://apireference.aspose.cloud/slides/#/Properties/DeleteSlidesDocumentProperty)|

cURL Example

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/author" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzA4ODMsImV4cCI6MTU2MDExNzI4MywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.bhURwSdcASMrRj4ukvG5rWTT_O2JpzVKH436ekU1CW6ZO7wOqGnE8wtkMdq6oivVzazs8xwbeuJmluFpHLNBco7A0vU56_UXZ5cIsfNCIpTOp6e_lmeHYgOD1rnW8f6y9jWLRoerup2vzqppjbF-8KXZ2HgCOXpos4lzy7GLqWmElW9TGd2uOd3cFEu1rXmkiJzuyjEi1dFdZtvRPvNyqon5R9ZS5rxQ09GhaiRA6DW4HwFTS-jTAPQo0QGfv87b4Gg_DvnUu_JjWlAhIeqWIM72-xmvFQ_20mk-s6H7foiyvJSC65w-XN5AqUyAyE8rAZduIwcS7BuYiQuOqqen4w" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

 {

   "list":[

      {

         "name":"Author",

         "value":"XANDER",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Author",

            "relation":"self"

         }

      },

      {

         "name":"Category",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Category",

            "relation":"self"

         }

      },

      {

         "name":"Comments",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Comments",

            "relation":"self"

         }

      },

      {

         "name":"Company",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Company",

            "relation":"self"

         }

      },

      {

         "name":"Keywords",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Keywords",

            "relation":"self"

         }

      },

      {

         "name":"LastSavedBy",

         "value":"Xamder",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastSavedBy",

            "relation":"self"

         }

      },

      {

         "name":"Manager",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Manager",

            "relation":"self"

         }

      },

      {

         "name":"NameOfApplication",

         "value":"Aspose.Slides for .NET",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/NameOfApplication",

            "relation":"self"

         }

      },

      {

         "name":"RevisionNumber",

         "value":"4",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/RevisionNumber",

            "relation":"self"

         }

      },

      {

         "name":"Subject",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Subject",

            "relation":"self"

         }

      },

      {

         "name":"Template",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Template",

            "relation":"self"

         }

      },

      {

         "name":"Title",

         "value":"PowerPoint Presentation",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Title",

            "relation":"self"

         }

      },

      {

         "name":"TotalEditingTime",

         "value":"PT0S",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/TotalEditingTime",

            "relation":"self"

         }

      },

      {

         "name":"CreatedTime",

         "value":"2019-03-29T13:21:33Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/CreatedTime",

            "relation":"self"

         }

      },

      {

         "name":"LastPrinted",

         "value":"0001-01-01T00:00:00Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastPrinted",

            "relation":"self"

         }

      },

      {

         "name":"LastSavedTime",

         "value":"2019-06-08T21:55:50Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastSavedTime",

            "relation":"self"

         }

      },

      {

         "name":"Another Custom Property",

         "value":"Example Value",

         "builtIn":false,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Another%20Custom%20Property",

            "relation":"self"

         }

      },

      {

         "name":"Processed By Office",

         "value":"Scotland Team",

         "builtIn":false,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Processed%20By%20Office",

            "relation":"self"

         }

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
Aspose.Slides  Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Example**
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
