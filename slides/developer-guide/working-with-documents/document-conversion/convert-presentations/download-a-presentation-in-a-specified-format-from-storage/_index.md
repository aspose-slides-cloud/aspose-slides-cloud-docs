---
title: "Download a Presentation in a Specified Format from Storage"
type: docs
url: /download-a-presentation-in-a-specified-format-from-storage/
weight: 30
---

## **Introduction**

The following method allows you to download a PowerPoint presentation located in a Cloud Storage in a desired format.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/{format}|POST|Converts a presentation located in a storage to a specified format and returns the result.|[DownloadPresentation](https://apireference.aspose.cloud/slides/#/Document/DownloadPresentation)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the presentation.|
|format|string|path|true|The desired format for the conversion.|
|options|object|body|false|The format-specific options for the conversion.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder path where the presentation is located.|
|storage|string|query|false|The name of the storage where the presentation is located.|
|fontsFolder|string|query|false|The path to the storage folder containing external fonts.|
|slides|string|query|false|The 1-based indices of the slides to be saved. If it is not specified, all slides are saved by default.|

To use **fontsFolder** parameter, you can create storage folders and upload font files to them using Slides Cloud API.

You can [convert parts of presentations](/slides/convert-selected-slides/) using the optional **slides** parameter.

You can specify [format-specific options](/slides/conversion-options/) using the **options** parameter.

{{% alert color="primary" %}}

If the slides of the presentation are converted to separate images (for example, PNG, JPG, etc.), the result will be a ZIP archive, and the `.zip` extension will be added to the output file name.

{{% /alert %}}

## **cURL Examples**

Download **MyFolder/example.pptx** presentation from **MyStorage** storage and save it as **output.html** document. The document should only contain the slides with indexes **2** and **4**. The **Helvetica** font should be used in case a presentation font is not found.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/example.pptx/Html?folder=MyFolder&storage=MyStorage&slides=2,4" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -H "accept: multipart/form-data" \
     -d "{'DefaultRegularFont': 'Helvetica'}" \
     -o output.html
```

{{< /tab >}}

{{< tab tabNum="2" >}}

file data

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**

Download **MyFolder/example.pptx** presentation from **MyStorage** storage and save it in HTML format. The document should only contain slides with indexes **2** and **4**. The **Helvetica** font should be used in case some presentation fonts are not found.

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

        // Use the Helvetica font if any presentation font is not found.
        var htmlOptions = new HtmlExportOptions { DefaultRegularFont = "Helvetica" };

        // The HTML document should only contain the slides with indexes 2 and 4.
        var slideIndices = new List<int> { 2, 4 };

        // Export the presentation to HTML document and download the result.
        using var htmlStream = api.DownloadPresentation(
            "example.pptx", ExportFormat.Html, htmlOptions, slides: slideIndices);

        // Save the HTML document to output.html file.
        using Stream outputStream = File.Create("output.html");
        htmlStream.CopyTo(outputStream);
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

import java.util.Arrays;

public class Main {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_key");

        // Use the Helvetica font if any presentation font is not found.
        HtmlExportOptions htmlOptions = new HtmlExportOptions();
        htmlOptions.setDefaultRegularFont("Helvetica");

        // The HTML document should only contain the slides with indexes 2 and 4.
        ArrayList slideIndices = new ArrayList(Arrays.asList(2, 4));

        // Export the presentation to HTML document and download the result.
        File response = slidesApi.downloadPresentation(
            "example.pptx", ExportFormat.HTML, htmlOptions, null, "MyFolder", "MyStorage", null, slideIndices);

        System.out.println("The HTML document was saved to " + response.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\HtmlExportOptions;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

// Use the Helvetica font if any presentation font is not found.
$htmlOptions = new HtmlExportOptions();
$htmlOptions->setDefaultRegularFont("Helvetica");

// The HTML document should only contain the slides with indexes 2 and 4.
$slideIndices = [2, 4];

// Export the presentation to HTML document and download the result.
$response = $slidesApi->downloadPresentation(
    "example.pptx", ExportFormat::HTML, $htmlOptions, null, "MyFolder", "MyStorage", null, $slideIndices);

print("The HTML document was saved to " . $response->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_key"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Use the Helvetica font if any presentation font is not found.
html_options = AsposeSlidesCloud::HtmlExportOptions.new
html_options.default_regular_font = "Helvetica"

# The HTML document should only contain the slides with indexes 2 and 4.
slide_indices = [2, 4]

# Export the presentation to HTML document and download the result.
html_data = slides_api.download_presentation(
    "example.pptx", "html", html_options, nil, "MyFolder", "MyStorage", nil, slide_indices)

# Save the HTML document to output.html file.
File.binwrite("output.html", html_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.html_export_options import HtmlExportOptions
from asposeslidescloud.models.export_format import ExportFormat

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

# Use the Helvetica font if any presentation font is not found.
html_options = HtmlExportOptions()
html_options.default_regular_font = "Helvetica"

# The HTML document should only contain the slides with indexes 2 and 4.
slide_indices = [2, 4]

# Export the presentation to HTML document and download the result.
html_path = slides_api.download_presentation(
    "example.pptx", ExportFormat.HTML, html_options, None, "MyFolder", "MyStorage", None, slide_indices)

print('The HTML document was saved to ' + html_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

// Use the Helvetica font if any presentation font is not found.
const htmlOptions = new cloud.HtmlExportOptions()
htmlOptions.defaultRegularFont = "Helvetica"

// The HTML document should only contain the slides with indexes 2 and 4.
const slideIndices = [2, 4]

// Export the presentation to HTML document and download the result.
slidesApi.downloadPresentation("example.pptx", cloud.ExportFormat.Html, htmlOptions, null, "MyFolder", "MyStorage", null, slideIndices).then((response) => {

    // Save the HTML document to output.html file.
    fs.writeFile("output.html", response.body, (error) => {
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

import java.util.Arrays;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        // Use the Helvetica font if any presentation font is not found.
        var htmlOptions = new HtmlExportOptions();
        htmlOptions.setDefaultRegularFont("Helvetica");

        // The HTML document should only contain the slides with indexes 2 and 4.
        var slideIndices = Arrays.asList(2, 4);

        // Export the presentation to HTML document and download the result.
        var response = slidesApi.downloadPresentation(
            "example.pptx", ExportFormat.HTML, htmlOptions, null, "MyFolder", "MyStorage", null, slideIndices);

        System.out.println("The HTML document was saved to " + response.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/HtmlExportOptions.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

    // Use the Helvetica font if any presentation font is not found.
    auto htmlOptions = std::make_shared<HtmlExportOptions>();
    htmlOptions->setDefaultRegularFont(to_string_t("Helvetica"));

    // The HTML document should only contain the slides with indexes 2 and 4.
    auto slideIndices = { 2, 4 };

    // Export the presentation to HTML document and download the result.
    auto htmlContent = slidesApi->downloadPresentation(
        to_string_t("example.pptx"), to_string_t("html"), htmlOptions, utility::string_t(), to_string_t("MyFolder"), to_string_t("MyStorage"), utility::string_t(), slideIndices).get();

    // Save the HTML document to output.html file.
    std::ofstream htmlStream(to_string_t("output.html"), std::ofstream::binary);
    htmlContent.writeTo(htmlStream);

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
