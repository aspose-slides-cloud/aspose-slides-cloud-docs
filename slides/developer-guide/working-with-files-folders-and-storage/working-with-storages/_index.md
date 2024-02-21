---
title: "Working with Storages"
type: docs
url: /working-with-storages/
weight: 10
---

## **Introduction**

With Aspose.Slides Cloud API, you can use the following methods to check if a storage exists, check if a folder or file exists, get disk usage information, and get file versions.

## **StorageExists**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/{storageName}/exist|GET|Checks if a storage exists.|[StorageExists](https://reference.aspose.cloud/slides/#/Storage/StorageExists)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|storageName|string|path|true|The name of a storage.|

### **Example**

Check if the **MyStorage** storage exists.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Check If the Storage Exists**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/storage/MyStorage/exist" \
     -H "authorization: Bearer MyAccessToken" 
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "exists": true
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";

        StorageExist storageExist = slidesApi.StorageExists(storageName);

        Console.WriteLine("Storage exists: " + storageExist.Exists);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.StorageExist;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";

        StorageExist storageExist = slidesApi.storageExists(storageName);

        System.out.println("Storage exists: " + storageExist.isExists());
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

$storageExist = $slidesApi->storageExists($storageName);

echo "Storage exists: ", $storageExist->getExists();
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

storage_exist = slides_api.storage_exists(storage_name)

print "Storage exists: ", storage_exist.exists
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"

storage_exist = slides_api.storage_exists(storage_name)

print("Storage exists:", storage_exist.exists)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";

slidesApi.storageExists(storageName).then(storageExist => {
    console.log("Storage exists:", storageExist.body.exists);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* storageName = L"MyStorage";

    std::shared_ptr<StorageExist> storageExist = slidesApi->storageExists(storageName).get();

    std::wcout << L"Storage exists: " << storageExist->isExists();
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

my $storage_exist = $slides_api->storage_exists(storage_name => $storage_name);

print("Storage exists: ", $storage_exist->{exists});
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **ObjectExists**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/exist/{path}|GET|Checks if a file or folder exists.|[ObjectExists](https://reference.aspose.cloud/slides/#/Storage/ObjectExists)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The path to a file or folder.|
|storageName|string|query|false|The name of a storage.|
|versionId|string|query|false|The version ID of the file.|

### **Example**

In the storage **MyStorage**, check if the file **MyFolder/MyPresentation.pptx** exists.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Check If the File Exists**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/storage/exist/MyFolder%2FMyPresentation.pptx?storageName=MyStorage" \
     -H "authorization: Bearer MyAccessToken" 
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "exists": true,
  "isFolder": false
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string objectPath = "MyFolder/MyPresentation.pptx";

        ObjectExist objectExist = slidesApi.ObjectExists(objectPath, storageName);

        Console.WriteLine("Object exists: " + objectExist.Exists);
        Console.WriteLine("Is folder: " + objectExist.IsFolder);
    }
}

// The output example:
//
// Object exists: True
// Is folder: False
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ObjectExist;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String objectPath = "MyFolder/MyPresentation.pptx";

        ObjectExist objectExist = slidesApi.objectExists(objectPath, storageName, null);

        System.out.println("Object exists: " + objectExist.isExists());
        System.out.println("Is folder: " + objectExist.getIsFolder());
    }
}

// The output example:
//
// Object exists: true
// Is folder: false
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
$objectPath = "MyFolder/MyPresentation.pptx";

$objectExist = $slidesApi->objectExists($objectPath, $storageName);

echo "Object exists: ", $objectExist->getExists(), "\n";
echo "Is folder: ", $objectExist->getIsFolder();

// The output example:
//
// Object exists: 1
// Is folder: 
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
object_path = "MyFolder/MyPresentation.pptx"

object_exist = slides_api.object_exists(object_path, storage_name)

puts "Object exists: #{object_exist.exists}"
puts "Is folder: #{object_exist.is_folder}"

# The output example:
#
# Object exists: true
# Is folder: false
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
object_path = "MyFolder/MyPresentation.pptx"

object_exist = slides_api.object_exists(object_path, storage_name)

print("Object exists:", object_exist.exists)
print("Is folder:", object_exist.is_folder)

# The output example:
#
# Object exists: True
# Is folder: False
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
objectPath = "MyFolder/MyPresentation.pptx";

slidesApi.objectExists(objectPath, storageName).then(objectExist => {
    console.log("Object exists:", objectExist.body.exists);
    console.log("Is folder:", objectExist.body.isFolder);
});

// The output example:
//
// Object exists: true
// Is folder: false
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
    const wchar_t* objectPath = L"MyFolder/MyPresentation.pptx";

    std::shared_ptr<ObjectExist> objectExist = slidesApi->objectExists(objectPath, storageName).get();

    std::wcout << L"Object exists: " << objectExist->isExists() << "\n";
    std::wcout << L"Is folder: " << objectExist->getIsFolder();
}

// The output example:
//
// Object exists: 1
// Is folder: 0
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
my $object_path = "MyFolder/MyPresentation.pptx";

my $object_exist = $slides_api->object_exists(path => $object_path, storage_name => $storage_name);

print("Object exists: ", $object_exist->{exists}, "\n");
print("Is folder: ", $object_exist->{is_folder});

# The output example:
#
# Object exists: 1
# Is folder: 0
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **GetDiscUsage**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/disc|GET|Retrieves information about disk usage in a storage.|[GetDiscUsage](https://reference.aspose.cloud/slides/#/Storage/GetDiscUsage)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|storageName|string|query|false|The name of a storage.|

### **Example**

Get disk usage information from **MyStorage** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Disk Usage Information**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/storage/disc?storageName=MyStorage" \
     -H "authorization: Bearer MyAccessToken" 
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "UsedSize": 50479860,
  "TotalSize": 2147483648
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";

        DiscUsage discUsage = slidesApi.GetDiscUsage(storageName);

        Console.WriteLine("Total size: " + discUsage.TotalSize);
        Console.WriteLine("Used size: " + discUsage.UsedSize);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.DiscUsage;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";

        DiscUsage discUsage = slidesApi.getDiscUsage(storageName);

        System.out.println("Total size: " + discUsage.getTotalSize());
        System.out.println("Used size: " + discUsage.getUsedSize());
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

$discUsage = $slidesApi->getDiscUsage($storageName);

echo "Total size: ", $discUsage->getTotalSize(), "\n";
echo "Used size: ", $discUsage->getUsedSize();
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

disc_usage = slides_api.get_disc_usage(storage_name)

puts "Total size: #{disc_usage.total_size}"
puts "Used size: #{disc_usage.used_size}"
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"

disc_usage = slides_api.get_disc_usage(storage_name)

print("Total size:", disc_usage.total_size)
print("Used size:", disc_usage.used_size)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";

slidesApi.getDiscUsage(storageName).then(discUsage => {
    console.log("Total size:", discUsage.body.totalSize);
    console.log("Used size:", discUsage.body.usedSize);
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

    std::shared_ptr<DiscUsage> discUsage = slidesApi->getDiscUsage(storageName).get();

    std::wcout << L"Total size: " << discUsage->getTotalSize() << "\n";
    std::wcout << L"Used size: " << discUsage->getUsedSize();
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

my $disc_usage = $slides_api->get_disc_usage(storage_name => $storage_name);

print("Total size: ", $disc_usage->{total_size}, "\n");
print("Used size: ", $disc_usage->{used_size});
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **GetFileVersions**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/storage/version/{path}|GET|Retrieves information about versions of a file.|[GetFileVersions](https://reference.aspose.cloud/slides/#/Storage/GetFileVersions)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|path|string|path|true|The path to a file.|
|storageName|string|query|false|The name of a storage.|

### **Example**

Get information about versions of the **MyFolder/MyPresentation.pptx** file located in **MyStorage** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get the Versions**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/storage/version/MyFolder%2FMyPresentation.pptx?storageName=MyStorage" \
     -H "authorization: Bearer MyAccessToken" 
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "value": [
    {
      "versionId": "null",
      "isLatest": true,
      "name": "MyPresentation.pptx",
      "isFolder": false,
      "modifiedDate": "2024-02-21T07:02:16+00:00",
      "size": 50557,
      "path": "/MyFolder/MyPresentation.pptx"
    }
  ]
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string filePath = "MyFolder/MyPresentation.pptx";

        FileVersions fileVersions = slidesApi.GetFileVersions(filePath, storageName);

        foreach (FileVersion fileVersion in fileVersions.Value)
        {
            Console.WriteLine("Version ID: " + fileVersion.VersionId);
            Console.WriteLine("Is latest: " + fileVersion.IsLatest);
            Console.WriteLine("File name: " + fileVersion.Name);
            Console.WriteLine("Is folder: " + fileVersion.IsFolder);
            Console.WriteLine("File size: " + fileVersion.Size);
            Console.WriteLine("File path: " + fileVersion.Path);
            Console.WriteLine();
        }
    }
}

// The output example:
//
// Version ID: null
// Is latest: True
// File name: MyPresentation.pptx
// Is folder: False
// File size: 50557
// File path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.FileVersion;
import com.aspose.slides.model.FileVersions;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String filePath = "MyFolder/MyPresentation.pptx";

        FileVersions fileVersions = slidesApi.getFileVersions(filePath, storageName);

        for (FileVersion fileVersion : fileVersions.getValue()) {
            System.out.println("Version ID: " + fileVersion.getVersionId());
            System.out.println("Is latest: " + fileVersion.getIsLatest());
            System.out.println("File name: " + fileVersion.getName());
            System.out.println("Is folder: " + fileVersion.getIsFolder());
            System.out.println("File size: " + fileVersion.getSize());
            System.out.println("File path: " + fileVersion.getPath());
            System.out.println();
        }
    }
}

// The output example:
//
// Version ID: null
// Is latest: true
// File name: MyPresentation.pptx
// Is folder: false
// File size: 50557
// File path: /MyFolder/MyPresentation.pptx
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
$filePath = "MyFolder/MyPresentation.pptx";

$fileVersions = $slidesApi->getFileVersions($filePath, $storageName);

foreach ($fileVersions->getValue() as $fileVersion)
{
    echo "Version ID: ", $fileVersion->getVersionId(), "\n";
    echo "Is latest: ", $fileVersion->getIsLatest(), "\n";
    echo "File name: ", $fileVersion->getName(), "\n";
    echo "Is folder: ", $fileVersion->getIsFolder(), "\n";
    echo "File size: ", $fileVersion->getSize(), "\n";
    echo "File path: ", $fileVersion->getPath(), "\n";
    echo "\n";
}

// The output example:
//
// Version ID: null
// Is latest: 1
// File name: MyPresentation.pptx
// Is folder: 
// File size: 50557
// File path: /MyFolder/MyPresentation.pptx
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
file_path = "MyFolder/MyPresentation.pptx"

file_versions = slides_api.get_file_versions(file_path, storage_name)

file_versions.value.each do |file_version|
    puts "Version ID: #{file_version.version_id}"
    puts "Is latest: #{file_version.is_latest}"
    puts "File name: #{file_version.name}"
    puts "Is folder: #{file_version.is_folder}"
    puts "File size: #{file_version.size}"
    puts "File path: #{file_version.path}" 
    puts
end

# The output example:
#
# Version ID: null
# Is latest: true
# File name: MyPresentation.pptx
# Is folder: false
# File size: 50557
# File path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
file_path = "MyFolder/MyPresentation.pptx"

file_versions = slides_api.get_file_versions(file_path, storage_name)

for file_version in file_versions.value:
    print("Version ID:", file_version.version_id)
    print("Is latest:", file_version.is_latest)
    print("File name:", file_version.name)
    print("Is folder:", file_version.is_folder)
    print("File size:", file_version.size)
    print("File path:", file_version.path)
    print()

# The output example:
#
# Version ID: null
# Is latest: True
# File name: MyPresentation.pptx
# Is folder: False
# File size: 50557
# File path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
filePath = "MyFolder/MyPresentation.pptx";

 slidesApi.getFileVersions(filePath, storageName).then(fileVersions => {
    fileVersions.body.value.forEach(fileVersion => {
        console.log("Version ID:", fileVersion.versionId);
        console.log("Is latest:", fileVersion.isLatest);
        console.log("File name:", fileVersion.name);
        console.log("Is folder:", fileVersion.isFolder);
        console.log("File size:", fileVersion.size);
        console.log("File path:", fileVersion.path);
        console.log();
    });
 });

// The output example:
//
// Version ID: null
// Is latest: true
// File name: MyPresentation.pptx
// Is folder: false
// File size: 50557
// File path: /MyFolder/MyPresentation.pptx
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
    const wchar_t* filePath = L"MyFolder/MyPresentation.pptx";

    std::shared_ptr<FileVersions> fileVersions = slidesApi->getFileVersions(filePath, storageName).get();

    for (std::shared_ptr<FileVersion> fileVersion : fileVersions->getValue())
    {
        std::wcout << L"Version ID: " << fileVersion->getVersionId() << "\n";
        std::wcout << L"Is latest: " << fileVersion->getIsLatest() << "\n";
        std::wcout << L"File name: " << fileVersion->getName() << "\n";
        std::wcout << L"Is folder: " << fileVersion->getIsFolder() << "\n";
        std::wcout << L"File size: " << fileVersion->getSize() << "\n";
        std::wcout << L"File path: " << fileVersion->getPath() << "\n";
        std::wcout << "\n";
    }
}

// The output example:
//
// Version ID: null
// Is latest: 1
// File name: MyPresentation.pptx
// Is folder: 0
// File size: 50557
// File path: /MyFolder/MyPresentation.pptx
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
my $file_path = "MyFolder/MyPresentation.pptx";

my $file_versions = $slides_api->get_file_versions(path => $file_path, storage_name => $storage_name);

for my $file_version (@{$file_versions->{value}}) {
    print("Version ID: ", $file_version->{version_id}, "\n");
    print("Is latest: ", $file_version->{is_latest}, "\n");
    print("File name: ", $file_version->{name}, "\n");
    print("Is folder: ", $file_version->{is_folder}, "\n");
    print("File size: ", $file_version->{size}, "\n");
    print("File path: ", $file_version->{path}, "\n");
    print("\n");
}

# The output example:
#
# Version ID: null
# Is latest: 1
# File name: MyPresentation.pptx
# Is folder: 0
# File size: 50557
# File path: /MyFolder/MyPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
