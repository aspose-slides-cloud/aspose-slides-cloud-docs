---
title: "Merging Presentations from Local Files and Storage into a File in Storage"
type: docs
url: /merging-presentations-from-local-files-and-storage-into-a-file-in-storage/
weight: 40
---

## **Introduction**

The article shows you how to merge PowerPoint presentations saved in local files and a storage. The final presentation is also saved in the storage. You can specify slide indices to merge. For protected presentations, passwords can be specified to open them. The request method below allows you to merge presentation files stored both locally and in storage, separately or together.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/merge|PUT|Merges presentations or some of their slides. Saves the result in the storage.|[MergeAndSaveOnline](https://apireference.aspose.cloud/slides/#/MergeDocument/MergeAndSaveOnline)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|files|array|formData|false|The array of presentation files to merge.|
|outPath|string|query|true|The path to the presentation output file in a storage.|
|request|object|body|false|The information about presentations to merge (paths, passwords, slide indices, etc.).|
|storage|string|query|false|The name of the storage where the final presentation will be saved.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

