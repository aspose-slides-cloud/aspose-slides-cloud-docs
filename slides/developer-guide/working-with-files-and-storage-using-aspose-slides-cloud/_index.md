---
title: "Working with Files and Storage using Aspose.Slides Cloud"
type: docs
url: /working-with-files-and-storage-using-aspose-slides-cloud/
weight: 120
---

## **Introduction**
Aspose.Slides Cloud provides helper functions to work with files uploaded to Aspose Cloud Storage or any other Cloud Storage of your choice. If you need any help getting started with setting third party storage please refer to [Aspose Cloud UI Help Topics](https://docs.aspose.cloud/display/totalcloud/Aspose+Cloud+UI+Help+Topics).

**Request Access Token**

The cURL examples below use **<access_token>** template string instead of an actual token string. You can receive the access token by your `client_id` and `client_secret` as shown below. Then you can use your access token in the code examples.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl -v -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
  "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE2NDUwMDcwMjQsImV4cCI6MTY0NTAxMDYyNCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkuYmlsbGluZyIsImFwaS5pZGVudGl0eSIsImFwaS5wcm9kdWN0cyIsImFwaS5zdG9yYWdlIl0sImNsaWVudF9pZCI6ImM1MTQwZDVhLTlhZDItNDRjZS1iOGNmLTcyMWZkNDBhNDk0OSIsImNsaWVudF9kZWZhdWx0X3N0b3JhZ2UiOiI1MzI2ZjMwNC1jOWZjLTQyYzktOGIxYy04NzAwZjQ0YmEwNTMiLCJjbGllbnRfaWRlbnRpdHlfdXNlcl9pZCI6Ijc5MTMzOCIsInNjb3BlIjpbImFwaS5iaWxsaW5nIiwiYXBpLmlkZW50aXR5IiwiYXBpLnByb2R1Y3RzIiwiYXBpLnN0b3JhZ2UiXX0.gqEhtex3zjYWknT4JVehzne70X1gJ0X-8UJqy41AolrVLvdk5sffqFnjCcGXUibVCNmwkxUC1l9-A4nn9gGsTAB7hw85aI8_yknEw4oVxou64-jpff0lXFqdq37iioZczhn4NO4kByTjnSrW_D_UOM70R_v4KUfCYNWUSQUqEQFcyI-Pl-yHqMKDF2BOYq4Stfx5yGX41i6EMW_p3zveFlqrHLyGQebOiAR_mSXwc3vnNgtum1VatCirvhDFei3Hjs7VVyrI0SGpWKRUsnEpTfxQ6ULmeo2GUZhBmkF_TPEmHuFG3E_w0rmC4rsxerpfvuGhDaxwPcvk-FmzLJaTAA",
  "expires_in": 3600,
  "token_type": "Bearer"
}
```

{{< /tab >}}

{{< /tabs >}}

## **Download a file from Cloud Storage**

### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/storage/file/{path}|GET|Downloads a file from a Cloud storage.|[DownloadFile](https://apireference.aspose.cloud/slides/#/File/DownloadFile)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The file path in a storage.|
|storageName|string|query|false|The storage name.|
|versionId|string|query|false|The file version ID.|

### **cURL Example**
Download a file **Data/example.pptx** from a storage **Main** and save the file to **result.pptx**. 

{{< tabs tabTotal="1" tabID="2" tabName1="Request" >}}

{{< tab tabNum="1" >}}

```java
curl -v -X GET "https://api.aspose.cloud/v3.0/slides/storage/file/Data/example.pptx?storageName=Main" -H "accept: multipart/form-data" -o result.pptx -H "Authorization: Bearer <access_token>" --ssl-no-revoke
```

{{< /tab >}}

{{< /tabs >}}

## **Uploading a file to Cloud Storage**

### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/storage/file/{path}|PUT|Uploads a file to a Cloud storage.|[UploadFile](https://apireference.aspose.cloud/slides/#/File/UploadFile)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The file path in a storage. If the content is multipart and the path does not contains the file name, it tries to get them from `filename` parameter from the Content-Disposition header.|
|file|file|formData|true|The file to upload.|
|storageName|string|query|false|The storage name.|

### **cURL Example**
Upload a file **example.pptx** to the path **Data/result.pptx** on a storage **Main**.

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/Data/result.pptx?storageName=Main"  -H "Content-Type:application/octet-stream" --data-binary @example.pptx -H "Authorization: Bearer <access_token>" --ssl-no-revoke
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "uploaded":[
      "presentation_images_1.pptx"
   ],
   "errors":[
   ]
}
```

{{< /tab >}}

{{< /tabs >}}

## **Copying a file to a new location on Cloud Storage**

### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/storage/file/copy/{srcPath}|PUT|Duplicates a file to a new location on a Cloud storage.|[CopyFile](https://apireference.aspose.cloud/slides/#/File/CopyFile)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|srcPath|string|path|true|The source file path.|
|destPath|string|query|true|The destination file path.|
|srcStorageName|string|query|false|The source storage name.|
|destStorageName|string|query|false|The destination storage name.|
|versionId|string|query|false|The version ID of the file to copy.|

### **cURL Example**
Copy a file **Data/example.pptx** to the path **Resources/example_copy.pptx** on a storage **Main**.

{{< tabs tabTotal="1" tabID="4" tabName1="Request" >}}

{{< tab tabNum="1" >}}

```java
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/copy/Data/example.pptx?destPath=Resources/example_copy.pptx&srcStorageName=Main&destStorageName=Main" -H "Content-Type:application/json" -H "Authorization: Bearer <access_token>"  -d {} --ssl-no-revoke
```

{{< /tab >}}

{{< /tabs >}}

## **Moving a file to a new location on Cloud Storage**

### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/storage/file/move/{srcPath}|PUT|Moves a file to a new location on a Cloud storage.|[MoveFile](https://apireference.aspose.cloud/slides/#/File/MoveFile)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|srcPath|string|path|true|The source file path.|
|destPath|string|query|true|The destination file path.|
|srcStorageName|string|query|false|The source storage name.|
|destStorageName|string|query|false|The destination storage name.|
|versionId|string|query|false|The version ID of the file to move.|

### **cURL Example**
Move a file **Data/example.pptx** to the path **Resources/example.pptx** on a storage **Main**.

{{< tabs tabTotal="1" tabID="5" tabName1="Request" >}}

{{< tab tabNum="1" >}}

```java
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/move/Data/example.pptx?destPath=Resources/example.pptx&srcStorageName=Main&destStorageName=Main" -H "Content-Type:application/json" -H "Authorization: Bearer <access_token>"  -d {} --ssl-no-revoke
```

{{< /tab >}}

{{< /tabs >}}

## **Deleting a file on Cloud Storage**

### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/storage/file/{path}|DELETE|Deletes a file from a Cloud storage.|[DeleteFile](https://apireference.aspose.cloud/slides/#/File/DeleteFile)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The file path.|
|storageName|string|query|false|The storage name.|
|versionId|string|query|false|The version ID of the file to delete.|

### **cURL Example**
Delete a file **Resources/example.pptx** on a storage **Main**.

{{< tabs tabTotal="1" tabID="6" tabName1="Request" >}}

{{< tab tabNum="1" >}}

```java
curl -v -X DELETE "https://api.aspose.cloud/v3.0/slides/storage/file/Resources/example.pptx?storageName=Main" -H "Content-Type:application/json" -H "Authorization: Bearer <access_token>" -d {} --ssl-no-revoke
```

{{< /tab >}}

{{< /tabs >}}
