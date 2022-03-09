---
title: "Passing a Presentation to Storage and Obtaining It in a Specified Format"
type: docs
url: /passing-a-presentation-to-storage-and-obtaining-it-in-a-specified-format/
weight: 10
---

## **Introduction**

The following method allows you to convert a PowerPoint presentation to a specified format by passing a local file. The result of the conversion will be obtained immediately for saving to a local file as well. In addition, you can also specify a folder in a storage containing external fonts that can be used in the presentation, and other options.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/convert/{format}|POST|Converts a passed presentation to a specified format and returns the result of the conversion.|[Convert](https://apireference.aspose.cloud/slides/#/Document/Convert)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The data of the presentation.|
|format|string|path|true|The desired format for the conversion.|
|password|string|header|false|The password to open the presentation.|
|storage|string|query|false|The name of a storage containing the external fonts.|
|fontsFolder|string|query|false|The path to a storage folder containing the external fonts.|
|slides|string|query|false|The 1-based indices of the slides to be converted. If not specified, all slides are converted by default.|
|options|data|body|false|The format-specific options for the conversion.|

To use **fontsFolder** parameter, you can create storage folders and upload font files to them using Slides Cloud API.

You can [convert parts of presentations](/slides/convert-selected-document-slides/) using the optional **slides** parameter.

You can specify [format-specific options](/slides/conversion-options/) using the **options** parameter.

## **cURL Examples**

Create **MyFonts** storage folder in **Main** storage, add **custom.ttf** font to the folder, convert **example.pptx** presentation to PDF format, and save the PDF document to **output.pdf** file.

{{< tabs tabTotal="2" tabID="1" tabName1="Requests" tabName2="Responses" >}}

{{< tab tabNum="1" >}}

**Creating the storage folder**
```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/folder/MyFonts?storageName=Main" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Length: 0"
```

**Adding the font to the folder**
```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/MyFonts/custom.ttf?storageName=Main" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/octet-stream" \
     --data-binary @custom.ttf
```

**Converting the presentation**
```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/convert/Pdf?storage=Main&fontsFolder=MyFonts" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/octet-stream" \
     --data-binary @example.pptx \
     -o output.pdf
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Creating the storage folder**
empty

**Adding the font to the folder**
```json
{
    "uploaded": [
        "custom.ttf"
    ],
    "errors": []
}
```

**Converting the presentation**
empty

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
