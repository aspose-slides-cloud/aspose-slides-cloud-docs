---
title: "Merging Presentations from Local Files and Storage into a Local File"
type: docs
url: /merging-presentations-from-local-files-and-storage-into-a-local-file/
weight: 30
---

## **Introduction**

The article shows you how to merge PowerPoint presentations saved in local files and a storage. The final presentation will be received as a local file. You can specify slide indices to merge presentations in parts. Passwords can be specified to open protected presentations. The request method below allows you to merge presentation files stored both locally and in storage, separately or together.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/merge|POST|Merges presentations or some of their slides. Returns the result file in the response.|[MergeOnline](https://apireference.aspose.cloud/slides/#/MergeDocument/MergeOnline)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|files|array|formData|false|The array of presentation files to merge.|
|request|object|body|false|The information about presentations to merge (paths, passwords, slide indices, etc.).|
|storage|string|query|false|The name of the storage where the presentations specified in the `request` parameter were saved.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

