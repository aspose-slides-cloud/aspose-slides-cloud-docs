---
title: "Saving a Presentation in a Specified Format"
type: docs
url: /saving-a-presentation-in-a-specified-format/
weight: 40
---

## **Introduction**

The following method allows you to covert a PowerPoint presentation located in a Cloud Storage to a desired format and save the result to the storage. 

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/{format}|PUT|Converts a presentation located in a storage to a specified format and saves the result to the storage.|[SavePresentation](https://apireference.aspose.cloud/slides/#/Document/SavePresentation)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the presentation.|
|format|string|path|true|The desired format for the conversion.|
|outPath|string|query|true|The output file path to save the result in the storage.|
|options|object|body|false|The format-specific options for the conversion.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder path where the presentation is located.|
|storage|string|query|false|The name of the storage where the presentation is located.|
|fontsFolder|string|query|false|The path to the storage folder containing external fonts.|
|slides|string|query|false|The 1-based indices of the slides to be saved. If it is not specified, all slides are saved by default.|

To use **fontsFolder** parameter, you can create storage folders and upload font files to them using Slides Cloud API.

{{% alert color="primary" %}}

If the slides of the presentation are converted to separate images (for example, PNG, JPG, etc.), the result will be a ZIP archive, and the `.zip` extension will be added to the output file name.

{{% /alert %}}
