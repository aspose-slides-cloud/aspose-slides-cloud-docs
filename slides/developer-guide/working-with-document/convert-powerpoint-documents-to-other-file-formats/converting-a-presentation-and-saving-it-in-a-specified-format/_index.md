---
title: "Converting a Presentation and Saving It in a Specified Format"
type: docs
url: /converting-a-presentation-and-saving-it-in-a-specified-format/
weight: 20
---

## **Introduction**

The following method allows you to transfer a PowerPoint presentation from a local file to a Cloud Storage, convert the presentation to a desired format and save the result in the storage. In addition, you can also specify a folder in the storage containing external fonts that can be used in the presentation, and other options.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/convert/{format}|PUT|Converts a passed presentation to a specified format and saves the result to the Cloud Storage.|[ConvertAndSave](https://apireference.aspose.cloud/slides/#/Document/ConvertAndSave)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The data of the presentation.|
|format|string|path|true|The desired format for the conversion.|
|outPath|string|query|true|The output file path to save the result in the storage.|
|password|string|header|false|The password to open the presentation.|
|storage|string|query|false|The name of the storage where the result will be located.|
|fontsFolder|string|query|false|The path to the storage folder containing the external fonts.|
|slides|string|query|false|The 1-based indices of the slides to be converted. If it is not specified, all slides are converted by default.|
|options|object|body|false|The format-specific options for the conversion.|

{{% alert color="primary" %}} 
If the presentation is converted to images (for example, PNG, JPG, etc.), then the result will be a ZIP archive, and the `.zip` extension will be added to the output file name.
{{% /alert %}} 

## **cURL Examples**

Convert **example.pptx** presentation from a local file to PNG images and save the result to **MyFolder/images.zip** file in **MyStorage** storage.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/convert/Png?outPath=MyFolder/images&storage=MyStorage" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/octet-stream" \
     --data-binary @example.pptx
```

{{< /tab >}}

{{< tab tabNum="2" >}}

no data

{{< /tab >}}

{{< /tabs >}}
