---
title: "Saving a Presentation in a Specified Format in a Storage"
type: docs
url: /saving-a-presentation-in-a-specified-format-in-a-storage/
weight: 40
---

## **Introduction**

The following method allows you to covert a PowerPoint presentation located in a Cloud Storage to a desired format and save the result to the storage. 

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/{format}|PUT|Converts a presentation located in a storage to a specified format and saves the result to the storage.|[SavePresentation](https://apireference.aspose.cloud/slides/#/Document/SavePresentation)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the presentation.|
|format|string|path|true|The desired format for the conversion.|
|outPath|string|query|true|The output file path to save the result in the storage.|
|options|object|body|false|The format-specific options for the conversion.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder path where the presentation is located.|
|storage|string|query|false|The name of the storage where the presentation is located.|
|fontsFolder|string|query|false|The path to the storage folder containing external fonts.|
|slides|string|query|false|The 1-based indices of the slides to be saved. If it is not specified, all slides are saved by default.|

To use **fontsFolder** parameter, you can create storage folders and upload font files to them using Slides Cloud API.

You can [convert parts of presentations](/slides/convert-selected-document-slides/) using the optional **slides** parameter.

You can specify [format-specific options](/slides/conversion-options/) using the **options** parameter.

{{% alert color="primary" %}}

If the slides of the presentation are converted to separate images (for example, PNG, JPG, etc.), the result will be a ZIP archive, and the `.zip` extension will be added to the output file name.

{{% /alert %}}

## **cURL Examples**

Convert **MyFolder/example.pptx** presentation located in **MyStorage** storage and save it to **MyImages/output.tiff** file into the same storage. The document should only contain the slides with indexes **1** and **3**. The slides should contain slide notes in the output file.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/example.pptx/Tiff?outPath=MyImages/output.tiff&folder=MyFolder&storage=MyStorage&slides=1,3" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -H "accept: application/json" \
     -d "{ 'NotesPosition':'BottomFull' }"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

no data

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**

Convert **MyFolder/example.pptx** presentation located in **MyStorage** storage and save it to **MyImages/output.tiff** file into the same storage. The document should only contain the slides with indexes **1** and **3**. The slides should contain slide notes in the output file.

{{< tabs tabTotal="11" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System.Collections.Generic;
using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Test
{
    static void Main()
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        // Slide notes should be added at the bottom of pages.
        var tiffOptions = new TiffExportOptions { NotesPosition = TiffExportOptions.NotesPositionEnum.BottomFull };

        // The TIFF file should only contain the slides with indexes 1 and 3.
        var slideIndices = new List<int> { 1, 3 };

        // Save the presentation to TIFF file.
        slidesApi.SavePresentation("example.pptx", ExportFormat.Tiff, "MyImages/output.tiff", tiffOptions, null, "MyFolder", "MyStorage", null, slideIndices);
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
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        // Slide notes should be added at the bottom of pages.
        var tiffOptions = new TiffExportOptions();
        tiffOptions.setNotesPosition(TiffExportOptions.NotesPositionEnum.BOTTOMFULL);

        // The TIFF file should only contain the slides with indexes 1 and 3.
        var slideIndices = Arrays.asList(1, 3);

        // Save the presentation to TIFF file.
        slidesApi.savePresentation("example.pptx", ExportFormat.TIFF, "MyImages/output.tiff", tiffOptions, null, "MyFolder", "MyStorage", null, slideIndices);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\TiffExportOptions;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

// Slide notes should be added at the bottom of pages.
$tiffOptions = new TiffExportOptions();
$tiffOptions->setNotesPosition("BottomFull");

// The TIFF file should only contain the slides with indexes 1 and 3.
$slideIndices = [1, 3];

// Save the presentation to TIFF file.
$slidesApi->savePresentation("example.pptx", ExportFormat::TIFF, "MyImages/output.tiff", $tiffOptions, null, "MyFolder", "MyStorage", null, $slideIndices);
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

# Slide notes should be added at the bottom of pages.
tiff_options = TiffExportOptions.new
tiff_options.notes_position = "BottomFull"

# The TIFF file should only contain the slides with indexes 1 and 3.
slide_indices = [1, 3]

# Save the presentation to TIFF file.
slides_api.save_presentation("example.pptx", ExportFormat::TIFF, "MyImages/output.tiff", tiff_options, nil, "MyFolder", "MyStorage", nil, slide_indices)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.tiff_export_options import TiffExportOptions
from asposeslidescloud.models.export_format import ExportFormat

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

# Slide notes should be added at the bottom of pages.
tiff_options = TiffExportOptions()
tiff_options.notes_position = "BottomFull"

# The TIFF file should only contain the slides with indexes 1 and 3.
slide_indices = [1, 3]

# Save the presentation to TIFF file.
slides_api.save_presentation("example.pptx", ExportFormat.TIFF, "MyImages/output.tiff", tiff_options, None, "MyFolder", "MyStorage", None, slide_indices)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

// Slide notes should be added at the bottom of pages.
const tiffOptions = new cloud.TiffExportOptions()
tiffOptions.notesPosition = "BottomFull"

// The TIFF file should only contain the slides with indexes 1 and 3.
const slideIndices = [1, 3]

// Save the presentation to TIFF file.
slidesApi.savePresentation("example.pptx", cloud.ExportFormat.Tiff, "MyImages/output.tiff", tiffOptions, null, "MyFolder", "MyStorage", null, slideIndices).then(() => {
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

        // Slide notes should be added at the bottom of pages.
        var tiffOptions = new TiffExportOptions();
        tiffOptions.setNotesPosition(TiffExportOptions.NotesPositionEnum.BOTTOMFULL);

        // The TIFF file should only contain the slides with indexes 1 and 3.
        var slideIndices = Arrays.asList(1, 3);

        // Save the presentation to TIFF file.
        slidesApi.savePresentation("example.pptx", ExportFormat.TIFF, "MyImages/output.tiff", tiffOptions, null, "MyFolder", "MyStorage", null, slideIndices);
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/TiffExportOptions.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

    // Slide notes should be added at the bottom of pages.
    auto tiffOptions = std::make_shared<TiffExportOptions>();
    tiffOptions->setNotesPosition(to_string_t("BottomFull"));

    // The TIFF file should only contain the slides with indexes 1 and 3.
    auto slideIndices = { 1, 3 };

    // Save the presentation to TIFF file.
    slidesApi->savePresentation(to_string_t("example.pptx"), to_string_t("tiff"), to_string_t("MyImages/output.tiff"), tiffOptions, 
        utility::string_t(), to_string_t("MyFolder"), to_string_t("MyStorage"), utility::string_t(), slideIndices).get();

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