---
title: "Merge PowerPoint Presentations"
type: docs
url: /merge-powerpoint-presentations/
weight: 70
---


## **Introduction**
These examples show you how to merge multiple presentation files using Aspose.Slides for Cloud API in your applications. You can use our REST API with any language: .NET, Java, PHP, Ruby, Rails, Python, jQuery, and much more.

### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/merge|POST|Merges the presentation with other presentations specified in the request parameter.|[Merge](https://apireference.aspose.cloud/slides/#/MergeDocument/Merge)|
|/slides/{name}/merge|PUT|Merges the presentation with other presentations or some of their slides specified in the request parameter.|[OrderedMerge](https://apireference.aspose.cloud/slides/#/MergeDocument/OrderedMerge)|
|/slides/merge|POST|Merges presentations or some of their slides specified in the request parameter. Returns the result file in the response.|[MergeOnline](https://apireference.aspose.cloud/slides/#/MergeDocument/MergeOnline)|
|/slides/merge|PUT|Merges presentations or some of their slides specified in the request parameter. Result will be saved in the storage.|[MergeAndSaveOnline](https://apireference.aspose.cloud/slides/#/MergeDocument/MergeAndSaveOnline)|

{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|folder|POST/PUT|string (query)|Optional|The merging presentation folder.|
|storage|POST/PUT|string (query)|Optional|The presentations storage.|
|password|POST/PUT|string (header)|Optional|The merging presentation password.|
|outPath|PUT|string (query)|Required|A path to save the result.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< /expand-list >}}

#### **HTTP GET**
Not supported.

#### **HTTP POST**

##### **Example 1**

Merge presentation 'genericPptx.pptx' with presentations 'TempSlides\Pres1.pptx' and 'TempSlides\Pres2.pptx'. Using a password to open Pres1.pptx document.

###### **Request**

```
https://api.aspose.cloud/v3.0/slides/genericPptx.pptx/merge
```

{{< expand-list title="Request body:" >}}
**JSON**
```
{
    "PresentationPaths": [
        "TempSlides/Pres1.pptx",
        "TempSlides/Pres2.pptx"
    ],
    "PresentationPasswords": [
        "mypassword01"
    ]
}
```

**XML**
```
<PresentationsMergeRequest>
    <Path>TempSlides/Pres1.pptx</Path>
    <Path>TempSlides/Pres2.pptx</Path>
    <Password>mypassword01</Password>
</PresentationsMergeRequest>
```

{{< /expand-list >}}

###### **Response:**
Full resource representation. See a cURL response in [Reading Information about a Presentation](/slides/reading-information-about-a-presentation/) article.

###### **.Net SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PresentationsMergeRequest request = new PresentationsMergeRequest
{
    PresentationPaths = new List<string> { "TempSlides/Pres1.pptx", "TempSlides/Pres2.pptx" },
    PresentationPasswords = new List<string> { "mypassword01" }
};
Document response = api.Merge("genericPptx.pptx", request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/genericPptx.pptx
```

##### **Example 2**

Merge presentations without uploading them to a storage.

###### **Request**

```
https://api.aspose.cloud/v3.0/slides/merge
```

{{< expand-list title="Request body:" >}}
**JSON**
```
{
    "Presentations": [
        {
            "Path": "example1.pptx",
        },
        {
           "Path": "example2.pptx",
        }
    ]
}
```

{{< /expand-list >}}

###### **.Net SDK Code:**

```csharp
var slidesApi = new SlidesApi(config);

var file1 = new FileInfo { Content = File.OpenRead(@"TestData\example1.pptx") };
var file2 = new FileInfo { Content = File.OpenRead(@"TestData\example2.pptx") };

var files = new List<FileInfo> { file1, file2 };
var resultStream = slidesApi.MergeOnline(files);

var fileStream = File.Open("merge_result.pptx", FileMode.Create);
resultStream.CopyTo(fileStream);
```

#### **HTTP PUT**

##### **Example 1**
Merge presentation 'genericPptx.pptx' with second slide and first slide of presentation 'TempSlides\Pres1.pptx'

###### **Request**
```
https://api.aspose.cloud/v3.0/slides/genericPptx.pptx/merge
```

{{< expand-list title="Request body:" >}}
**JSON**
```
{
    "Presentations": [
        {
            "Path":   "TempSlides\Pres1.pptx",
            "Password": "mypassword01"
            "Slides": [2, 1]
        }
    ]
}
```

**XML**
```
<OrderedMergeRequest>
    <Presentation>
        <Path>TempSlides\Pres1.pptx</Path>
        <Password>mypassword01</Password>
        <Slide>2</Slide>
        <Slide>1</Slide>
    </Presentation>
</OrderedMergeRequest>
```

{{< /expand-list >}}

###### **Response:**
[Full presentation resource representation.](https://docs.aspose.cloud/slides/create-new-powerpoint-presentations/#response)

###### **.Net SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PresentationToMerge presentationToMerge = new PresentationToMerge
{
    Path = "TempSlides/Pres1.pptx",
    Password = "mypassword01",
    Slides = new List<int> { 2, 1 }
};
OrderedMergeRequest mergeRequest = new OrderedMergeRequest
{
    Presentations = new List<PresentationToMerge> { presentationToMerge }
};
Document response = api.OrderedMerge("NewPresentation.pptx", mergeRequest, folder: "TempSlidesSDK");
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/genericPptx.pptx
```

##### **Example 2**
Merge a presentation 'TestData/example1.pptx' existing on a storage with specified slides from a presentation 'example2.pptx' existing as a local file.

###### **Request**
```
https://api.aspose.cloud/v3.0/slides/merge?outPath=merge_result.pptx
```

{{< expand-list title="Request body:" >}}
**JSON**
```
{
   "Presentations": [
      {
         "Path":"TestData/example1.pptx",
         "Password":"******",
         "Slides":[],
         "Source":"Storage"
      },
      {
         "Path":"second",
         "Password":null,
         "Slides":[2,4],
         "Source":"Request"
      }
   ]
}
```
{{< /expand-list >}}

{{< expand-list title="Response:" >}}
**JSON**
```
{
    "DocumentProperties": {
        "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/documentProperties",
        "Relation": "self",
        "LinkType": null,
        "Title": null
    },
    "ViewProperties": {
        "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/viewProperties",
        "Relation": "self",
        "LinkType": null,
        "Title": null
    },
    "Slides": {
        "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/slides",
        "Relation": "self",
        "LinkType": null,
        "Title": null
    },
    "Images": {
        "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/images",
        "Relation": "self",
        "LinkType": null,
        "Title": null
    },
    "LayoutSlides": {
        "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/layoutSlides",
        "Relation": "self",
        "LinkType": null,
        "Title": null
    },
    "MasterSlides": {
        "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/masterSlides",
        "Relation": "self",
        "LinkType": null,
        "Title": null
    },
    "SelfUri": {
        "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx",
        "Relation": "self",
        "LinkType": null,
        "Title": null
    },
    "AlternateLinks": [
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/odp",
            "Relation": "alternate",
            "LinkType": "application/vnd.oasis.opendocument.presentation",
            "Title": "Download as Odp"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/fodp",
            "Relation": "alternate",
            "LinkType": "application/vnd.oasis.opendocument.presentation",
            "Title": "Download as Fodp"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/ppt",
            "Relation": "alternate",
            "LinkType": "application/vnd.ms-powerpoint",
            "Title": "Download as Ppt"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/pdf",
            "Relation": "alternate",
            "LinkType": "application/pdf",
            "Title": "Download as Pdf"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/tiff",
            "Relation": "alternate",
            "LinkType": "image/tiff",
            "Title": "Download as Tiff"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/xps",
            "Relation": "alternate",
            "LinkType": "application/vnd.ms-xpsdocument",
            "Title": "Download as Xps"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/pps",
            "Relation": "alternate",
            "LinkType": "application/vnd.ms-powerpoint",
            "Title": "Download as Pps"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/ppsx",
            "Relation": "alternate",
            "LinkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "Title": "Download as Ppsx"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/pptm",
            "Relation": "alternate",
            "LinkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "Title": "Download as Pptm"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/ppsm",
            "Relation": "alternate",
            "LinkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "Title": "Download as Ppsm"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/pot",
            "Relation": "alternate",
            "LinkType": "application/vnd.ms-powerpoint",
            "Title": "Download as Pot"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/potx",
            "Relation": "alternate",
            "LinkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
            "Title": "Download as Potx"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/potm",
            "Relation": "alternate",
            "LinkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
            "Title": "Download as Potm"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/otp",
            "Relation": "alternate",
            "LinkType": "application/vnd.oasis.opendocument.presentation-template",
            "Title": "Download as Otp"
        },
        {
            "Href": "https://api.aspose.cloud/v3.0/slides/mergeResult.pptx/html",
            "Relation": "alternate",
            "LinkType": "text/html",
            "Title": "Download as Html"
        }
    ]
}
```
{{< /expand-list >}}

###### **.Net SDK Code:**

```csharp
var slidesApi = new SlidesApi(config);

// a presentation existing in a storage
var presentation1 = new PresentationToMerge
{
    Path = "TestData/example1.pptx",
    Password = "my_password",
    Source = PresentationToMerge.SourceEnum.Storage
};

// a presentation existing as a local file
var presentation2 = new PresentationToMerge
{
    Path = "second",
    Slides = new List<int> { 2, 4 },
    Source = PresentationToMerge.SourceEnum.Request
};

var file2 = new FileInfo
{
    Content = File.OpenRead("example2.pptx"),
    Name = "second"
};

var files = new List<FileInfo> { file2 };

OrderedMergeRequest mergeRequest = new OrderedMergeRequest
{
    Presentations = new List<PresentationToMerge> { presentation1, presentation2 }
};

// merge and save to the storage
slidesApi.MergeAndSaveOnline("merge_result.pptx", files, mergeRequest);
```

#### **HTTP DELETE**
Not supported.


## **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Auth Header**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl -v "http://api.aspose.cloud/v1.1/slides/sample.pptx/merge" -d '{"PresentationPaths": ["merge1.pptx","merge2.pptx"]}' -X POST -H "Content-Type: application/json" -H "Accept: application/json"-H "Accept:application/json" -H "Authorization: Bearer -Ou_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw_c8cAuk3qoag3g7bghMHw_pe_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR_hOD8Doqk5SBi_j-efODJK_PmGUxj0onOrUUx8Tj_GuUKrG6DcBnpl84_UykdOP87IeHnT2_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS_q3lthTDRMg2LuZ6s0r9MKlwVJ_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "Document":{
      "DocumentProperties":{
         "Uri":{
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/documentProperties",
            "Relation":"self",
            "LinkType":null,
            "Title":null
         }
      },
      "Slides":{
         "Uri":{
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/slides",
            "Relation":"self",
            "LinkType":null,
            "Title":null
         }
      },
      "Images":{
         "Uri":{
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/images",
            "Relation":"self",
            "LinkType":null,
            "Title":null
         }
      },
      "LayoutSlides":{
         "Uri":{
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/layoutSlides",
            "Relation":"self",
            "LinkType":null,
            "Title":null
         }
      },
      "MasterSlides":{
         "Uri":{
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/masterSlides",
            "Relation":"self",
            "LinkType":null,
            "Title":null
         }
      },
      "SelfUri":{
         "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx",
         "Relation":"self",
         "LinkType":null,
         "Title":null
      },
      "AlternateLinks":[
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=odp",
            "Relation":"alternate",
            "LinkType":"application/vnd.oasis.opendocument.presentation",
            "Title":"Download as Odp"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppt",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint",
            "Title":"Download as Ppt"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pdf",
            "Relation":"alternate",
            "LinkType":"application/pdf",
            "Title":"Download as Pdf"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=tiff",
            "Relation":"alternate",
            "LinkType":"image/tiff",
            "Title":"Download as Tiff"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=xps",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-xpsdocument",
            "Title":"Download as Xps"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pps",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint",
            "Title":"Download as Pps"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppsx",
            "Relation":"alternate",
            "LinkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "Title":"Download as Ppsx"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pptm",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "Title":"Download as Pptm"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppsm",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "Title":"Download as Ppsm"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=potx",
            "Relation":"alternate",
            "LinkType":"application/vnd.openxmlformats-officedocument.presentationml.template",
            "Title":"Download as Potx"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=potm",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",
            "Title":"Download as Potm"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=html",
            "Relation":"alternate",
            "LinkType":"text/html",
            "Title":"Download as Html"
         }
      ],
      "Links":[
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx",
            "Relation":"self",
            "LinkType":null,
            "Title":null
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=odp",
            "Relation":"alternate",
            "LinkType":"application/vnd.oasis.opendocument.presentation",
            "Title":"Download as Odp"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppt",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint",
            "Title":"Download as Ppt"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pdf",
            "Relation":"alternate",
            "LinkType":"application/pdf",
            "Title":"Download as Pdf"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=tiff",
            "Relation":"alternate",
            "LinkType":"image/tiff",
            "Title":"Download as Tiff"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=xps",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-xpsdocument",
            "Title":"Download as Xps"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pps",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint",
            "Title":"Download as Pps"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppsx",
            "Relation":"alternate",
            "LinkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "Title":"Download as Ppsx"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=pptm",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "Title":"Download as Pptm"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=ppsm",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "Title":"Download as Ppsm"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=potx",
            "Relation":"alternate",
            "LinkType":"application/vnd.openxmlformats-officedocument.presentationml.template",
            "Title":"Download as Potx"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=potm",
            "Relation":"alternate",
            "LinkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",
            "Title":"Download as Potm"
         },
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx?format=html",
            "Relation":"alternate",
            "LinkType":"text/html",
            "Title":"Download\* Connection #0 to host api.aspose.cloud left intact as Html"
         }
      ]
   },
   "Code":200,
   "Status":"OK"
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.


### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "MergePresentations.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "MergePresentations.java" >}}

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
      $fileName2 = "test-unprotected2.ppt";

      $inputFolder = realpath(__DIR__ . '/../..') . '\resources\\';

      // Upload original documents to storage
      $fileStream = fopen($inputFolder . $fileName, 'r');
      $slidesApi->uploadFile($fileName,  $fileStream, CommonUtils::$MyStorage);

      $fileStream2 = fopen($inputFolder . $fileName2, 'r');
      $slidesApi->uploadFile($fileName2,  $fileStream2, CommonUtils::$MyStorage);
      
      $mergeList = new Model\PresentationsMergeRequest();
      $mergeList->setPresentationPaths(array($fileName, $fileName2));

      $request = new Requests\PostPresentationMergeRequest($fileName, $mergeList);
      $result = $slidesApi->postPresentationMerge($request);
      print_r($result);

   } catch (Exception $e) {
      echo "Something went wrong: ", $e->getMessage(), "\n";
   }
?>
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "MergePresentations.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "MergePresentations.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "MergePresentations.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "MergePresentations.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
