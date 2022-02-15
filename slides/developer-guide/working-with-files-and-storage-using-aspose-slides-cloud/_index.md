---
title: "Working with Files and Storage using Aspose.Slides Cloud"
type: docs
url: /working-with-files-and-storage-using-aspose-slides-cloud/
weight: 120
---

## **Introduction**
Aspose.Slides Cloud provides helper functions to work with files uploaded to Aspose Cloud Storage or any other Cloud Storage of your choice. If you need any help getting started with setting third party storage please refer to [Aspose Cloud UI Help Topics](https://docs.aspose.cloud/display/totalcloud/Aspose+Cloud+UI+Help+Topics).

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

{{< tabs tabTotal="1" tabID="1" tabName1="Request" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```java
curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/storage/file/presentation_images.pptx" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwOTI3OTcsImV4cCI6MTU2MDE3OTE5NywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.rFS4KehYAg1yOVGmteeinIh-AFq7nVEmtUr_cDltIfk0iN0JJJ3o6TK1StpnItAAqlkb_QtF0WcY5D8NCjeyTVKL1oewdIshjjODoPEN1tmCsRXceHGYTG5f--B8sWrMuZtOqSzlbr-x3_Mat9Fy7xcNbS6nNNmBv7mo3suRDF4xdUZWdIY7bO6yBptc-qyhIFb0olNMxdeAZPsN8sPLW0XIbEGf8CaE16p9al_O5SjWLtEZT7APuvDesJwWYOSPtG6hCsXtHItphKDAcMULEnqJ-QW_QpzBxybTnQ1VNzundQWOYM_viYzU8hOlf6VTE4YQKyCmgz72Ena8KZx0VA" --ssl-no-revoke
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

{{< tabs tabTotal="2" tabID="4" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```java
curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/presentation_images_1.pptx" "Content-Type:application/octet-stream" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwOTI3OTcsImV4cCI6MTU2MDE3OTE5NywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.rFS4KehYAg1yOVGmteeinIh-AFq7nVEmtUr_cDltIfk0iN0JJJ3o6TK1StpnItAAqlkb_QtF0WcY5D8NCjeyTVKL1oewdIshjjODoPEN1tmCsRXceHGYTG5f--B8sWrMuZtOqSzlbr-x3_Mat9Fy7xcNbS6nNNmBv7mo3suRDF4xdUZWdIY7bO6yBptc-qyhIFb0olNMxdeAZPsN8sPLW0XIbEGf8CaE16p9al_O5SjWLtEZT7APuvDesJwWYOSPtG6hCsXtHItphKDAcMULEnqJ-QW_QpzBxybTnQ1VNzundQWOYM_viYzU8hOlf6VTE4YQKyCmgz72Ena8KZx0VA" --ssl-no-revoke --data-binary @destination.pptx
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

{{< tabs tabTotal="1" tabID="8" tabName1="Request" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```java
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/copy/presentation_images.pptx?destPath=cp.pptx" -H "Content-Type:application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAxMDY1MDcsImV4cCI6MTU2MDE5MjkwNywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.FeU2K-qTf4meenSv1IQZqUpSPQREk0MmYK5oMMRx2t_LqELHMRnBawHC8nJ5DzGKsK_xyZwPpIANRA8eWHPoPICMoZnDZtUbLagxvSbFMZPReV2Ip3sVTTSvQXA-UOaLC6BbWnyHWDAbAGPv92AFMu_A0wiEBVs68vx_ZOOhjhZkX1rKfJFbJjWr8tJC9HVkEGubfiqXAb6ejL2ISwWcvUr49napuPPVrejJkAbj27z1oGSjmzYvoUuN4tP8Tb2VwD6L4B_Q99EOAs0y4VownW1BE3Ku_rKUgGAOa7OKZKtzOgKrtWqSc9oQ9h0DuiIkmKhn5I_PczHwigZ-ytb3OQ" --ssl-no-revoke -d {}
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

{{< tabs tabTotal="1" tabID="11" tabName1="Request" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```java
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/move/cp.pptx?destPath=mv_result.pptx" -H "Content-Type:application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAxMDY1MDcsImV4cCI6MTU2MDE5MjkwNywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.FeU2K-qTf4meenSv1IQZqUpSPQREk0MmYK5oMMRx2t_LqELHMRnBawHC8nJ5DzGKsK_xyZwPpIANRA8eWHPoPICMoZnDZtUbLagxvSbFMZPReV2Ip3sVTTSvQXA-UOaLC6BbWnyHWDAbAGPv92AFMu_A0wiEBVs68vx_ZOOhjhZkX1rKfJFbJjWr8tJC9HVkEGubfiqXAb6ejL2ISwWcvUr49napuPPVrejJkAbj27z1oGSjmzYvoUuN4tP8Tb2VwD6L4B_Q99EOAs0y4VownW1BE3Ku_rKUgGAOa7OKZKtzOgKrtWqSc9oQ9h0DuiIkmKhn5I_PczHwigZ-ytb3OQ" --ssl-no-revoke -d {}
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

{{< tabs tabTotal="1" tabID="14" tabName1="Request" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```java
curl -v -X DELETE "https://api.aspose.cloud/v3.0/slides/storage/file/mv.pptx" -H "Content-Type:application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAxMDY1MDcsImV4cCI6MTU2MDE5MjkwNywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.FeU2K-qTf4meenSv1IQZqUpSPQREk0MmYK5oMMRx2t_LqELHMRnBawHC8nJ5DzGKsK_xyZwPpIANRA8eWHPoPICMoZnDZtUbLagxvSbFMZPReV2Ip3sVTTSvQXA-UOaLC6BbWnyHWDAbAGPv92AFMu_A0wiEBVs68vx_ZOOhjhZkX1rKfJFbJjWr8tJC9HVkEGubfiqXAb6ejL2ISwWcvUr49napuPPVrejJkAbj27z1oGSjmzYvoUuN4tP8Tb2VwD6L4B_Q99EOAs0y4VownW1BE3Ku_rKUgGAOa7OKZKtzOgKrtWqSc9oQ9h0DuiIkmKhn5I_PczHwigZ-ytb3OQ" --ssl-no-revoke -d {}
```

{{< /tab >}}

{{< /tabs >}}
