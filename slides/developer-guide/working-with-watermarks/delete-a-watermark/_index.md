---
title: "Delete a Watermark"
keywords: "PowerPoint, presentation, REST API, Cloud API, text, watermark, delete a watermark, remove a watermark"
type: docs
url: /delete-a-watermark/
weight: 30
---

## **Introduction**

PowerPoint slides may contain watermarks, which are text or graphic elements added to the slide to provide a specific visual effect or to protect the document from copying. The following methods allow you to delete watermarks from a PowerPoint document.

{{% alert color="primary" %}} 
The methods below, by default, delete watermark shapes named "watermark" from a presentation. You can also specify the name of the watermark shapes you want to delete.
{{% /alert %}} 

## **DeleteWatermark**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/watermark/delete|DELETE|Deletes watermark shapes from the presentation saved to a storage.|[DeleteWatermark](https://reference.aspose.cloud/slides/#/Watermark/DeleteWatermark)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The presentation file name.|
|shapeName|string|query|false|The name of the watermark shapes. If the value is `null`, the default value of "watermark" is used.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete watermark shapes from the document **MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Watermarks**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/watermark/delete" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var fileName = "MyPresentation.pptx";

        slidesApi.DeleteWatermark(fileName);
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

        String fileName = "MyPresentation.pptx";

        slidesApi.deleteWatermark(fileName, null, null, null, null);
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

$fileName = "MyPresentation.pptx";

$slidesApi->deleteWatermark($fileName);
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

file_name = "MyPresentation.pptx"

slides_api.delete_watermark(file_name)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"

slides_api.delete_watermark(file_name)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

var fileName = "MyPresentation.pptx";

slidesApi.deleteWatermark(fileName).then(() => {
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto fileName = L"MyPresentation.pptx";

    slidesApi->deleteWatermark(fileName).get();
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

my %parameters = (name => "MyPresentation.pptx");

$slides_api->delete_watermark(%parameters);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **DeleteWatermarkOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/watermark/delete|POST|Deletes watermark shapes from the presentation saved to a local file.|[DeleteWatermarkOnline](https://reference.aspose.cloud/slides/#/Watermark/DeleteWatermarkOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|shapeName|string|query|false|The name of the watermark shapes. If the value is `null`, the default value of "watermark" is used.|
|password|string|header|false|The password to open the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete watermark shapes from the document **MyPresentation.pptx** saved to a local file.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Watermarks**

```sh
curl POST "https://api.aspose.cloud/v3.0/slides/watermark/delete" \
     -H "authorization: Bearer MyAccessToken" \
     -F "file=@MyPresentation.pptx" \
     -o Output.pptx
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

file

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System.IO;
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var inputFilePath = "MyPresentation.pptx";
        var outputFilePath = "Output.pptx";

        // Remove the watermark shapes.
        using var inputStream = File.OpenRead(inputFilePath);
        using var outputStream = slidesApi.DeleteWatermarkOnline(inputStream);

        // Save the output document.
        using var resultStream = File.OpenWrite(outputFilePath);
        outputStream.CopyTo(resultStream);
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

        String inputFilePath = "MyPresentation.pptx";

        // Remove the watermark shapes.
        byte[] inputData = Files.readAllBytes(Paths.get(inputFilePath));
        File outputFile = slidesApi.deleteWatermarkOnline(inputData, null, null);

        System.out.println("The output file was saved to " + outputFile.getPath());
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

$inputFilePath = "MyPresentation.pptx";

// Remove the watermark shapes.
$inputStream = fopen($inputFilePath, "r");
$outputFile = $slidesApi->deleteWatermarkOnline($inputStream);

echo "The output file was saved to ", $outputFile->getPathname();
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

input_file_path = "MyPresentation.pptx"
output_file_path = "Output.pptx"

# Remove the watermark shapes.
input_data = File.binread(input_file_path)
output_data = slides_api.delete_watermark_online(input_data)

# Save the output document.
File.binwrite(output_file_path, output_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

input_file_path = "MyPresentation.pptx"

# Remove the watermark shapes.
with open(input_file_path, "rb") as input_stream:
    output_file_path = slides_api.delete_watermark_online(input_stream)

print("The output file was saved to", output_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const inputFilePath = "MyPresentation.pptx";
const outputFilePath = "Output.pptx";

// Remove the watermark shapes.
const inputStream = fs.createReadStream(inputFilePath);
slidesApi.deleteWatermarkOnline(inputStream).then(response => {
    // Save the output document.
    fs.writeFile(outputFilePath, response.body, error => {
        if (error) throw error;
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
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto inputFilePath = L"MyPresentation.pptx";
    auto outputFilePath = L"Output.pptx";

    // Prepare request data with the presentation.
    auto inputStream = std::make_shared<std::ifstream>(inputFilePath, std::ios::binary);
    auto inputContent = std::make_shared<HttpContent>();
    inputContent->setData(inputStream);

    // Remove the watermark shapes.
    auto outputContent = slidesApi->deleteWatermarkOnline(inputContent).get();

    // Save the output document.
    std::ofstream outputStream(outputFilePath, std::ofstream::binary);
    outputContent.writeTo(outputStream);
}
```

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

my $input_file_path = "MyPresentation.pptx";
my $output_file_path = "Output.pptx";

# Remove the watermark shapes.
my $input_data = read_file($input_file_path, { binmode => ":raw" });
my %parameters = (document => $input_data);
my $output_data = $slides_api->delete_watermark_online(%parameters);

# Save the output document.
write_file($output_file_path, {binmode => ":raw"}, $output_data);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
