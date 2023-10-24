---
title: "Setting Protection Properties"
type: docs
url: /setting-protection-properties/
weight: 20
---

## **Introduction**

The following methods allow you to set protection properties for a PowerPoint presentation. You can set passwords to read/write the presentation, or set read-only recommendation.

## **SetProtection**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/protection|PUT|Sets the protection properties for a presentation saved to the storage.|[SetProtection](https://reference.aspose.cloud/slides/#/Protection/SetProtection)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of the presentation file.|
|dto|[ProtectionProperties](/slides/working-with-protection-properties#ProtectionProperties)|body|true|The protection properties for the presentation.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Specify the string **MyPassword** to protect the document **MyPresentation.pptx** to read and set the recommendation to **read-only** for the presentation.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**
```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the Protection Properties**
```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/protection" \
     -H "Authorization: Bearer MyAccessToken" \
     -H "accept: application/json" \
     -H "Content-Type: application/json" \
     -d @ProtectionProperties.json
```

ProtectionProperties.json content:
```json
{
    "ReadPassword": "MyPassword",
    "ReadOnlyRecommended": true
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "encryptDocumentProperties": true,
    "readOnlyRecommended": true,
    "readPassword": "MyPassword",
    "isWriteProtected": false,
    "isEncrypted": true,
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
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the protection properties for the presentation.
        var properties = new ProtectionProperties
        {
            ReadPassword = "MyPassword",
            ReadOnlyRecommended = true
        };

        var response = slidesApi.SetProtection("MyPresentation.pptx", properties);

        // Check if the presentation has been encrypted.
        Console.WriteLine(response.IsEncrypted);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ProtectionProperties;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the protection properties for the presentation.
        ProtectionProperties properties = new ProtectionProperties();
        properties.setReadPassword("MyPassword");
        properties.setReadOnlyRecommended(true);

        ProtectionProperties response = slidesApi.setProtection("MyPresentation.pptx", properties, null, null, null);

        // Check if the presentation has been encrypted.
        System.out.println(response.isIsEncrypted());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ProtectionProperties;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare the protection properties for the presentation.
$properties = new ProtectionProperties();
$properties->setReadPassword("MyPassword");
$properties->setReadOnlyRecommended(true);

$response = $slidesApi->setProtection("MyPresentation.pptx", $properties);

// Check if the presentation has been encrypted.
echo $response->getIsEncrypted();
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

# Prepare the protection properties for the presentation.
properties = ProtectionProperties.new
properties.read_password = "MyPassword"
properties.read_only_recommended = true

response = slides_api.set_protection("MyPresentation.pptx", properties)

# Check if the presentation has been encrypted.
puts response.is_encrypted
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models import ProtectionProperties

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare the protection properties for the presentation.
properties = ProtectionProperties()
properties.read_password = "MyPassword"
properties.read_only_recommended = True

response = slides_api.set_protection("MyPresentation.pptx", properties)

# Check if the presentation has been encrypted.
print(response.is_encrypted)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Prepare the protection properties for the presentation.
const properties = new cloud.ProtectionProperties();
properties.readPassword = "MyPassword";
properties.readOnlyRecommended = true;

slidesApi.setProtection("MyPresentation.pptx", properties).then(response => {
    // Check if the presentation has been encrypted.
    console.log(response.body.isIsEncrypted);
}).catch(error => {
    console.error(error.message);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::ProtectionProperties;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare protection properties for the presentation.
my $properties = AsposeSlidesCloud::Object::ProtectionProperties->new();
$properties->{read_password} = "MyPassword";
$properties->{read_only_recommended} = 1;

my %parameters = (name => "MyPresentation.pptx", dto => $properties);
my $response = $slides_api->set_protection(%parameters);

# Check if the presentation has been encrypted.
print($response->{is_encrypted});
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SetProtectionOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/protection|PUT|Sets the protection properties for a presentation saved to a local file.|[SetProtectionOnline](https://reference.aspose.cloud/slides/#/Protection/SetProtectionOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|dto|[ProtectionProperties](/slides/working-with-protection-properties#ProtectionProperties)|body|true|The protection properties for the presentation.|
|password|string|header|false|The password to open the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Specify the string **MyPassword** to protect the **MyPresentation.pptx** document saved to a local file from being modified.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the Protection Properties**

```sh
curl -X PUT https://api.aspose.cloud/v3.0/slides/protection \
     -H "Authorization: Bearer MyAccessToken" \
     -F "file=@MyPresentation.pptx" \
     -F "dto=@ProtectionProperties.json;filename=" \
     -o WriteProtected.pptx
```

ProtectionProperties.json content:

```json
{
    "WritePassword": "MyPassword"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

The protected presentation file.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System.IO;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the protection properties for the presentation.
        var properties = new ProtectionProperties
        {
            WritePassword = "MyPassword"
        };

        using var documentStream = File.OpenRead("MyPresentation.pptx");
        using var resultStream = slidesApi.SetProtectionOnline(documentStream, properties);

        // Save the protected presentation.
        using var outputStream = File.OpenWrite("WriteProtected.pptx");
        resultStream.CopyTo(outputStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ProtectionProperties;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the protection properties for the presentation.
        ProtectionProperties properties = new ProtectionProperties();
        properties.setWritePassword("MyPassword");

        byte[] documentData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        File resultFile = slidesApi.setProtectionOnline(documentData, properties, null);

        System.out.println("The protected presentation was saved to " + resultFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ProtectionProperties;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare the protection properties for the presentation.
$properties = new ProtectionProperties();
$properties->setWritePassword("MyPassword");

$documentStream = fopen("MyPresentation.pptx", "r");
$resultFile = $slidesApi->setProtectionOnline($documentStream, $properties);

echo "The protected presentation was saved to ", $resultFile->getPathname();
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

# Prepare the protection properties for the presentation.
properties = ProtectionProperties.new
properties.write_password = "MyPassword"

document_data = File.binread("MyPresentation.pptx")
result_data = slides_api.set_protection_online(document_data, properties)

# Save the protected presentation.
File.binwrite("WriteProtected.pptx", result_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models import ProtectionProperties

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare the protection properties for the presentation.
properties = ProtectionProperties()
properties.write_password = "MyPassword"

with open("MyPresentation.pptx", "rb") as document_stream:
    result_file_path = slides_api.set_protection_online(document_stream, properties)

print("The protected presentation was saved to", result_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Prepare the protection properties for the presentation.
const properties = new cloud.ProtectionProperties();
properties.writePassword = "MyPassword";

const documentStream = fs.createReadStream("MyPresentation.pptx");
slidesApi.setProtectionOnline(documentStream, properties).then(response => {
    // Save the protected presentation.
    fs.writeFile("WriteProtected.pptx", response.body, (error) => {
        if (error) throw error;
    });
}).catch(error => {
    console.error(error.message);
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
use AsposeSlidesCloud::Object::ProtectionProperties;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare the protection properties for the presentation.
my $properties = AsposeSlidesCloud::Object::ProtectionProperties->new();
$properties->{write_password} = "MyPassword";

my $document_data = read_file("MyPresentation.pptx", { binmode => ":raw" });
my %parameters = (document => $document_data, dto => $properties);
my $result_data = $slides_api->set_protection_online(%parameters);

# Save the protected presentation.
write_file("WriteProtected.pptx", {binmode => ":raw"}, $result_data);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

The Aspose.Slides for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/).
