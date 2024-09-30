---
title: "Working with Files"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- cloud storage
- file storage
- upload file
- download file
- copy file
- move file
type: docs
url: /working-with-files/
weight: 30
---

## **Introduction**

Aspose.Slides Cloud API provides methods to work with files in Aspose Cloud Storage or any other Cloud storage of your choice. If you need any help setting up third-party storage, please refer to [Aspose Cloud UI Help Topics](https://docs.aspose.cloud/storage/aspose-cloud-ui-help-topics/).

**Request Access Token**

The cURL examples below use **<access_token>** template string instead of an actual token string. You can receive the access token by your `client_id` and `client_secret` as shown below. Then you can use your access token in the code examples.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" \
     -H "Content-Type: application/x-www-form-urlencoded" \
     -H "Accept: application/json"
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

## **DownloadFile**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/file/{path}|GET|Downloads a file from a Cloud storage.|[DownloadFile](https://reference.aspose.cloud/slides/#/File/DownloadFile)|
|/slides/async/storage/file/{path}|GET|Downloads a file from a Cloud storage.|[Download](https://reference.aspose.cloud/slides/#/File/Download)|

The two methods are totally identical; as the second is part of async API, it does not have file size restrictions.

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The path to a file in a storage.|
|storageName|string|query|false|The name of the storage.|
|versionId|string|query|false|The version ID of the file.|

### **Examples**

Download the **Data/example.pptx** file from the **MyStorage** storage and save it to **result.pptx**. 

**cURL Solution**

{{< tabs tabTotal="1" tabID="2" tabName1="Request" >}}

{{< tab tabNum="1" >}}
```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/storage/file/Data/example.pptx?storageName=MyStorage" \
     -H "Authorization: Bearer <access_token>" \
     -H "accept: multipart/form-data" \ 
     -o result.pptx
```
{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="9" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" >}}

{{< tab tabNum="1" >}}
```cs
using System;
using System.IO;
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string filePath = "Data/example.pptx";
        string resultPath = "result.pptx";

        using Stream fileStream = slidesApi.DownloadFile(filePath, storageName);

        using FileStream resultStream = File.OpenWrite(resultPath);
        fileStream.CopyTo(resultStream);
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```java
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

import java.io.File;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String filePath = "Data/example.pptx";
        String resultPath = "result.pptx";

        // Note: The file data will be stored to a temporary file.
        File file = slidesApi.downloadFile(filePath, storageName, null);

        Files.copy(file.toPath(), Paths.get(resultPath));
    }
}
```
{{< /tab >}}

{{< tab tabNum="3" >}}
```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "MyStorage";
$filePath = "Data/example.pptx";
$resultPath = "result.pptx";

// Note: The file data will be stored to a temporary file.
$file = $slidesApi->downloadFile($filePath, $storageName);

copy($file->getRealPath(), $resultPath);
```
{{< /tab >}}

{{< tab tabNum="4" >}}
```rb
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
file_path = "Data/example.pptx"
result_path = "result.pptx"

file_data = slides_api.download_file(file_path, storage_name)

File.binwrite(result_path, file_data)
```
{{< /tab >}}

{{< tab tabNum="5" >}}
```py
import asposeslidescloud
import shutil

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
file_path = "Data/example.pptx"
result_path = "result.pptx"

# Note: The file data will be stored to a temporary file.
temp_path = slides_api.download_file(file_path, storage_name)

shutil.copyfile(temp_path, result_path)
```
{{< /tab >}}

{{< tab tabNum="6" >}}
```js
const cloudSdk = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
filePath = "Data/example.pptx";
resultPath = "result.pptx";

slidesApi.downloadFile(filePath, storageName).then(fileData => {
    fs.writeFile(resultPath, fileData.body, error => {
    });
});
```
{{< /tab >}}

{{< tab tabNum="7" >}}
```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* storageName = L"MyStorage";
    const wchar_t* filePath = L"Data/example.pptx";
    const wchar_t* resultPath = L"result.pptx";

    HttpContent fileContent = slidesApi->downloadFile(filePath, storageName).get();

    std::ofstream resultStream(resultPath, std::ofstream::binary);
    fileContent.writeTo(resultStream);
}
```
{{< /tab >}}

{{< tab tabNum="8" >}}
```pl
use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_data = $slides_api->download_file(
    path => "Data/example.pptx", 
    storage_name => "MyStorage");

write_file("result.pptx", {binmode => ":raw"}, $file_data);
```
{{< /tab >}}

{{< tab tabNum="9" >}}
```go
import (
	"io"
	"os"

	asposeslidescloud "github.com/aspose-slides-cloud/aspose-slides-cloud-go/v24"
)

func main() {
	configuration := asposeslidescloud.NewConfiguration()
	configuration.AppSid = "MyClientId"
	configuration.AppKey = "MyClientSecret"

	slidesApi := asposeslidescloud.NewAPIClient(configuration).SlidesApi

	storageName := "MyStorage"
	filePath := "Data/example.pptx"
	resultPath := "result.pptx"

	// Note: The file data will be stored to a temporary file.
	file, _, _ := slidesApi.DownloadFile(filePath, storageName, "")

	source, _ := os.Open(file.Name())
	defer source.Close()

	destination, _ := os.Create(resultPath)
	defer destination.Close()

	io.Copy(destination, source)
}
```
{{< /tab >}}

{{< /tabs >}}

## **UploadFile**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/file/{path}|PUT|Uploads a file to a Cloud storage.|[UploadFile](https://reference.aspose.cloud/slides/#/File/UploadFile)|
|/slides/async/storage/file/{path}|PUT|Uploads a file to a Cloud storage.|[Upload](https://reference.aspose.cloud/slides/#/File/Upload)|

The two methods are totally identical; as the second is part of async API, it does not have file size restrictions.

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The path to a file in a storage. If the content is multipart and the path does not contains the file name, it tries to get them from the `filename` parameter from the Content-Disposition header.|
|file|file|formData|true|The file to be uploaded.|
|storageName|string|query|false|The name of the storage.|

### **Examples**

Upload the **example.pptx** file to the **Data/result.pptx** path in the **MyStorage** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/Data/result.pptx?storageName=MyStorage" \
     -H "Authorization: Bearer <access_token>" \
     -H "Content-Type:application/octet-stream" \
     --data-binary @example.pptx
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```json
{
   "uploaded":[
      "result.pptx"
   ],
   "errors":[
   ]
}
```
{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="9" tabID="33" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" >}}

{{< tab tabNum="1" >}}
```cs
using System;
using System.IO;
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string filePath = "example.pptx";
        string resultPath = "Data/result.pptx";

        using FileStream fileStream = File.OpenRead(filePath);
        FilesUploadResult uploadResult = slidesApi.UploadFile(resultPath, fileStream, storageName);

        int fileCount = uploadResult.Uploaded.Count;
        Console.WriteLine("Number of uploaded files: " + fileCount); // 1
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.FilesUploadResult;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String filePath = "example.pptx";
        String resultPath = "Data/result.pptx";

        byte[] fileData = Files.readAllBytes(Paths.get(filePath));
        FilesUploadResult uploadResult = slidesApi.uploadFile(resultPath, fileData, storageName);

        int fileCount = uploadResult.getUploaded().size();
        System.out.println("Number of uploaded files: " + fileCount); // 1
    }
}
```
{{< /tab >}}

{{< tab tabNum="3" >}}
```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "MyStorage";
$filePath = "example.pptx";
$resultPath = "Data/result.pptx";

$fileStream = fopen($filePath, "r");
$uploadResult = $slidesApi->uploadFile($resultPath, $fileStream, $storageName);

$fileCount = count($uploadResult->getUploaded());
print("Number of uploaded files: " . $fileCount); // 1
```
{{< /tab >}}

{{< tab tabNum="4" >}}
```rb
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
file_path = "example.pptx"
result_path = "Data/result.pptx"

file_data = File.binread(file_path)
upload_result = slides_api.upload_file(result_path, file_data, storage_name)

file_count = upload_result.uploaded.length()
puts "Number of uploaded files: #{file_count}" # 1
```
{{< /tab >}}

{{< tab tabNum="5" >}}
```py
from asposeslidescloud.apis import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
file_path = "example.pptx"
result_path = "Data/result.pptx"

with open(file_path, "rb") as file_stream:
    upload_result = slides_api.upload_file(result_path, file_stream, storage_name)

file_count = len(upload_result.uploaded)
print("Number of uploaded files:", file_count)  # 1
```
{{< /tab >}}

{{< tab tabNum="6" >}}
```js
const fs = require("fs");
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
filePath = "example.pptx";
resultPath = "Data/result.pptx";

fileStream = fs.createReadStream(filePath);

slidesApi.uploadFile(resultPath, fileStream, storageName).then(uploadResult => {
    fileCount = uploadResult.body.uploaded.length;
    console.log("Number of uploaded files:", fileCount); // 1
});
```
{{< /tab >}}

{{< tab tabNum="7" >}}
```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

	const wchar_t* storageName = L"MyStorage";
	const wchar_t* filePath = L"example.pptx";
	const wchar_t* resultPath = L"Data/result.pptx";

	std::shared_ptr<std::ifstream> fileStream = std::make_shared<std::ifstream>(filePath, std::ios::binary);
	std::shared_ptr<HttpContent> uploadContent = std::make_shared<HttpContent>();
	uploadContent->setData(fileStream);

	std::shared_ptr<FilesUploadResult> uploadResult = slidesApi->uploadFile(resultPath, uploadContent, storageName).get();

	int fileCount = uploadResult->getUploaded().size();
	std::wcout << L"Number of uploaded files: " << fileCount; // 1
}
```
{{< /tab >}}

{{< tab tabNum="8" >}}
```pl
use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_data = read_file("example.pptx", { binmode => ":raw" });

my $upload_result = $slides_api->upload_file(
    path => "Data/result.pptx",
    file => $file_data,
    storage_name => "MyStorage");

my $file_count = @{$upload_result->{uploaded}};
print "Number of uploaded files: ", $file_count; # 1
```
{{< /tab >}}

{{< tab tabNum="9" >}}
```go
import (
	"fmt"
	"os"

	asposeslidescloud "github.com/aspose-slides-cloud/aspose-slides-cloud-go/v24"
)

func main() {
	configuration := asposeslidescloud.NewConfiguration()
	configuration.AppSid = "MyClientId"
	configuration.AppKey = "MyClientSecret"

	slidesApi := asposeslidescloud.NewAPIClient(configuration).SlidesApi

	storageName := "MyStorage"
	filePath := "example.pptx"
	resultPath := "Data/result.pptx"

	fileData, _ := os.ReadFile(filePath)
	uploadResult, _, _ := slidesApi.UploadFile(resultPath, fileData, storageName)

	fileCount := len(uploadResult.GetUploaded())
	fmt.Println("Number of uploaded files:", fileCount) // 1
}
```
{{< /tab >}}

{{< /tabs >}}

## **CopyFile**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/file/copy/{srcPath}|PUT|Copies a file in a Cloud storage.|[CopyFile](https://reference.aspose.cloud/slides/#/File/CopyFile)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|srcPath|string|path|true|The path to a source file.|
|destPath|string|query|true|The path to a destination file.|
|srcStorageName|string|query|false|The name of a source storage.|
|destStorageName|string|query|false|The name of a destination storage.|
|versionId|string|query|false|The version ID of the file to be copied.|

### **Examples**

Copy the **Data/example.pptx** file to the **Resources/example_copy.pptx** path in the **MyStorage** storage.

**cURL Solution**

{{< tabs tabTotal="1" tabID="4" tabName1="Request" >}}

{{< tab tabNum="1" >}}
```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/copy/Data%2Fexample.pptx?destPath=Resources%2Fexample_copy.pptx&srcStorageName=MyStorage&destStorageName=MyStorage" 
     -H "Authorization: Bearer <access_token>"
```
{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="9" tabID="44" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" >}}

{{< tab tabNum="1" >}}
```cs
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string sourcePath = "Data/example.pptx";
        string targetPath = "Resources/example_copy.pptx";

        slidesApi.CopyFile(sourcePath, targetPath, storageName, storageName);
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```java
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String sourcePath = "Data/example.pptx";
        String targetPath = "Resources/example_copy.pptx";

        slidesApi.copyFile(sourcePath, targetPath, storageName, storageName, null);
    }
}
```
{{< /tab >}}

{{< tab tabNum="3" >}}
```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "MyStorage";
$sourcePath = "Data/example.pptx";
$targetPath = "Resources/example_copy.pptx";

$slidesApi->copyFile($sourcePath, $targetPath, $storageName, $storageName);
```
{{< /tab >}}

{{< tab tabNum="4" >}}
```rb
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
source_path = "Data/example.pptx"
target_path = "Resources/example_copy.pptx"

slides_api.copy_file(source_path, target_path, storage_name, storage_name)
```
{{< /tab >}}

{{< tab tabNum="5" >}}
```py
import asposeslidescloud

from asposeslidescloud.apis import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
source_path = "Data/example.pptx"
target_path = "Resources/example_copy.pptx"

slides_api.copy_file(source_path, target_path, storage_name, storage_name)
```
{{< /tab >}}

{{< tab tabNum="6" >}}
```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
sourcePath = "Data/example.pptx";
targetPath = "Resources/example_copy.pptx";

slidesApi.copyFile(sourcePath, targetPath, storageName, storageName).then(() => {
});
```
{{< /tab >}}

{{< tab tabNum="7" >}}
```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

	const wchar_t* storageName = L"MyStorage";
	const wchar_t* sourcePath = L"Data/example.pptx";
	const wchar_t* targetPath = L"Resources/example_copy.pptx";

	slidesApi->copyFile(sourcePath, targetPath, storageName, storageName);
}
```
{{< /tab >}}

{{< tab tabNum="8" >}}
```pl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

$slides_api->copy_file(
    src_path => "Data/example.pptx",
    dest_path => "Resources/example_copy.pptx",
    src_storage_name => "MyStorage",
    dest_storage_name => "MyStorage");
```
{{< /tab >}}

{{< tab tabNum="9" >}}
```go
import (
	asposeslidescloud "github.com/aspose-slides-cloud/aspose-slides-cloud-go/v24"
)

func main() {
	configuration := asposeslidescloud.NewConfiguration()
	configuration.AppSid = "MyClientId"
	configuration.AppKey = "MyClientSecret"

	slidesApi := asposeslidescloud.NewAPIClient(configuration).SlidesApi

	storageName := "MyStorage"
	sourcePath := "Data/example.pptx"
	targetPath := "Resources/example_copy.pptx"

	slidesApi.CopyFile(sourcePath, targetPath, storageName, storageName, "")
}
```
{{< /tab >}}

{{< /tabs >}}

## **MoveFile**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/file/move/{srcPath}|PUT|Moves a file to a new location in a Cloud storage.|[MoveFile](https://reference.aspose.cloud/slides/#/File/MoveFile)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|srcPath|string|path|true|The path to a source file.|
|destPath|string|query|true|The path to a destination file.|
|srcStorageName|string|query|false|The name of a source storage.|
|destStorageName|string|query|false|The name of a destination storage.|
|versionId|string|query|false|The version ID of the file to be moved.|

### **Examples**

Move the **Data/example.pptx** file to the **Resources** folder in the **MyStorage** storage.

**cURL Solution**

{{< tabs tabTotal="1" tabID="5" tabName1="Request" >}}

{{< tab tabNum="1" >}}
```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/move/Data%2Fexample.pptx?destPath=Resources%2Fexample.pptx&srcStorageName=MyStorage&destStorageName=MyStorage" \
     -H "Authorization: Bearer <access_token>"
```
{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="9" tabID="55" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" >}}

{{< tab tabNum="1" >}}
```cs
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string sourcePath = "Data/example.pptx";
        string targetPath = "Resources/example.pptx";

        slidesApi.MoveFile(sourcePath, targetPath, storageName, storageName);
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String sourcePath = "Data/example.pptx";
        String targetPath = "Resources/example.pptx";

        slidesApi.moveFile(sourcePath, targetPath, storageName, storageName, null);
    }
}
```
{{< /tab >}}

{{< tab tabNum="3" >}}
```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "MyStorage";
$sourcePath = "Data/example.pptx";
$targetPath = "Resources/example.pptx";

$slidesApi->moveFile($sourcePath, $targetPath, $storageName, $storageName);
```
{{< /tab >}}

{{< tab tabNum="4" >}}
```rb
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
source_path = "Data/example.pptx"
target_path = "Resources/example.pptx"

slides_api.move_file(source_path, target_path, storage_name, storage_name)
```
{{< /tab >}}

{{< tab tabNum="5" >}}
```py
import asposeslidescloud

from asposeslidescloud.apis import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
source_path = "Data/example.pptx"
target_path = "Resources/example.pptx"

slides_api.move_file(source_path, target_path, storage_name, storage_name)
```
{{< /tab >}}

{{< tab tabNum="6" >}}
```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
sourcePath = "Data/example.pptx";
targetPath = "Resources/example.pptx";

slidesApi.moveFile(sourcePath, targetPath, storageName, storageName).then(() => {
});
```
{{< /tab >}}

{{< tab tabNum="7" >}}
```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

	const wchar_t* storageName = L"MyStorage";
	const wchar_t* sourcePath = L"Data/example.pptx";
	const wchar_t* targetPath = L"Resources/example.pptx";

	slidesApi->moveFile(sourcePath, targetPath, storageName, storageName);
}
```
{{< /tab >}}

{{< tab tabNum="8" >}}
```pl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

$slides_api->move_file(
    src_path => "Data/example.pptx",
    dest_path => "Resources/example.pptx",
    src_storage_name => "MyStorage",
    dest_storage_name => "MyStorage");
```
{{< /tab >}}

{{< tab tabNum="9" >}}
```go
import (
	asposeslidescloud "github.com/aspose-slides-cloud/aspose-slides-cloud-go/v24"
)

func main() {
	configuration := asposeslidescloud.NewConfiguration()
	configuration.AppSid = "MyClientId"
	configuration.AppKey = "MyClientSecret"

	slidesApi := asposeslidescloud.NewAPIClient(configuration).SlidesApi

	storageName := "MyStorage"
	sourcePath := "Data/example.pptx"
	targetPath := "Resources/example.pptx"

	slidesApi.MoveFile(sourcePath, targetPath, storageName, storageName, "")
}
```
{{< /tab >}}

{{< /tabs >}}

## **DeleteFile**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/file/{path}|DELETE|Deletes a file from a Cloud storage.|[DeleteFile](https://reference.aspose.cloud/slides/#/File/DeleteFile)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The path to a file.|
|storageName|string|query|false|The name of a storage.|
|versionId|string|query|false|The version ID of the file to be deleted.|

### **Examples**

Delete the **Resources/example.pptx** file from the **MyStorage** storage.

**cURL Solution**

{{< tabs tabTotal="1" tabID="6" tabName1="Request" >}}

{{< tab tabNum="1" >}}
```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/storage/file/Resources%2Fexample.pptx?storageName=MyStorage" \
     -H "Authorization: Bearer <access_token>"
```
{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="9" tabID="66" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" >}}

{{< tab tabNum="1" >}}
```cs
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";        
        string filePath = "Resources/example.pptx";

        slidesApi.DeleteFile(filePath, storageName);
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```java
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String filePath = "Resources/example.pptx";

        slidesApi.deleteFile(filePath, storageName, null);
    }
}
```
{{< /tab >}}

{{< tab tabNum="3" >}}
```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "MyStorage";
$filePath = "Resources/example.pptx";

$slidesApi->deleteFile($filePath, $storageName);
```
{{< /tab >}}

{{< tab tabNum="4" >}}
```rb
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
file_path = "Resources/example.pptx"

slides_api.delete_file(file_path, storage_name)
```
{{< /tab >}}

{{< tab tabNum="5" >}}
```py
import asposeslidescloud

from asposeslidescloud.apis import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
file_path = "Resources/example.pptx"

slides_api.delete_file(file_path, storage_name)
```
{{< /tab >}}

{{< tab tabNum="6" >}}
```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
filePath = "Resources/example.pptx";

slidesApi.deleteFile(filePath, storageName).then(() => {
});
```
{{< /tab >}}

{{< tab tabNum="7" >}}
```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

	const wchar_t* storageName = L"MyStorage";
	const wchar_t* filePath = L"Resources/example.pptx";

	slidesApi->deleteFile(filePath, storageName);
}
```
{{< /tab >}}

{{< tab tabNum="8" >}}
```pl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

$slides_api->delete_file(
    path => "Resources/example.pptx", 
    storage_name => "MyStorage");
```
{{< /tab >}}

{{< tab tabNum="9" >}}
```go
import (
	asposeslidescloud "github.com/aspose-slides-cloud/aspose-slides-cloud-go/v24"
)

func main() {
	configuration := asposeslidescloud.NewConfiguration()
	configuration.AppSid = "MyClientId"
	configuration.AppKey = "MyClientSecret"

	slidesApi := asposeslidescloud.NewAPIClient(configuration).SlidesApi

	storageName := "MyStorage"
	filePath := "Resources/example.pptx"

	slidesApi.DeleteFile(filePath, storageName, "")
}
```
{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
