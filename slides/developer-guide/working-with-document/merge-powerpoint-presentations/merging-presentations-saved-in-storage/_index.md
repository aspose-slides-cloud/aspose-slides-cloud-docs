---
title: "Merging Presentations Saved in Storage"
type: docs
url: /merging-presentations-saved-in-storage/
weight: 10
---

## **Introduction**

The article shows you how to merge PowerPoint presentations saved in a storage. To merge protected presentations, passwords can be specified to open them.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/merge|POST|Merges a presentation with other presentations saved in a storage.|[Merge](https://apireference.aspose.cloud/slides/#/MergeDocument/Merge)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the initial presentation into which other presentations are merged.|
|request|object|body|true|The information about presentations to merge (paths, passwords).|
|password|string|header|false|The password to open the initial presentation.|
|folder|string|query|false|The storage folder path where the initial presentation was saved.|
|storage|string|query|false|The storage name where the initial presentation was saved.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

