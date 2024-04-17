---
title: "Convert Using a Custom Size"
type: docs
url: /convert-using-a-custom-size/
weight: 40
---

## **Introduction**

You can use [conversion options](/slides/conversion-options/) to specify a custom slide size when [converting presentations](/slides/convert-presentations/) to other formats.

## **cURL Example**

Convert **MyPresentation.pptx** file to **480x360** PNG images.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Convert the Presentation**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/convert/png" \
     -H "authorization: Bearer <access_token>" \
     -F "file=@MyPresentation.pptx" \
     -F "data=@options.json;filename=" \
     -o MyPresentation.zip
```

options.json file:
```json
{
    "width": 480,
    "height": 360
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{response-data}
```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**

Convert **MyPresentation.pptx** file to **480x360** PNG images.

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

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

        // Set the size for output images.
        var options = new ImageExportOptions { Width = 480, Height = 360 };

        // Convert the presentation to the images.
        using var presentationStream = File.OpenRead("MyPresentation.pptx");
        using var responseStream = api.Convert(presentationStream, ExportFormat.Png, options: options);

        using var outputStream = File.Create("MyPresentation.zip");
        responseStream.CopyTo(outputStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws IOException, ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_key");

        // Set the size for output images.
        ImageExportOptions options = new ImageExportOptions();
        options.setWidth(480);
        options.setHeight(360);

        // Convert the presentation to the images.
        byte[] presentationData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        File outputFile = slidesApi.convert(presentationData, ExportFormat.PNG, null, null, null, null, options);

        System.out.println("The file with images was saved to: " + outputFile.toPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ImageExportOptions;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

// Set the size for output images.
$options = new ImageExportOptions();
$options->setWidth(480);
$options->setHeight(360);

// Convert the presentation to the images.
$presentationFile = fopen("MyPresentation.pptx", 'r');
$outputFile = $slidesApi->convert($presentationFile, ExportFormat::PNG, null, null, null, null, $options);

print("The file with images was saved to " . $outputFile->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_key"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Set the size for output images.
options = AsposeSlidesCloud::ImageExportOptions.new
options.width = 480
options.height = 360

# Convert the presentation to the images.
presentation_data = File.binread("MyPresentation.pptx")
output_data = slides_api.convert(presentation_data, ExportFormat::PNG, nil, nil, nil, nil, options)

File.binwrite("MyPresentation.zip", output_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.image_export_options import ImageExportOptions
from asposeslidescloud.models.export_format import ExportFormat

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

# Set the size for output images.
options = ImageExportOptions()
options.width = 480
options.height = 360

# Convert the presentation to the images.
with open("MyPresentation.pptx", "rb") as presentation_file:
    output_path = slides_api.convert(presentation_file.read(), ExportFormat.PNG, None, None, None, None, options)

print("The file with images was saved to: " + output_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key");

// Set the size for output images.
const options = new cloud.ImageExportOptions();
options.width = 480;
options.height = 360;

// Convert the presentation to the images.
const presentationStream = fs.createReadStream("MyPresentation.pptx");
slidesApi.convert(presentationStream, "png", null, null, null, null, options).then(response => {
    fs.writeFile("MyPresentation.zip", response.body, (error) => {
        if (error) throw error;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-go

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "my_client_id"
cfg.AppKey = "my_client_key"
api := asposeslidescloud.NewAPIClient(cfg)

// Set the size for output images.
options := asposeslidescloud.NewImageExportOptions()
options.Width = 480
options.Height = 360

source, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

// Convert the presentation to the images.
result, _, e := api.SlidesApi.Convert(source, "png", "", "", "", nil, options)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("The file with images was saved to  %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/ImageExportOptions.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

    // Set the size for output images.
    auto options = std::make_shared<ImageExportOptions>();
    options->setWidth(480);
    options->setHeight(360);

    auto presentationStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto presentationContent = std::make_shared<HttpContent>();
    presentationContent->setData(presentationStream);

    // Convert the presentation to the images.
    auto responseContent = slidesApi->convert(
        presentationContent, to_string_t("png"), utility::string_t(), utility::string_t(), utility::string_t(), {}, options).get();

    std::ofstream outputStream("MyPresentation.zip", std::ofstream::binary);
    responseContent.writeTo(outputStream);

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
