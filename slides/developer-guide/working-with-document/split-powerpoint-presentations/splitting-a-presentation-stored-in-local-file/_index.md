---
title: "Splitting a Presentation Stored in Local File"
type: docs
url: /splitting-a-presentation-stored-in-local-file/
weight: 20
---

## **Introduction**

The article shows you how to split a PowerPoint presentation stored in a local file and receive splitted parts.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/split/{format}|POST|Splits a presentation file stored in a local file and returns the result.|[SplitOnline](https://apireference.aspose.cloud/slides/#/Document/SplitOnline)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|format|string|path|true|The format for output files. See [the table](/slides/split-powerpoint-presentations#available-formats-for-output-files/) for available formats. The default value is `jpeg`.|
|width|integer|query|false|The width of each slide in the output files. Does not affect the HTML format.|
|height|integer|query|false|The height of each slide in the output files. Does not affect the HTML format.|
|from|integer|query|false|The 1-based starting slide number for the splitting. If it is not specified, the splitting starts from the first slide of the presentation.|
|to|integer|query|false|The 1-based last slide number for the splitting. If it is not specified, the splitting ends at the last slide of the presentation.|
|password|string|header|false|The password to open the presentation.|
|storage|string|query|false|The name of the storage where the presentation is saved. If it is not specified, the default storage is assumed.|
|fontsFolder|string|query|false|The path to the storage folder containing custom fonts that can be used in the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{% alert color="primary" %}} 

The `SplitOnline` method returns the output files as a ZIP archive.

{{% /alert %}} 

## **Splitting a Range of Slides**

Split the 2nd and 3rd slides from **MyPresentation.pptx** file and receive the output slides in PDF format.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Split the Presentation**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/split/Pdf?from=2&to=3" \
     -H "authorization: Bearer <access_token>" \
     -F "file=@MyPresentation.pptx" \
     -o output.zip
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{response-data}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System.IO;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split the 2nd and 3rd slides and save them to PDF documents.
        using var presentationStream = File.OpenRead("MyPresentation.pptx");
        using var responseStream = slidesApi.SplitOnline(presentationStream, SlideExportFormat.Pdf, from: 2, to: 3);

        // Save the output stream to a ZIP file.
        using var outputStream = File.Create("output.zip");
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
import com.aspose.slides.model.SlideExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Application {
    public static void main(String[] args) throws IOException, ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split the 2nd and 3rd slides and save them to PDF documents.
        var presentationData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        var responseFile = slidesApi.splitOnline(presentationData, SlideExportFormat.PDF, null, null, 2, 3, null, null, null);

        System.out.println("The output ZIP file was saved to " + responseFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Split the 2nd and 3rd slides and save them to PDF documents.
$presentationStream = fopen("MyPresentation.pptx", "r");
$responseFile = $slidesApi->splitOnline($presentationStream, SlideExportFormat::PDF, null, null, 2, 3);

print("The output ZIP file was saved to " . $responseFile->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_secret"

slides_api = SlidesApi.new(configuration)

# Split the 2nd and 3rd slides and save them to PDF documents.
presentation_data = File.binread("MyPresentation.pptx")
output_data = slides_api.split_online(presentation_data, SlideExportFormat::PDF, nil, nil, 2, 3)

# Save the output data to a ZIP file.
File.binwrite("output.zip", output_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_export_format import SlideExportFormat

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Split the 2nd and 3rd slides and save them to PDF documents.
with open("MyPresentation.pptx", "rb") as presentation_stream:
    output_path = slides_api.split_online(presentation_stream, SlideExportFormat.PDF, None, None, 2, 3)

print("The output ZIP file was saved to " + output_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret")

// Split the 2nd and 3rd slides and save them to PDF documents.
const presentationStream = fs.createReadStream("MyPresentation.pptx")
slidesApi.splitOnline(presentationStream, "pdf", null, null, 2, 3).then((response) => {

    // Save the output data to a ZIP file.
    fs.writeFile("output.zip", response.body, (error) => {
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
import com.aspose.slides.model.SlideExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split the 2nd and 3rd slides and save them to PDF documents.
        var presentationData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        var responseFile = slidesApi.splitOnline(presentationData, SlideExportFormat.PDF, null, null, 2, 3, null, null, null);

        System.out.println("The output ZIP file was saved to " + responseFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility;
using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_secret"));

    // Prepare a request content.
    auto presentationStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto requestContent = std::make_shared<HttpContent>();
    requestContent->setData(presentationStream);

    // Split the 2nd and 3rd slides and save them to PDF documents.
    auto responseContent = slidesApi->splitOnline(requestContent, to_string_t("pdf"), boost::none, boost::none, 2, 3).get();

    // Save the output data to a ZIP file.
    std::ofstream outputStream("output.zip", std::ofstream::binary);
    responseContent.writeTo(outputStream);

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Split the 2nd and 3rd slides and save them to PDF documents.
my $presentation_data = read_file("MyPresentation.pptx", { binmode => ":raw" });
my %split_params = ("document" => $presentation_data, "format" => "pdf", "from" => 2, "to" => 3);
my $output_data = $slides_api->split_online(%split_params);

# Save the output data to a ZIP file.
write_file("output.zip", {binmode => ":raw"}, $output_data);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
