---
title: "Split a Presentation from a Local File and Save Parts to Storage"
keywords: "PowerPoint, presentation, REST API, Cloud API, split a presentation, split slides"
type: docs
url: /split-a-presentation-from-a-local-file-and-save-parts-to-storage/
weight: 30
---

## **Introduction**

The article shows you how to split a PowerPoint presentation stored in a local file and save the splitted parts to a storage.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/split/{format}|PUT|Splits a presentation file stored in a local file and saves the result in a storage.|[SplitAndSaveOnline](https://apireference.aspose.cloud/slides/#/Document/SplitAndSaveOnline)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|format|string|path|true|The format for output files. See [the table](/slides/split-presentations#available-formats-for-output-files/) for available formats. The default value is `jpeg`.|
|destFolder|string|query|false|The storage folder where the output files will be uploaded. If it is not specified, the files will be uploaded to the folder where the presentation is saved.|
|width|integer|query|false|The width of each slide in the output files. Does not affect the HTML format.|
|height|integer|query|false|The height of each slide in the output files. Does not affect the HTML format.|
|from|integer|query|false|The 1-based starting slide number for the splitting. If it is not specified, the splitting starts from the first slide of the presentation.|
|to|integer|query|false|The 1-based last slide number for the splitting. If it is not specified, the splitting ends at the last slide of the presentation.|
|password|string|header|false|The password to open the presentation.|
|storage|string|query|false|The name of the storage where the presentation is saved. If it is not specified, the default storage is assumed.|
|fontsFolder|string|query|false|The path to the storage folder containing custom fonts that can be used in the presentation.|

## **Splitting a Range of Slides**

Split the first three slides from **MyPresentation.pptx** file and save them as **480x270 bitmap** images to **MyImages** folder in **MyStorage** storage.

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
curl -X PUT "https://api.aspose.cloud/v3.0/slides/split/Bmp?destFolder=MyImages&width=480&height=270&from=1&to=3&storage=MyStorage" \
     -H "authorization: Bearer <access_token>" \
     -F "file=@MyPresentation.pptx"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "slides": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp",
            "relation": "self",
            "linkType": "image/bmp",
            "title": "Slide 1"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_2.bmp",
            "relation": "self",
            "linkType": "image/bmp",
            "title": "Slide 2"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_3.bmp",
            "relation": "self",
            "linkType": "image/bmp",
            "title": "Slide 3"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/sourcePresentation",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;
using System.IO;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Split the first three slides and save them to 480x270 bitmaps in the storage.
        using var presentationStream = File.OpenRead("MyPresentation.pptx");
        var response = api.SplitAndSaveOnline(presentationStream, SlideExportFormat.Bmp, "MyImages", 480, 270, 1, 3);

        // Print information about the result.
        foreach (var slide in response.Slides)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
            Console.WriteLine(slide.Href);
        }
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
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split the first three slides and save them to 480x270 bitmaps in the storage.
        byte[] presentationData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        SplitDocumentResult response = slidesApi.splitAndSaveOnline(presentationData, SlideExportFormat.BMP, "MyImages", 480, 270, 1, 3, null, "MyStorage", null, null);

        // Print information about the result.
        for (ResourceUri slide : response.getSlides())
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
            System.out.println(slide.getHref());
        }
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

// Split the first three slides and save them to 480x270 bitmaps in the storage.
$presentationStream = fopen("MyPresentation.pptx", "r");
$response = $slidesApi->splitAndSaveOnline($presentationStream, SlideExportFormat::BMP, "MyImages", 480, 270, 1, 3, null, "MyStorage");

// Print information about the result.
foreach ($response->getSlides() as $slide)
{
    // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
    echo $slide->getHref(), "\n";
}
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

# Split the first three slides and save them to 480x270 bitmaps in the storage.
presentation_data = File.binread("MyPresentation.pptx")
response = slides_api.split_and_save_online(presentation_data, SlideExportFormat::BMP, "MyImages", 480, 270, 1, 3, nil, "MyStorage")

# Print information about the result.
for slide in response.slides
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
    puts slide.href
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_export_format import SlideExportFormat

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Split the first three slides and save them to 480x270 bitmaps in the storage.
with open("MyPresentation.pptx", "rb") as presentation_stream:
    response = slides_api.split_and_save_online(presentation_stream, SlideExportFormat.BMP, "MyImages", 480, 270, 1, 3, None, "MyStorage")

# Print information about the result.
for slide in response.slides:
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
    print(slide.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Split the first three slides and save them to 480x270 bitmaps in the storage.
const presentationStream = fs.createReadStream("MyPresentation.pptx");
slidesApi.splitAndSaveOnline(presentationStream, "bmp", "MyImages", 480, 270, 1, 3, null, "MyStorage").then(response => {
    // Print information about the result.
    response.body.slides.forEach(slide => {
        // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
        console.log(slide.href);
    });
});
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
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split the first three slides and save them to 480x270 bitmaps in the storage.
        byte[] presentationData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        SplitDocumentResult response = slidesApi.splitAndSaveOnline(presentationData, SlideExportFormat.BMP, "MyImages", 480, 270, 1, 3, null, "MyStorage", null, null);

        // Print information about the result.
        for (ResourceUri slide : response.getSlides())
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
            System.out.println(slide.getHref());
        }
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

    // Prepare a request content for the splitting.
    auto presentationStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto requestContent = std::make_shared<HttpContent>();
    requestContent->setData(presentationStream);

    // Split the first three slides and save them to 480x270 bitmaps in the storage.
    auto responseContent = slidesApi->splitAndSaveOnline(
        requestContent, to_string_t("bmp"), to_string_t("MyImages"), 480, 270, 1, 3, string_t(), to_string_t("MyStorage")).get();

    // Print information about the result.
    for (auto slide : responseContent->getSlides())
    {
        // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
        std::cout << to_utf8string(slide->getHref()) << std::endl;
    }

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

# Split the first three slides and save them to 480x270 bitmaps in the storage.
my $presentation_data = read_file("MyPresentation.pptx", { binmode => ":raw" });
my %split_params = ("document" => $presentation_data, "format" => "bmp", "dest_folder" => "MyImages", "width" => 480, "height" => 270, "from" => 1, "to" => 3, "storage" => "MyStorage");
my $response = $slides_api->split_and_save_online(%split_params);

# Print information about the result.
for $slide (@{$response->{slides}}) {
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/sourcePresentation_1.bmp, etc.
    print $slide->{href}, "\n";
}
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
