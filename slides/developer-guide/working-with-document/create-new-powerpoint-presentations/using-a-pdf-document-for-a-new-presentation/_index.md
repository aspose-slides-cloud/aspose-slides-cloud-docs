---
title: "Using a PDF Document for a New Presentation"
type: docs
url: /using-a-pdf-document-for-a-new-presentation/
weight: 60
---

## **Introduction**
The following method allows you to create a PowerPoint presentation from a PDF document. This method can also be used to append a PDF document to an existing presentation.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/fromPdf|POST|Creates a new presentation from a PDF document.|[ImportFromPdf](https://apireference.aspose.cloud/slides/#/Document/ImportFromPdf)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the new presentation or existing one.|
|pdf|file|formData|true|The input data of a PDF document.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder path where the presentation is located.|
|storage|string|query|false|The storage name where the presentation is located.|

## **cURL Examples**
Create a new presentation **Data/summary.pptx** in a **Main** storage from a PDF document **report.pdf**.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/summary.pptx/fromPdf?folder=Data&storage=Main" \
     -H "accept: application/json" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: multipart/form-data" \
     -F "file=@report.pdf"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "documentProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/documentProperties?folder=Data",
        "relation": "self"
    },
    "viewProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/viewProperties?folder=Data",
        "relation": "self"
    },
    "slides": {
        "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/slides?folder=Data",
        "relation": "self"
    },
    "images": {
        "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/images?folder=Data",
        "relation": "self"
    },
    "layoutSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/layoutSlides?folder=Data",
        "relation": "self"
    },
    "masterSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/masterSlides?folder=Data",
        "relation": "self"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx?folder=Data",
        "relation": "self"
    },
    "alternateLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/odp?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Odp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/fodp?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Fodp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/ppt?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Ppt"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/pdf?folder=Data",
            "relation": "alternate",
            "linkType": "application/pdf",
            "title": "Download as Pdf"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/tiff?folder=Data",
            "relation": "alternate",
            "linkType": "image/tiff",
            "title": "Download as Tiff"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/xps?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-xpsdocument",
            "title": "Download as Xps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/pps?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/ppsx?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "title": "Download as Ppsx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/pptm?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "title": "Download as Pptm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/ppsm?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "title": "Download as Ppsm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/pot?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pot"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/potx?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
            "title": "Download as Potx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/potm?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
            "title": "Download as Potm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/otp?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation-template",
            "title": "Download as Otp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/summary.pptx/html?folder=Data",
            "relation": "alternate",
            "linkType": "text/html",
            "title": "Download as Html"
        }
    ]
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDK Examples**
Create a new presentation **Data/summary.pptx** in a **Main** storage from a PDF document **report.pdf**.

{{< tabs tabTotal="11" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

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
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        using (var pdfStream = File.OpenRead("test.pdf"))
        {
            var response = api.ImportFromPdf("summary.pptx", pdfStream);
            Console.WriteLine(response.SelfUri.Href); // https://api.aspose.cloud/v3.0/slides/summary.pptx
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

        var pdfData = Files.readAllBytes(Paths.get("report.pdf"));
        var response = slidesApi.importFromPdf("summary.pptx", pdfData, null, "Data", "Main");

        System.out.println(response.getSelfUri().getHref()); // https://api.aspose.cloud/v3.0/slides/summary.pptx?folder=Data
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

$pdfSteam = fopen("report.pdf", 'r');
$response = $slidesApi->importFromPdf("summary.pptx", $pdfSteam, null, "Data", "Main");

echo $response->getSelfUri()->getHref(); // https://api.aspose.cloud/v3.0/slides/summary.pptx?folder=Data
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

pdf_data = File.binread("report.pdf")
response = slides_api.import_from_pdf("summary.pptx", pdf_data, nil, "Data", "Main")

print response.self_uri.href # https://api.aspose.cloud/v3.0/slides/summary.pptx?folder=Data
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

with open("report.pdf", "rb") as pdf_stream:
    response = slides_api.import_from_pdf("summary.pptx", pdf_stream, None, "Data", "Main")

print(response.self_uri.href) # https://api.aspose.cloud/v3.0/slides/summary.pptx?folder=Data
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

const pdfStream = fs.createReadStream("report.pdf")

slidesApi.importFromPdf("summary.pptx", pdfStream, null, "Data", "Main").then((response) => {
    console.log(response.body.selfUri.href) // https://api.aspose.cloud/v3.0/slides/summary.pptx?folder=Data
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

        var pdfData = Files.readAllBytes(Paths.get("report.pdf"));
        var response = slidesApi.importFromPdf("summary.pptx", pdfData, null, "Data", "Main");

        System.out.println(response.getSelfUri().getHref()); // https://api.aspose.cloud/v3.0/slides/summary.pptx?folder=Data
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

    auto pdfStream = std::make_shared<std::ifstream>("report.pdf", std::ios::binary);

    auto pdfContent = std::make_shared<HttpContent>();
    pdfContent->setData(pdfStream);

    auto response = slidesApi->importFromPdf(
        to_string_t("summary.pptx"), pdfContent, utility::string_t(), to_string_t("Data"), to_string_t("Main")).get();

    std::cout << to_utf8string(response->getSelfUri()->getHref()); // https://api.aspose.cloud/v3.0/slides/summary.pptx?folder=Data

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

## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
