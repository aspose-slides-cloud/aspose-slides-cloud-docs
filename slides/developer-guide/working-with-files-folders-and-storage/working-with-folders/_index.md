---
title: "Working with Folders"
keywords: "PowerPoint, presentation, REST API, Cloud API, cloud storage, file storage, create a folder, copy a folder, delete a folder"
type: docs
url: /working-with-folders/
weight: 20
---

## **Introduction**

Aspose.Slides Cloud API provides you with the ability to create and manage folders in storages. Folders in storages perform the same basic functions as on your computer. You can use the following methods to create new folders, delete, copy, move, and retrieve information about them.

## **GetFilesList**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/folder/{path}|GET|Retrieves information about all files and folders within a folder.|[GetFilesList](https://reference.aspose.cloud/slides/#/Folder/GetFilesList)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The path to the folder.|
|storageName|string|query|false|The name of a storage where the folder is located.|

{{% alert color="primary" %}} 
This method only retrieves information about files and folders that are directly within the specified folder, and does not take into account subfolders.
{{% /alert %}} 

### **Example**

In the **MyStorage** storage, there is a folder named **MyFolder**. Get information about all files and folders in the **MyFolder** folder.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Information about the Files and Folders**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/storage/folder/MyFolder?storageName=MyStorage" \
     -H "authorization: Bearer MyAccessToken" 
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "value": [
    {
      "name": "MyFolder1",
      "isFolder": true,
      "modifiedDate": "0001-01-01T00:00:00",
      "size": 0,
      "path": "/MyFolder/MyFolder1/"
    },
    {
      "name": "MyFolder2",
      "isFolder": true,
      "modifiedDate": "0001-01-01T00:00:00",
      "size": 0,
      "path": "/MyFolder/MyFolder2/"
    },
    {
      "name": "MyPresentation.pptx",
      "isFolder": false,
      "modifiedDate": "2024-02-16T07:05:08+00:00",
      "size": 34259,
      "path": "/MyFolder/MyPresentation.pptx"
    }
  ]
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string folderName = "MyFolder";

        FilesList filesList = slidesApi.GetFilesList(folderName, storageName);

        foreach (StorageFile item in filesList.Value)
        {
            Console.WriteLine("Name: " + item.Name);
            Console.WriteLine("Is folder: " + item.IsFolder);
            Console.WriteLine("Size: " + item.Size);
            Console.WriteLine("Path: " + item.Path);
            Console.WriteLine();
        }
    }
}

// The output example:
//
// Name: MyFolder1
// Is folder: True
// Size: 0
// Path: /MyFolder/MyFolder1/
//
// Name: MyFolder2
// Is folder: True
// Size: 0
// Path: /MyFolder/MyFolder2/
//
// Name: MyPresentation.pptx
// Is folder: False
// Size: 34259
// Path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.FilesList;
import com.aspose.slides.model.StorageFile;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String folderName = "MyFolder";

        FilesList filesList = slidesApi.getFilesList(folderName, storageName);

        for (StorageFile item : filesList.getValue())
        {
            System.out.println("Name: " + item.getName());
            System.out.println("Is folder: " + item.isIsFolder());
            System.out.println("Size: " + item.getSize());
            System.out.println("Path: " + item.getPath());
            System.out.println();
        }
    }
}

// The output example:
// 
// Name: MyFolder1
// Is folder: true
// Size: 0
// Path: /MyFolder/MyFolder1/
// 
// Name: MyFolder2
// Is folder: true
// Size: 0
// Path: /MyFolder/MyFolder2/
// 
// Name: MyPresentation.pptx
// Is folder: false
// Size: 34259
// Path: /MyFolder/MyPresentation.pptx
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
$folderName = "MyFolder";

$filesList = $slidesApi->getFilesList($folderName, $storageName);

foreach ($filesList->getValue() as $item)
{
    echo "Name: ", $item->getName(), "\n";
    echo "Is folder: ", $item->getIsFolder(), "\n";
    echo "Size: ", $item->getSize(), "\n";
    echo "Path: ", $item->getPath(), "\n";
    echo "\n";
}

// The output example:
// 
// Name: MyFolder1
// Is folder: 1
// Size: 0
// Path: /MyFolder/MyFolder1/
// 
// Name: MyFolder2
// Is folder: 1
// Size: 0
// Path: /MyFolder/MyFolder2/
// 
// Name: MyPresentation.pptx
// Is folder: 
// Size: 34259
// Path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
folder_name = "MyFolder"

files_list = slides_api.get_files_list(folder_name, storage_name)

files_list.value.each do |item|
    puts "Name: #{item.name}"
    puts "Is folder: #{item.is_folder}" 
    puts "Size: #{item.size}"
    puts "Path: #{item.path}"
    puts
end

# The output example:
# 
# Name: MyFolder1
# Is folder: true
# Size: 0
# Path: /MyFolder/MyFolder1/
# 
# Name: MyFolder2
# Is folder: true
# Size: 0
# Path: /MyFolder/MyFolder2/
# 
# Name: MyPresentation.pptx
# Is folder: false
# Size: 34259
# Path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
folder_name = "MyFolder"

files_list = slides_api.get_files_list(folder_name, storage_name)

for item in files_list.value:
    print("Name:", item.name)
    print("Is folder:", item.is_folder)
    print("Size:", item.size)
    print("Path:", item.path)
    print()

# The output example:
# 
# Name: MyFolder1
# Is folder: True
# Size: 0
# Path: /MyFolder/MyFolder1/
# 
# Name: MyFolder2
# Is folder: True
# Size: 0
# Path: /MyFolder/MyFolder2/
# 
# Name: MyPresentation.pptx
# Is folder: False
# Size: 34259
# Path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
folderName = "MyFolder";

slidesApi.getFilesList(folderName, storageName).then(filesList => {
    filesList.body.value.forEach(item => {
        console.log("Name:", item.name);
        console.log("Is folder:", item.isFolder);
        console.log("Size:", item.size);
        console.log("Path:", item.path);
        console.log();
    });
});

// The output example:
// 
// Name: MyFolder1
// Is folder: true
// Size: 0
// Path: /MyFolder/MyFolder1/
// 
// Name: MyFolder2
// Is folder: true
// Size: 0
// Path: /MyFolder/MyFolder2/
// 
// Name: MyPresentation.pptx
// Is folder: false
// Size: 34259
// Path: /MyFolder/MyPresentation.pptx
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
    const wchar_t* folderName = L"MyFolder";

    std::shared_ptr<FilesList> filesList = slidesApi->getFilesList(folderName, storageName).get();

    for (std::shared_ptr<StorageFile> item : filesList->getValue())
    {
        std::wcout << L"Name: " << item->getName() << "\n";
        std::wcout << L"Is folder: " << item->getIsFolder() << "\n";
        std::wcout << L"Size: " << item->getSize() << "\n";
        std::wcout << L"Path: " << item->getPath() << "\n";
        std::wcout << "\n";
    }
}

// The output example:
// 
// Name: MyFolder1
// Is folder: 1
// Size: 0
// Path: /MyFolder/MyFolder1/
// 
// Name: MyFolder2
// Is folder: 1
// Size: 0
// Path: /MyFolder/MyFolder2/
// 
// Name: MyPresentation.pptx
// Is folder: 0
// Size: 34259
// Path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyStorage";
$config->{app_key} = "MyFolder";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $storage_name = "MyStorage";
my $folder_name = "MyFolder";

my %parameters = (path => $folder_name, storage_name => $storage_name);
my $files_list = $slides_api->get_files_list(%parameters);

for my $item (@{$files_list->{value}}) {
    print("Name: ", $item->{name}, "\n");
    print("Is folder: ", $item->{is_folder}, "\n");
    print("Size: ", $item->{size}, "\n");
    print("Path: ", $item->{path}, "\n");
    print("\n");
}

# The output example:
# 
# Name: MyFolder1
# Is folder: 1
# Size: 0
# Path: /MyFolder/MyFolder1/
# 
# Name: MyFolder2
# Is folder: 1
# Size: 0
# Path: /MyFolder/MyFolder2/
# 
# Name: MyPresentation.pptx
# Is folder: 0
# Size: 34259
# Path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **CreateFolder**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/folder/{path}|PUT|Creates a folder in a storage.|[CreateFolder](https://reference.aspose.cloud/slides/#/Folder/CreateFolder)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The path to the folder to be created.|
|storageName|string|query|false|The name of a storage.|

### **Example**

Create a folder named **MyPresentations** in the **MyFolder** folder located in the **MyStorage** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Create the Folder**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/folder/MyFolder%2FMyPresentations?storageName=MyStorage" \
     -H "authorization: Bearer MyAccessToken" 
```

{{< /tab >}}

{{< tab tabNum="2" >}}

None.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string folderPath = "MyFolder/MyPresentations";

        slidesApi.CreateFolder(folderPath, storageName);
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
        String folderPath = "MyFolder/MyPresentations";

        slidesApi.createFolder(folderPath, storageName);
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
$folderPath = "MyFolder/MyPresentations";

$slidesApi->createFolder($folderPath, $storageName);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
folder_path = "MyFolder/MyPresentations"

slides_api.create_folder(folder_path, storage_name)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
folder_path = "MyFolder/MyPresentations"

slides_api.create_folder(folder_path, storage_name)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
folderPath = "MyFolder/MyPresentations";

slidesApi.createFolder(folderPath, storageName).then(() => {
    console.log("Done.");
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
    const wchar_t* folderPath = L"MyFolder/MyPresentations";

    slidesApi->createFolder(folderPath, storageName).get();
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $storage_name = "MyStorage";
my $folder_path = "MyFolder/MyPresentations";

$slides_api->create_folder(path => $folder_path, storage_name => $storage_name);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **DeleteFolder**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/folder/{path}|DELETE|Deletes a folder from a storage.|[DeleteFolder](https://reference.aspose.cloud/slides/#/Folder/DeleteFolder)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The path to the folder to be deleted.|
|storageName|string|query|false|The name of a storage.|
|recursive|boolean|query|false|Enable to delete subfolders and files. The default value is false.|

### **Example**

Delete the folder **MyPresentations** from the folder **MyFolder** located in the storage **MyStorage**. Also, delete subfolders and files.

**cURL Solution**

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Folder**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/storage/folder/MyFolder%2FMyPresentations?storageName=MyStorage&recursive=true" \
     -H "authorization: Bearer MyAccessToken"  
```

{{< /tab >}}

{{< tab tabNum="2" >}}

None.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="33" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string folderPath = "MyFolder/MyPresentations";
        bool recursive = true;

        slidesApi.DeleteFolder(folderPath, storageName, recursive);
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
        String folderPath = "MyFolder/MyPresentations";
        boolean recursive = true;
        
        slidesApi.deleteFolder(folderPath, storageName, recursive);
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
$folderPath = "MyFolder/MyPresentations";
$recursive = true;

$slidesApi->deleteFolder($folderPath, $storageName, $recursive);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
folder_path = "MyFolder/MyPresentations"
recursive = true

slides_api.delete_folder(folder_path, storage_name, recursive)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
folder_path = "MyFolder/MyPresentations"
recursive = True

slides_api.delete_folder(folder_path, storage_name, recursive)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
folderPath = "MyFolder/MyPresentations";
recursive = true;

slidesApi.deleteFolder(folderPath, storageName, recursive).then(() => {
    console.log("Done.");
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
    const wchar_t* folderPath = L"MyFolder/MyPresentations";
    bool recursive = true;

    slidesApi->deleteFolder(folderPath, storageName, recursive).get();
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $storage_name = "MyStorage";
my $folder_path = "MyFolder/MyPresentations";
my $recursive = "true";

$slides_api->delete_folder(path => $folder_path, storage_name => $storage_name, recursive => $recursive);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **CopyFolder**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/folder/copy/{srcPath}|PUT|Copies an existing folder to a new folder.|[CopyFolder](https://reference.aspose.cloud/slides/#/Folder/CopyFolder)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|srcPath|string|path|true|The path to the folder to be copied.|
|destPath|string|query|true|The path to the destination folder.|
|srcStorageName|string|query|false|The name of a source storage.|
|destStorageName|string|query|false|The name of a destination storage.|

### **Example**

In the **default** storage, copy the **MyPresentations** folder from **MyFolder1** to **MyFolder2**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="4" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Copy the Folder**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/folder/copy/MyFolder1%2FMyPresentations?destPath=MyFolder2%2FMyPresentations" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

None.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="44" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string srcFolderPath = "MyFolder1/MyPresentations";
        string dstFolderPath = "MyFolder2/MyPresentations";

        slidesApi.CopyFolder(srcFolderPath, dstFolderPath);
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

        String srcFolderPath = "MyFolder1/MyPresentations";
        String dstFolderPath = "MyFolder2/MyPresentations";

        slidesApi.copyFolder(srcFolderPath, dstFolderPath, null, null);
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

$srcFolderPath = "MyFolder1/MyPresentations";
$dstFolderPath = "MyFolder2/MyPresentations";

$slidesApi->copyFolder($srcFolderPath, $dstFolderPath);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

src_folder_path = "MyFolder1/MyPresentations"
dst_folder_path = "MyFolder2/MyPresentations"

slides_api.copy_folder(src_folder_path, dst_folder_path)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

src_folder_path = "MyFolder1/MyPresentations"
dst_folder_path = "MyFolder2/MyPresentations"

slides_api.copy_folder(src_folder_path, dst_folder_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

srcFolderPath = "MyFolder1/MyPresentations";
dstFolderPath = "MyFolder2/MyPresentations";

slidesApi.copyFolder(srcFolderPath, dstFolderPath).then(() => {
    console.log("Done.");
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"cMyClientId", L"MyClientSecret");

    const wchar_t* srcFolderPath = L"MyFolder1/MyPresentations";
    const wchar_t* dstFolderPath = L"MyFolder2/MyPresentations";

    slidesApi->copyFolder(srcFolderPath, dstFolderPath).get();
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "cMyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $src_folder_path = "MyFolder1/MyPresentations";
my $dst_folder_path = "MyFolder2/MyPresentations";

$slides_api->copy_folder(src_path => $src_folder_path, dest_path => $dst_folder_path);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **MoveFolder**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/folder/move/{srcPath}|PUT|Moves a folder to a new location.|[MoveFolder](https://reference.aspose.cloud/slides/#/Folder/MoveFolder)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|srcPath|string|path|true|The path to the folder to be moved.|
|destPath|string|query|true|The path to the new location.|
|srcStorageName|string|query|false|The name of a source storage.|
|destStorageName|string|query|false|The name of a destination storage.|

### **Example**

In the **default** storage, move the **MyPresentations** folder from **MyFolder1** to **MyFolder2**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Move the Folder**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/folder/move/MyFolder1%2FMyPresentations?destPath=MyFolder2%2FMyPresentations" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

None.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="55" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string srcFolderPath = "MyFolder1/MyPresentations";
        string dstFolderPath = "MyFolder2/MyPresentations";

        slidesApi.MoveFolder(srcFolderPath, dstFolderPath);
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

        String srcFolderPath = "MyFolder1/MyPresentations";
        String dstFolderPath = "MyFolder2/MyPresentations";

        slidesApi.moveFolder(srcFolderPath, dstFolderPath, null, null);
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

$srcFolderPath = "MyFolder1/MyPresentations";
$dstFolderPath = "MyFolder2/MyPresentations";

$slidesApi->moveFolder($srcFolderPath, $dstFolderPath);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

src_folder_path = "MyFolder1/MyPresentations"
dst_folder_path = "MyFolder2/MyPresentations"

slides_api.move_folder(src_folder_path, dst_folder_path)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

src_folder_path = "MyFolder1/MyPresentations"
dst_folder_path = "MyFolder2/MyPresentations"

slides_api.move_folder(src_folder_path, dst_folder_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

srcFolderPath = "MyFolder1/MyPresentations";
dstFolderPath = "MyFolder2/MyPresentations";

slidesApi.moveFolder(srcFolderPath, dstFolderPath).then(() => {
    console.log("Done.");
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

    const wchar_t* srcFolderPath = L"MyFolder1/MyPresentations";
    const wchar_t* dstFolderPath = L"MyFolder2/MyPresentations";

    slidesApi->moveFolder(srcFolderPath, dstFolderPath).get();
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $src_folder_path = "MyFolder1/MyPresentations";
my $dst_folder_path = "MyFolder2/MyPresentations";

$slides_api->move_folder(src_path => $src_folder_path, dest_path => $dst_folder_path);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
