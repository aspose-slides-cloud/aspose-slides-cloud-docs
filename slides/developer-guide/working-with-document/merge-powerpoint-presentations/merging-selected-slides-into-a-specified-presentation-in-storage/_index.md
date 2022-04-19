---
title: "Merging Selected Slides into a Specified Presentation in Storage"
type: docs
url: /merging-selected-slides-into-a-specified-presentation-in-storage/
weight: 20
---

## **Introduction**

The article shows you how to merge PowerPoint presentations saved in a storage. You can specify slide indices to merge. For protected presentations, passwords can be specified.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/merge|PUT|Merges a presentation with other presentations or some of their slides.|[OrderedMerge](https://apireference.aspose.cloud/slides/#/MergeDocument/OrderedMerge)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the initial presentation into which other presentations are merged.|
|request|object|body|true|The information about presentations to merge (paths, passwords, slide indices, etc.).|
|password|string|header|false|The password to open the initial presentation.|
|folder|string|query|false|The storage folder path where the initial presentation was saved.|
|storage|string|query|false|The storage name where the initial presentation was saved.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

