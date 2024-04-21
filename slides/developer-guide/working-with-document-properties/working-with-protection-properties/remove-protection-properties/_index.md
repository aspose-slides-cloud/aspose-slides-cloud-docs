---
title: "Remove Protection Properties"
keywords: "PowerPoint, presentation, REST API, Cloud API, protection, protection properties, remove a protection property"
type: docs
url: /remove-protection-properties/
weight: 30
---

## **Introduction**

The following methods allow you to remove protection properties from a PowerPoint presentation saved to storage or a local file.

## **DeleteProtection**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/protection|DELETE|Removes the protection properties from a presentation saved to the storage.|[DeleteProtection](https://reference.aspose.cloud/slides/#/Protection/DeleteProtection)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of the presentation file.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

The **MyPresentation.pptx** document has been saved to **the storage**. Remove the protection properties from the presentation that is protected to be opened by the password **MyPassword**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Remove the Protection Properties**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/protection" \
     -H "Authorization: Bearer MyAccessToken" \
     -H "password: MyPassword" \
     -H "accept: application/json"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "encryptDocumentProperties": false,
    "readOnlyRecommended": false,
    "isWriteProtected": false,
    "isEncrypted": false,
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/protectionProperties",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;
using System;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var protectionProperties = slidesApi.DeleteProtection("MyPresentation.pptx", "MyPassword");

        // Check if the presentation has been decrypted.
        Console.WriteLine(protectionProperties.IsEncrypted);
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

        ProtectionProperties protectionProperties = slidesApi.deleteProtection("MyPresentation.pptx", "MyPassword", null, null);

        // Check if the presentation has been decrypted.
        System.out.println(protectionProperties.getIsEncrypted());
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

$protectionProperties = $slidesApi->deleteProtection("MyPresentation.pptx", "MyPassword");

// Check if the presentation has been decrypted.
echo $protectionProperties->getIsEncrypted();
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

protection_properties = slides_api.delete_protection("MyPresentation.pptx", "MyPassword")

# Check if the presentation has been decrypted.
puts protection_properties.is_encrypted
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

protection_properties = slides_api.delete_protection("MyPresentation.pptx", "MyPassword")

# Check if the presentation has been decrypted.
print(protection_properties.is_encrypted)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

slidesApi.deleteProtection("MyPresentation.pptx", "MyPassword").then(protectionProperties => {
    // Check if the presentation has been decrypted.
    console.log(protectionProperties.body.isIsEncrypted);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %parameters = (name => "MyPresentation.pptx", password => "MyPassword");
my $protection_properties = $slides_api->delete_protection(%parameters);

# Check if the presentation has been encrypted.
print($protection_properties->{is_encrypted});
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **DeleteProtectionOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/protection/delete|POST|Removes the protection properties from a presentation saved to a local file.|[DeleteProtectionOnline](https://reference.aspose.cloud/slides/#/Protection/DeleteProtectionOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|password|string|header|true|The password to open the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

The **MyPresentation.pptx** document has been saved to **a local file**. Remove the protection properties from the presentation that is protected to be opened by the password **MyPassword**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Remove the Protection Properties**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/protection/delete" \
     -H "Authorization: Bearer MyAccessToken" \
     -H "password: MyPassword" \
     -F "file=@MyPresentation.pptx" \ 
     -o Unprotected.pptx
```

{{< /tab >}}

{{< tab tabNum="2" >}}

The unprotected presentation file.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;
using System.IO;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        using var documentStream = File.OpenRead("MyPresentation.pptx");
        using var resultStream = slidesApi.DeleteProtectionOnline(documentStream, "MyPassword");

        // Save the unprotected presentation.
        using var outputStream = File.OpenWrite("Unprotected.pptx");
        resultStream.CopyTo(outputStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        byte[] documentData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        File resultFile = slidesApi.deleteProtectionOnline(documentData, "MyPassword");

        System.out.println("The unprotected presentation was saved to " + resultFile.getPath());
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

$documentStream = fopen("MyPresentation.pptx", "r");
$resultFile = $slidesApi->deleteProtectionOnline($documentStream, "MyPassword");

echo "The unprotected presentation was saved to ", $resultFile->getPathname();
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

document_data = File.binread("MyPresentation.pptx")
result_data = slides_api.delete_protection_online(document_data, "MyPassword")

# Save the unprotected presentation.
File.binwrite("Unprotected.pptx", result_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

with open("MyPresentation.pptx", "rb") as document_stream:
    result_file_path = slides_api.delete_protection_online(document_stream, "MyPassword")

print("The unprotected presentation was saved to", result_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const documentStream = fs.createReadStream("MyPresentation.pptx");
slidesApi.deleteProtectionOnline(documentStream, "MyPassword").then(response => {
    // Save the unprotected presentation.
    fs.writeFile("Unprotected.pptx", response.body, (error) => {
        if (error) throw error;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $document_data = read_file("MyPresentation.pptx", { binmode => ":raw" });
my %parameters = (document => $document_data, password => "MyPassword");
my $result_data = $slides_api->delete_protection_online(%parameters);

# Save the unprotected presentation.
write_file("Unprotected.pptx", {binmode => ":raw"}, $result_data);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

The Aspose.Slides for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/).
