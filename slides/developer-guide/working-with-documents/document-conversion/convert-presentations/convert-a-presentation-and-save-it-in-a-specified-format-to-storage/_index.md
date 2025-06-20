---
title: "Convert a Presentation and Save It in a Specified Format to Storage"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- convert a presentation
- export a presentation
- PPT to PDF
- PPT to BMP
- PPT to GIF
- PPT to HTML
- PPT to HTML 5
- PPT to JPG
- PPT to PNG
- PPT to PPTX
- PPT to SVG
- PPT to MPEG-4
- PPT to SWF
- PPT to TIFF
- PPT to XAML
- PPT to XPS
- PPT to MD
- PPT to EMF
type: docs
url: /convert-a-presentation-and-save-it-in-a-specified-format-to-storage/
weight: 20
---

## **Introduction**

The following method allows you to transfer a PowerPoint presentation from a local file to a Cloud Storage, convert the presentation to a desired format and save the result in the storage.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/convert/{format}|PUT|Converts a passed presentation to a specified format and saves the result to the storage.|[ConvertAndSave](https://apireference.aspose.cloud/slides/#/Document/ConvertAndSave)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The data of the presentation.|
|format|string|path|true|The desired format for the conversion.|
|outPath|string|query|true|The output file path to save the result in the storage.|
|password|string|header|false|The password to open the presentation.|
|storage|string|query|false|The name of the storage where the result will be located.|
|fontsFolder|string|query|false|The path to the storage folder containing the external fonts.|
|slides|string|query|false|The 1-based indices of the slides to be converted. If it is not specified, all slides are converted by default.|
|options|object|body|false|The format-specific options for the conversion.|

To use **fontsFolder** parameter, you can create storage folders and upload font files to them using Slides Cloud API.

You can [convert parts of presentations](/slides/convert-selected-slides/) using the optional **slides** parameter.

You can specify [format-specific options](/slides/conversion-options/) using the **options** parameter.

{{% alert color="primary" %}}

If the slides of the presentation are converted to separate images (for example, PNG, JPG, etc.), the result will be a ZIP archive, and the `.zip` extension will be added to the output file name.

{{% /alert %}}

## **cURL Examples**

Convert **example.pptx** presentation from a local file to PNG images and save the result to **MyFolder/images.zip** file in **MyStorage** storage.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/convert/Png?outPath=MyFolder/images&storage=MyStorage" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/octet-stream" \
     -H "accept: application/json" \
     --data-binary @example.pptx
```

{{< /tab >}}

{{< tab tabNum="2" >}}

no data

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**

Convert **example.pptx** presentation from a local file to PNG images and save the result to **MyFolder/images.zip** file in **MyStorage** storage.

{{< tabs tabTotal="11" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System.IO;

class Test
{
    static void Main(string[] args)
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        using var fileStream = File.OpenRead("example.pptx");
        api.ConvertAndSave(fileStream, ExportFormat.Png, "MyFolder/images");
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_key");

        byte[] fileData = Files.readAllBytes(Paths.get("example.pptx"));
        slidesApi.convertAndSave(fileData, ExportFormat.PNG, "MyFolder/images", null, "MyStorage", null, null, null);
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

$fileStream = fopen("example.pptx", 'r');
$slidesApi->convertAndSave($fileStream, "png", "MyFolder/images", null, "MyStorage");
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require 'aspose_slides_cloud'

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_key"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

file_data = File.binread("example.pptx")
slides_api.convert_and_save(file_data, "png", "MyFolder/images", nil, "MyStorage")
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

with open("example.pptx", "rb") as file_stream:
    slides_api.convert_and_save(file_stream, "png", "MyFolder/images", None, "MyStorage")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key");

const fileStream = fs.createReadStream("example.pptx");
slidesApi.convertAndSave(fileStream, "png", "MyFolder/images", null, "MyStorage").then(() => {
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var fileData = Files.readAllBytes(Paths.get("example.pptx"));
        slidesApi.convertAndSave(fileData, ExportFormat.PNG, "MyFolder/images", null, "MyStorage", null, null, null);
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
       
    auto fileStream = std::make_shared<std::ifstream>("example.pptx", std::ios::binary);
    auto fileContent = std::make_shared<HttpContent>();
    fileContent->setData(fileStream);

    slidesApi->convertAndSave(fileContent, to_string_t("png"), to_string_t("MyFolder/images"), utility::string_t(), to_string_t("MyStorage")).get();

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
