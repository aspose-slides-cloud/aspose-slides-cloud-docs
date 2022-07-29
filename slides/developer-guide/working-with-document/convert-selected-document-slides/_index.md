---
title: "Convert Selected Document Slides"
type: docs
url: /convert-selected-document-slides/
weight: 20
---

## **Introduction**

You can [convert](/slides/convert-powerpoint-documents-to-other-file-formats/) parts of presentations using optional **slides** parameter. This parameter is a comma-separated list of slides that should be included in the output.

## **cURL Example**

Convert **MyPresentation.pptx** presentation to **MyPresentation.pdf** document. The document should only contain the slides with indexes **2** and **4**.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/convert/Pdf?slides=2,4" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/octet-stream" \
     -H "accept: multipart/form-data" \
     --data-binary @MyPresentation.pptx \
     -o MyPresentation.pdf
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

Convert **MyPresentation.pptx** presentation to a PDF document. The document should only contain the slides with indexes **2** and **4**.

{{< tabs tabTotal="11" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System.Collections.Generic;
using System.IO;

class Test
{
    static void Main(string[] args)
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        using var fileStream = File.OpenRead("MyPresentation.pptx");
        using var resultStream = api.Convert(fileStream, ExportFormat.Pdf, slides: new List<int> { 2, 4 });

        using var outputStream = File.Create("MyPresentation.pdf");
        resultStream.CopyTo(outputStream);
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
import java.util.Arrays;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var fileData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        var response = slidesApi.convert(fileData, ExportFormat.PDF, null, null, null, Arrays.asList(2, 4), null);

        System.out.println("The converted file was saved to " + response.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$fileStream = fopen("MyPresentation.pptx", 'r');
$response = $slidesApi->Convert($fileStream, ExportFormat::PDF, null, null, null, [ 2, 4 ]);

print("The converted file was saved to " . $response->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_key"

slides_api = SlidesApi.new(configuration)

file_data = File.binread("MyPresentation.pptx")
pdf_data = slides_api.convert(file_data, ExportFormat::PDF, nil, nil, nil, [2, 4])

File.binwrite("MyPresentation.pdf", pdf_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.export_format import ExportFormat

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

with open("MyPresentation.pptx", "rb") as file_stream:
    pdf_path = slides_api.convert(file_stream, ExportFormat.PDF, None, None, None, [2, 4])

print("The converted file was saved to " + pdf_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require('fs')

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

const fileStream = fs.createReadStream("MyPresentation.pptx")
slidesApi.convert(fileStream, "pdf", null, null, null, [2, 4]).then((response) => {
    fs.writeFile("MyPresentation.pdf", response.body, (error) => {
        if (error) throw error
    })
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.Arrays;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var fileData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        var response = slidesApi.convert(fileData, ExportFormat.PDF, null, null, null, Arrays.asList(2, 4), null);

        System.out.println("The converted file was saved to " + response.getPath());
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

    auto fileStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto fileContent = std::make_shared<HttpContent>();
    fileContent->setData(fileStream);

    auto responseContent = slidesApi->convert(
        fileContent, to_string_t("pdf"), utility::string_t(), utility::string_t(), utility::string_t(), {2, 4}).get();

    std::ofstream pdfStream("MyPresentation.pdf", std::ofstream::binary);
    responseContent.writeTo(pdfStream);

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
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-go

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "my_client_id"
cfg.AppKey = "my_client_key"
api := asposeslidescloud.NewAPIClient(cfg)

source, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

result, _, e := c.SlidesApi.Convert(source, "pdf", nil, nil, nil, []int32 { 2, 4 }, nil)
if e != nil {
    fmt.Printf("Error: %v.", e)
}
fmt.Printf("The converted file was saved to  %v.", result.Name())
```

{{< /tab >}}

{{< /tabs >}}
