---
title: "Working with Files and Storage using Aspose.Slides Cloud"
type: docs
url: /working-with-files-and-storage-using-aspose-slides-cloud/
weight: 120
---

## **Introduction**
Aspose.Slides Cloud provides methods to work with files uploaded to Aspose Cloud Storage or any other Cloud Storage of your choice. If you need any help getting started with setting third party storage please refer to [Aspose Cloud UI Help Topics](https://docs.aspose.cloud/storage/aspose-cloud-ui-help-topics/).

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

## **Downloading a file from Cloud Storage**

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

### **SDK Examples**
Download a file **Data/example.pptx** from a storage **Main** and save the file to **result.pptx**. 

{{< tabs tabTotal="11" tabID="7" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System;
using System.IO;
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var resultPath = "result.pptx";

        using (var fileStream = slidesApi.DownloadFile(filePath, storageName))
        using (var resultStream = File.OpenWrite(resultPath))
            fileStream.CopyTo(resultStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var resultPath = "result.pptx";

        // Note: The file data will be stored to a temporary file.
        var file = slidesApi.downloadFile(filePath, storageName, null);

        Files.copy(file.toPath(), Paths.get(resultPath));
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "Main";
$filePath = "Data/example.pptx";
$resultPath = "result.pptx";

// Note: The file data will be stored to a temporary file.
$file = $slidesApi->downloadFile($filePath, $storageName);

copy($file->getRealPath(), $resultPath);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud
import shutil

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

storage_name = "Main"
file_path = "Data/example.pptx"
result_path = "result.pptx"

# Note: The file data will be stored to a temporary file.
temp_path = slides_api.download_file(file_path, storage_name)

shutil.copyfile(temp_path, result_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

const storageName = "Main"
const filePath = "Data/example.pptx"
const resultPath = "result.pptx"

slidesApi.downloadFile(filePath, storageName).then((response) => {
    fs.writeFile(resultPath, response.body, (error) => {
         if (error) {
             console.error(error) 
         }
     })
 })
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var resultPath = "result.pptx";

        // Note: The file data will be stored to a temporary file.
        var file = slidesApi.downloadFile(filePath, storageName, null);

        Files.copy(file.toPath(), Paths.get(resultPath));
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
	auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

	auto storageName = to_string_t("Main");
	auto filePath = to_string_t("Data/example.pptx");
	auto resultPath = to_string_t("result.pptx");

	std::ofstream resultStream(resultPath, std::ofstream::binary);
	slidesApi->downloadFile(filePath, storageName).get().writeTo(resultStream);
	
	return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go

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
      "result.pptx"
   ],
   "errors":[
   ]
}
```

{{< /tab >}}

{{< /tabs >}}

### **SDK Examples**
Upload a file **example.pptx** to the path **Data/result.pptx** on a storage **Main**.

{{< tabs tabTotal="11" tabID="8" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System;
using System.IO;
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "example.pptx";
        var resultPath = "Data/result.pptx";

        using (var fileStream = File.OpenRead(filePath))
        {
            var response = slidesApi.UploadFile(resultPath, fileStream, storageName);
            Console.WriteLine(response.Uploaded.Count);
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "example.pptx";
        var resultPath = "Data/result.pptx";

        var fileData = Files.readAllBytes(Paths.get(filePath));
        var response = slidesApi.uploadFile(resultPath, fileData, storageName);

        System.out.println(response.getUploaded().size());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "Main";
$filePath = "example.pptx";
$resultPath = "Data/result.pptx";

$fileStream = fopen($filePath, 'r');
$response = $slidesApi->uploadFile($resultPath, $fileStream, $storageName);

echo count($response->getUploaded());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

storage_name = "Main"
file_path = "example.pptx"
result_path = "Data/result.pptx"

with open(file_path, "rb") as file_stream:
    response = slides_api.upload_file(result_path, file_stream, storage_name)

print(len(response.uploaded))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

const storageName = "Main"
const filePath = "example.pptx"
const resultPath = "Data/result.pptx"

const fileStream = fs.createReadStream(filePath)
slidesApi.uploadFile(resultPath, fileStream, storageName).then((response) => {
    console.log(response.body.uploaded.length)
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "example.pptx";
        var resultPath = "Data/result.pptx";

        var fileData = Files.readAllBytes(Paths.get(filePath));
        var response = slidesApi.uploadFile(resultPath, fileData, storageName);

        System.out.println(response.getUploaded().size());
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
	auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

	auto storageName = to_string_t("Main");
	auto filePath = to_string_t("example.pptx");
	auto resultPath = to_string_t("Data/result.pptx");

	auto fileStream = std::make_shared<std::ifstream>(filePath, std::ios::binary);
	auto uploadContent = std::make_shared<HttpContent>();
	uploadContent->setData(fileStream);

	auto response = slidesApi->uploadFile(resultPath, uploadContent, storageName).get();
	std::cout << response->getUploaded().size();
	
	return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go

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

### **SDK Examples**
Copy a file **Data/example.pptx** to the path **Resources/example_copy.pptx** on a storage **Main**.

{{< tabs tabTotal="11" tabID="9" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System;
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var copyPath = "Resources/example_copy.pptx";

        slidesApi.CopyFile(filePath, copyPath, storageName, storageName);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var copyPath = "Resources/example_copy.pptx";

        slidesApi.copyFile(filePath, copyPath, storageName, storageName, null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "Main";
$filePath = "Data/example.pptx";
$copyPath = "Resources/example_copy.pptx";

$slidesApi->copyFile($filePath, $copyPath, $storageName, $storageName);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

storage_name = "Main"
file_path = "Data/example.pptx"
copy_path = "Resources/example_copy.pptx"

slides_api.copy_file(file_path, copy_path, storage_name, storage_name)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

const storageName = "Main"
const filePath = "Data/example.pptx"
const copyPath = "Resources/example_copy.pptx"

slidesApi.copyFile(filePath, copyPath, storageName, storageName).then(() => {
    console.log("Done")
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var copyPath = "Resources/example_copy.pptx";

        slidesApi.copyFile(filePath, copyPath, storageName, storageName, null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
	auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

	auto storageName = to_string_t("Main");
	auto filePath = to_string_t("Data/example.pptx");
	auto copyPath = to_string_t("Resources/example_copy.pptx");

	slidesApi->copyFile(filePath, copyPath, storageName, storageName);
	
	return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go

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

### **SDK Examples**
Move a file **Data/example.pptx** to the path **Resources/example.pptx** on a storage **Main**.

{{< tabs tabTotal="11" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System;
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var newPath = "Resources/example.pptx";

        slidesApi.MoveFile(filePath, newPath, storageName, storageName);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var newPath = "Resources/example.pptx";

        slidesApi.moveFile(filePath, newPath, storageName, storageName, null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "Main";
$filePath = "Data/example.pptx";
$newPath = "Resources/example.pptx";

$slidesApi->moveFile($filePath, $newPath, $storageName, $storageName);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

storage_name = "Main"
file_path = "Data/example.pptx"
new_path = "Resources/example.pptx"

slides_api.move_file(file_path, new_path, storage_name, storage_name)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

const storageName = "Main"
const filePath = "Data/example.pptx"
const newPath = "Resources/example.pptx"

slidesApi.moveFile(filePath, newPath, storageName, storageName).then(() => {
    console.log("Done")
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Data/example.pptx";
        var newPath = "Resources/example.pptx";

        slidesApi.moveFile(filePath, newPath, storageName, storageName, null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
	auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

	auto storageName = to_string_t("Main");
	auto filePath = to_string_t("Data/example.pptx");
	auto newPath = to_string_t("Resources/example.pptx");

	slidesApi->moveFile(filePath, newPath, storageName, storageName);
	
	return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go

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
curl -v -X DELETE "https://api.aspose.cloud/v3.0/slides/storage/file/Resources/example.pptx?storageName=Main" -H "Content-Type:application/json" -H "Authorization: Bearer <access_token>" --ssl-no-revoke
```

{{< /tab >}}

{{< /tabs >}}

### **SDK Examples**
Delete a file **Resources/example.pptx** on a storage **Main**.

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System;
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Resources/example.pptx";

        slidesApi.DeleteFile(filePath, storageName);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Resources/example.pptx";

        slidesApi.deleteFile(filePath, storageName, null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "Main";
$filePath = "Resources/example.pptx";

$slidesApi->deleteFile($filePath, $storageName);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

storage_name = "Main"
file_path = "Resources/example.pptx"

slides_api.delete_file(file_path, storage_name)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

const storageName = "Main"
const filePath = "Resources/example.pptx"

slidesApi.deleteFile(filePath, storageName).then(() => {
    console.log("Done")
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var filePath = "Resources/example.pptx";

        slidesApi.deleteFile(filePath, storageName, null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
	auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

	auto storageName = to_string_t("Main");
	auto filePath = to_string_t("Resources/example.pptx");

	slidesApi->deleteFile(filePath, storageName);
	
	return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go

```

{{< /tab >}}

{{< /tabs >}}
