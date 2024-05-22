---
title: "Extract a Slide"
type: docs
url: /extract-a-slide/
weight: 10
---

## **Introduction**

The following request methods allow you to easily extract a particular slide from a PowerPoint document. At the same time, the slide may be converted to a specified format. It can be PowerPoint format, image, HTML, PDF, and many others. Depending on the output format, many options may be applied for the output document. You can keep the original size of the slide or specify a different one. A password can be provided when the presentation is protected. You can use the default storage and folder where the presentation was saved or specify them in parameters.

## **DownloadSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{format}|POST|Downloads the specified slide from a presentation saved to a storage.|[DownloadSlide](https://apireference.aspose.cloud/slides/#/Slides/DownloadSlide)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of a presentation saved to a storage.|
|slideIndex|integer|path|true|The 1-based index of the slide to be downloaded.|
|format|string|path|true|The output format for the slide. See [the table](/slides/split-presentations/#available-formats-for-output-files) for available formats.|
|options|body|object|false|The export options depending on the output format. See [conversion options](/slides/conversion-options/) for the available formats.|
|width|integer|query|false|The width of the slide in output format units. The default value is 0 (used the original width).|
|height|integer|query|false|The height of the slide in output format units. The default value is 0 (used the original height).|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|fontsFolder|string|query|false|The path to the storage folder contaning custom fonts to be used with the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Extract the **third** slide from **MyFolder/MyPresentation.pptx** saved to **MyStorage** and convert it to a **540x380 TIFF** image using **24bppRGB** pixel format.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Download the Slide**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/Tiff?folder=MyFolder&storage=MyStorage" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -d @request_data.json \
     -o slide_3.tiff
```

request_data.json content:

```json
{ 
    "PixelFormat": "Format24bppRgb",
    "Width": 540,
    "Height": 380
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

TIFF file data

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
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Set options for the output TIFF image.
        var tiffOptions = new TiffExportOptions
        {
            PixelFormat = TiffExportOptions.PixelFormatEnum.Format24bppRgb,
            Width = 540,
            Height = 380
        };

        // Extract the third slide and get it in TIFF format.
        using var tiffStream = api.DownloadSlide("MyPresentation.pptx", 3, SlideExportFormat.Tiff, tiffOptions);
        
        // Save the TIFF image to a file.
        using var outputStream = File.OpenWrite("slide_3.tiff");
        tiffStream.CopyTo(outputStream);
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Set options for the output TIFF image.
        TiffExportOptions tiffOptions = new TiffExportOptions();
        tiffOptions.setPixelFormat(TiffExportOptions.PixelFormatEnum.FORMAT24BPPRGB);
        tiffOptions.setWidth(540);
        tiffOptions.setHeight(380);

        // Extract the third slide and get it in TIFF format.
        File tiffFile = slidesApi.downloadSlide("MyPresentation.pptx", 3, SlideExportFormat.TIFF, tiffOptions, null, null, null, "MyFolder", "MyStorage", null);

        System.out.println("The TIFF image was saved to " + tiffFile.getPath());
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
use Aspose\Slides\Cloud\Sdk\Model\SlideExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Set options for the output TIFF image.
$tiffOptions = new TiffExportOptions();
$tiffOptions->setPixelFormat("Format24bppRgb");
$tiffOptions->setWidth(540);
$tiffOptions->setHeight(380);

// Extract the third slide and get it in TIFF format.
$tiffFile = $slidesApi->downloadSlide("MyPresentation.pptx", 3, SlideExportFormat::TIFF, $tiffOptions, null, null, null, "MyFolder", "MyStorage");

print("The TIFF image was saved to " . $tiffFile->getPathname());
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

# Set options for the output TIFF image.
tiff_options = TiffExportOptions.new
tiff_options.pixel_format = "Format24bppRgb"
tiff_options.width = 540
tiff_options.height = 380

# Extract the third slide and get it in TIFF format.
tiff_data = slides_api.download_slide("MyPresentation.pptx", 3, SlideExportFormat::TIFF, tiff_options, nil, nil, nil, "MyFolder", "MyStorage")

# Save the TIFF image to a file.
File.binwrite("slide_3.tiff", tiff_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_export_format import SlideExportFormat
from asposeslidescloud.models.tiff_export_options import TiffExportOptions

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Set options for the output TIFF image.
tiff_options = TiffExportOptions()
tiff_options.pixel_format = "Format24bppRgb"
tiff_options.width = 540
tiff_options.height = 380

# Extract the third slide and get it in TIFF format.
tiff_path = slides_api.download_slide("MyPresentation.pptx", 3, SlideExportFormat.TIFF, tiff_options, None, None, None, "MyFolder", "MyStorage")

print("The TIFF image was saved to " + tiff_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Set options for the output TIFF image.
const tiffOptions = new cloud.TiffExportOptions();
tiffOptions.pixelFormat = "Format24bppRgb";
tiffOptions.width = 540;
tiffOptions.height = 380;

// Extract the third slide and get it in TIFF format.
slidesApi.downloadSlide("MyPresentation.pptx", 3, "tiff", tiffOptions, null, null, null, "MyFolder", "MyStorage").then(response => {
    // Save the TIFF image to a file.
    fs.writeFile("slide_3.tiff", response.body, (error) => {
        if (error) throw error;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Set options for the output TIFF image.
        TiffExportOptions tiffOptions = new TiffExportOptions();
        tiffOptions.setPixelFormat(TiffExportOptions.PixelFormatEnum.FORMAT24BPPRGB);
        tiffOptions.setWidth(540);
        tiffOptions.setHeight(380);

        // Extract the third slide and get it in TIFF format.
        File tiffFile = slidesApi.downloadSlide("MyPresentation.pptx", 3, SlideExportFormat.TIFF, tiffOptions, null, null, null, "MyFolder", "MyStorage", null);

        System.out.println("The TIFF image was saved to " + tiffFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/TiffExportOptions.h"

using namespace utility;
using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"my_client_id", L"my_client_secret");

    // Set options for the output TIFF image.
    auto tiffOptions = std::make_shared<TiffExportOptions>();
    tiffOptions->setPixelFormat(L"Format24bppRgb");
    tiffOptions->setWidth(540);
    tiffOptions->setHeight(380);

    // Extract the third slide and get it in TIFF format.
    auto responseContent = slidesApi->downloadSlide(
        L"MyPresentation.pptx", 3, L"tiff", tiffOptions, NULL, NULL, L"", L"MyFolder", L"MyStorage").get();

    // Save the TIFF image to a file.
    std::ofstream tiffStream("slide_3.tiff", std::ofstream::binary);
    responseContent.writeTo(tiffStream);
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::TiffExportOptions;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Set options for the output TIFF image.
my $tiff_options = AsposeSlidesCloud::Object::TiffExportOptions->new();
$tiff_options->{pixel_format} = "Format24bppRgb";
$tiff_options->{width} = 540;
$tiff_options->{height} = 380;

# Extract the third slide and get it in TIFF format.
my %slide_params = (name => "MyPresentation.pptx", slide_index => 3, format => "tiff", options => $tiff_options,  folder => "MyFolder", storage => "MyStorage");
my $tiff_data = $slides_api->download_slide(%slide_params);

# Save the TIFF image to a file.
write_file("slide_3.tiff", {binmode => ":raw"}, $tiff_data);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SaveSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{format}|PUT|Extracts the specified slide from a presentation saved to a storage and saves the slide to the storage.|[SaveSlide](https://apireference.aspose.cloud/slides/#/Slides/SaveSlide)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of a presentation saved to a storage.|
|slideIndex|integer|path|true|The 1-based index of the slide to be extracted from the presentation.|
|format|string|path|true|The output format for the slide. See [the table](/slides/split-presentations/#available-formats-for-output-files) for available formats.|
|options|body|object|false|The export options depending on the output format. See [conversion options](/slides/conversion-options/) for the available formats.|
|outPath|string|query|true|The output path for a slide file.|
|width|integer|query|false|The width of the slide in output format units. The default value is 0 (used the original width).|
|height|integer|query|false|The height of the slide in output format units. The default value is 0 (used the original height).|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|fontsFolder|string|query|false|The path to the storage folder contaning custom fonts to be used with the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Extract the **second** slide from **MyFolder/MyPresentation.pptx** saved to **MyStorage**, and save the slide to **MyImages/slide_2.png** file. The image must contain **slide notes** and **slide comments**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Save the Slide**

```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/Png?outPath=MyImages/slide_2.png&folder=MyFolder&storage=MyStorage" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -d @request_data.json
```

request_data.json content:

```json
{
    "NotesPosition": "BottomTruncated",
    "CommentsPosition": "Right"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

None

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Set options for the output PNG image.
        var pngOptions = new ImageExportOptions
        {
            SlidesLayoutOptions = new NotesCommentsLayoutingOptions
            {
                NotesPosition = NotesCommentsLayoutingOptions.NotesPositionEnum.BottomTruncated,
                CommentsPosition = NotesCommentsLayoutingOptions.CommentsPositionEnum.Right
            }
        };

        // Save the second slide to the PNG image.
        api.SaveSlide("MyPresentation.pptx", 2, SlideExportFormat.Png, "MyImages/slide_2.png", pngOptions);
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Set options for the output PNG image.
        NotesCommentsLayoutingOptions slidesLayoutOptions = new NotesCommentsLayoutingOptions();
        slidesLayoutOptions.setNotesPosition(NotesCommentsLayoutingOptions.NotesPositionEnum.BOTTOMTRUNCATED);
        slidesLayoutOptions.setCommentsPosition(NotesCommentsLayoutingOptions.CommentsPositionEnum.RIGHT);

        ImageExportOptions pngOptions = new ImageExportOptions();
        pngOptions.setSlidesLayoutOptions(slidesLayoutOptions);

        // Save the second slide to the PNG image.
        slidesApi.saveSlide("MyPresentation.pptx", 2, SlideExportFormat.PNG, "MyImages/slide_2.png", pngOptions, null, null, null, "MyFolder", "MyStorage", null);
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
use Aspose\Slides\Cloud\Sdk\Model\NotesCommentsLayoutingOptions;
use Aspose\Slides\Cloud\Sdk\Model\SlideExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Set options for the output PNG image.
$slidesLayoutOptions = new NotesCommentsLayoutingOptions();
$slidesLayoutOptions->setNotesPosition("BottomTruncated");
$slidesLayoutOptions->setCommentsPosition("Right");

$pngOptions = new ImageExportOptions();
$pngOptions->setSlidesLayoutOptions(slidesLayoutOptions);

// Save the second slide to the PNG image.
$slidesApi->saveSlide("MyPresentation.pptx", 2, SlideExportFormat::PNG, "MyImages/slide_2.png", $pngOptions, null, null, null, "MyFolder", "MyStorage");
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

# Set options for the output PNG image.
slides_layout_options = NotesCommentsLayoutingOptions.new
slides_layout_options.notes_position = "BottomTruncated"
slides_layout_options.comments_position = "Right"

png_options = ImageExportOptions.new
png_options.slides_layout_options = slides_layout_options

# Save the second slide to the PNG image.
slides_api.save_slide("MyPresentation.pptx", 2, SlideExportFormat::PNG, "MyImages/slide_2.png", png_options, nil, nil, nil, "MyFolder", "MyStorage")
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_export_format import SlideExportFormat
from asposeslidescloud.models.image_export_options import ImageExportOptions

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Set options for the output PNG image.
slides_layout_options = NotesCommentsLayoutingOptions()
slides_layout_options.notes_position = "BottomTruncated"
slides_layout_options.comments_position = "Right"

png_options = ImageExportOptions()
png_options.slides_layout_options = slides_layout_options

# Save the second slide to the PNG image.
slides_api.save_slide("MyPresentation.pptx", 2, SlideExportFormat.PNG, "MyImages/slide_2.png", png_options, None, None, None, "MyFolder", "MyStorage")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Set options for the output PNG image.
const slidesLayoutOptions = new cloud.NotesCommentsLayoutingOptions();
slidesLayoutOptions.notesPosition = "BottomTruncated";
slidesLayoutOptions.commentsPosition = "Right";

const pngOptions = new cloud.ImageExportOptions();
pngOptions.slidesLayoutOptions = slidesLayoutOptions;

// Save the second slide to the PNG image.
slidesApi.saveSlide("MyPresentation.pptx", 2, "png", "MyImages/slide_2.png", pngOptions, null, null, null, "MyFolder", "MyStorage").then(() => {
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Set options for the output PNG image.
        NotesCommentsLayoutingOptions slidesLayoutOptions = new NotesCommentsLayoutingOptions();
        slidesLayoutOptions.setNotesPosition(NotesCommentsLayoutingOptions.NotesPositionEnum.BOTTOMTRUNCATED);
        slidesLayoutOptions.setCommentsPosition(NotesCommentsLayoutingOptions.CommentsPositionEnum.RIGHT);

        ImageExportOptions pngOptions = new ImageExportOptions();
        pngOptions.setSlidesLayoutOptions(slidesLayoutOptions);

        // Save the second slide to the PNG image.
        slidesApi.saveSlide("MyPresentation.pptx", 2, SlideExportFormat.PNG, "MyImages/slide_2.png", pngOptions, null, null, null, "MyFolder", "MyStorage", null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/ImageExportOptions.h"
#include "asposeslidescloud/model/NotesCommentsLayoutingOptions.h"

using namespace utility;
using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"my_client_id", L"my_client_secret");

    // Set options for the output PNG image.
    auto slidesLayoutOptions = std::make_shared<NotesCommentsLayoutingOptions>();
    slidesLayoutOptions->setNotesPosition(L"BottomTruncated");
    slidesLayoutOptions->setCommentsPosition(L"Right");

    auto pngOptions = std::make_shared<ImageExportOptions>();
    pngOptions->setSlidesLayoutOptions(slidesLayoutOptions);

    // Save the second slide to the PNG image.
    slidesApi->saveSlide(
        L"MyPresentation.pptx", 2, L"png", L"MyImages/slide_2.png", pngOptions, NULL, NULL, L"", L"MyFolder", L"MyStorage").get();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::ImageExportOptions;
use AsposeSlidesCloud::Object::NotesCommentsLayoutingOptions;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Set options for the output PNG image.
my $slides_layout_options = AsposeSlidesCloud::Object::NotesCommentsLayoutingOptions->new();
$slides_layout_options->{notes_position} = "BottomTruncated";
$slides_layout_options->{comments_position} = "Right";

my $png_options = AsposeSlidesCloud::Object::ImageExportOptions->new();
$png_options->{slides_layout_options} = $slides_layout_options;

# Prepare parameters for saving the second slide to the PNG image.
my %params = (name => "MyPresentation.pptx", slide_index => 2, format => "png", out_path => "MyImages/slide_2.png", 
              options => $png_options, folder => "MyFolder", storage => "MyStorage");

# Save the slide.
$slides_api->save_slide(%params);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **DownloadSlideOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/slides/{slideIndex}/{format}|POST|Uploads a presentation to a storage and downloads the specified slide from the presentation.|[DownloadSlideOnline](https://apireference.aspose.cloud/slides/#/Slides/DownloadSlideOnline)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file data.|
|slideIndex|integer|path|true|The 1-based index of the slide to be downloaded.|
|format|string|path|true|The output format for the slide. See [the table](/slides/split-presentations/#available-formats-for-output-files) for available formats.|
|width|integer|query|false|The width of the slide in output format units. The default value is 0 (used the original width).|
|height|integer|query|false|The height of the slide in output format units. The default value is 0 (used the original height).|
|password|string|header|false|The password to open the presentation.|
|fontsFolder|string|query|false|The path to the storage folder contaning custom fonts to be used with the presentation.|
|storage|string|query|false|The name of the storage.|
|options|body|object|false|The export options depending on the output format. See [conversion options](/slides/conversion-options/) for the available formats.|

### **Examples**

Extract the **fifth** slide from **MyPresentation.pptx** and convert it to a **PDF** document using the **PDF/A-1b** standard. **Embed all font characters** in the output document and set the quality value for JPG images to **90%**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Download the Slide**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/slides/5/Pdf" \
     -H "authorization: Bearer <access_token>" \
     -F "file=@MyPresentation.pptx" \
     -F "data=@request_data.json;filename=" \
     -o slide_5.pdf
```

request_data.json content:

```json
{
    "Compliance": "PdfA1b",
    "EmbedFullFonts": "true",
    "JpegQuality": "90"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

PDF file data

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="33" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

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
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        using var fileStream = File.OpenRead("MyPresentation.pptx");

        // Set the options for the output PDF document.
        var pdfOptions = new PdfExportOptions
        {
            Compliance = PdfExportOptions.ComplianceEnum.PdfA1b,
            EmbedFullFonts = true,
            JpegQuality = 90
        };

        // Extract the 5th slide and save it to the PDF document.
        using var pdfStream = api.DownloadSlideOnline(fileStream, 5, SlideExportFormat.Pdf, options: pdfOptions);

        // Save the PDF document to a file.
        using var outputStream = File.OpenWrite("slide_5.pdf");
        pdfStream.CopyTo(outputStream);
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

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        byte[] fileData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));

        // Set the options for the output PDF document.
        PdfExportOptions pdfOptions = new PdfExportOptions();
        pdfOptions.setCompliance(PdfExportOptions.ComplianceEnum.PDFA1B);
        pdfOptions.setEmbedFullFonts(true);
        pdfOptions.setJpegQuality(90);

        // Extract the 5th slide and save it to the PDF document.
        File pdfFile = slidesApi.downloadSlideOnline(fileData, 5, SlideExportFormat.PDF, null, null, null, null, null, pdfOptions);

        System.out.println("The PDF document was saved to " + pdfFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\PdfExportOptions;
use Aspose\Slides\Cloud\Sdk\Model\SlideExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

$fileStream = fopen("MyPresentation.pptx", 'r');

// Set the options for the output PDF document.
$pdfOptions = new PdfExportOptions();
$pdfOptions->setCompliance("PdfA1b");
$pdfOptions->setEmbedFullFonts(true);
$pdfOptions->setJpegQuality(90);

// Extract the 5th slide and save it to the PDF document.
$pdfFile = $slidesApi->downloadSlideOnline($fileStream, 5, SlideExportFormat::PDF, null, null, null, null, null, $pdfOptions);

echo "The PDF document was saved to ", $pdfFile->getPathname();
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

file_data = File.binread("MyPresentation.pptx")

# Set the options for the output PDF document.
pdf_options = PdfExportOptions.new
pdf_options.compliance = "PdfA1b"
pdf_options.embed_full_fonts = true
pdf_options.jpeg_quality = 90

# Extract the 5th slide and save it to the PDF document.
pdf_data = slides_api.download_slide_online(file_data, 5, SlideExportFormat::PDF, nil, nil, nil, nil, nil, pdf_options)

# Save the PDF document to a file.
File.binwrite("slide_5.pdf", pdf_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_export_format import SlideExportFormat
from asposeslidescloud.models.pdf_export_options import PdfExportOptions

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Set the options for the output PDF document.
pdf_options = PdfExportOptions()
pdf_options.compliance = "PdfA1b"
pdf_options.embed_full_fonts = True
pdf_options.jpeg_quality = 90

# Extract the 5th slide from the presentation and save it to the PDF document.
with open("MyPresentation.pptx", "rb") as file_stream:
    pdf_file_path = slides_api.download_slide_online(file_stream.read(), 5, SlideExportFormat.PDF, None, None, None, None, None, pdf_options)

print("The PDF document was saved to ", pdf_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

const fileStream = fs.createReadStream("MyPresentation.pptx");

// Set the options for the output PDF document.
const pdfOptions = new cloud.PdfExportOptions();
pdfOptions.compliance = "PdfA1b";
pdfOptions.embedFullFonts = true;
pdfOptions.jpegQuality = 90;

// Extract the 5th slide and save it to the PDF document.
slidesApi.downloadSlideOnline(fileStream, 5, cloud.SlideExportFormat.Pdf, null, null, null, null, null, pdfOptions).then(response => {
    // Save the PDF document to a file.
    fs.writeFile("slide_5.pdf", response.body, (error) => {
        if (error) throw error;
    });
});
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

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        byte[] fileData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));

        // Set the options for the output PDF document.
        PdfExportOptions pdfOptions = new PdfExportOptions();
        pdfOptions.setCompliance(PdfExportOptions.ComplianceEnum.PDFA1B);
        pdfOptions.setEmbedFullFonts(true);
        pdfOptions.setJpegQuality(90);

        // Extract the 5th slide and save it to the PDF document.
        File pdfFile = slidesApi.downloadSlideOnline(fileData, 5, SlideExportFormat.PDF, null, null, null, null, null, pdfOptions);

        System.out.println("The PDF document was saved to " + pdfFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/PdfExportOptions.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"my_client_id", L"my_client_secret");

    // Prepare request data with the presentation.
    auto fileStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto fileContent = std::make_shared<HttpContent>();
    fileContent->setData(fileStream);

    // Set the options for the output PDF document.
    auto pdfOptions = std::make_shared<PdfExportOptions>();
    pdfOptions->setCompliance(L"PdfA1b");
    pdfOptions->setEmbedFullFonts(true);
    pdfOptions->setJpegQuality(90);
   
    // Extract the 5th slide and save it to the PDF document.
    auto pdfContent = slidesApi->downloadSlideOnline(
        fileContent, 5, L"pdf", NULL, NULL, L"", L"", L"", pdfOptions).get();

    // Save the PDF document to a file.
    std::ofstream outputStream("slide_5.pdf", std::ofstream::binary);
    pdfContent.writeTo(outputStream);

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::PdfExportOptions;

use File::Slurp;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_data = read_file("MyPresentation.pptx", { binmode => ":raw" });

# Set the options for the output PDF document.
my $pdf_options = AsposeSlidesCloud::Object::PdfExportOptions->new();
$pdf_options->{compliance} = "PdfA1b";
$pdf_options->{embed_full_fonts} = true;
$pdf_options->{jpeg_quality} = 90;

# Extract the 5th slide and save it to the PDF document.
my %parameters = (document => $file_data, slide_index => 5, format => "pdf", options => $pdf_options);
my $pdf_data = $slides_api->download_slide_online(%parameters);

# Save the PDF document to a file.
write_file("slide_5.pdf", {binmode => ":raw"}, $pdf_data);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SaveSlideOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/slides/{slideIndex}/{format}|PUT|Uploads a presentation to a storage, extracts the specified slide from the presentation, and saves the slide to the storage.|[SaveSlideOnline](https://apireference.aspose.cloud/slides/#/Slides/SaveSlideOnline)|

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file data.|
|slideIndex|integer|path|true|The 1-based index of the slide to be extracted from the presentation.|
|format|string|path|true|The output format for the slide. See [the table](/slides/split-presentations/#available-formats-for-output-files) for available formats.|
|outPath|string|query|true|The output path for a slide file.|
|width|integer|query|false|The width of the slide in output format units. The default value is 0 (used the original width).|
|height|integer|query|false|The height of the slide in output format units. The default value is 0 (used the original height).|
|password|string|header|false|The password to open the presentation.|
|storage|string|query|false|The name of the storage.|
|fontsFolder|string|query|false|The path to the storage folder contaning custom fonts to be used with the presentation.|
|options|body|object|false|The export options depending on the output format. See [conversion options](/slides/conversion-options/) for the available formats.|

### **Examples**

Extract the **fourth** slide from **MyPresentation.pptx** and save it to **MyImages/slide_4.svg** file in SVG format using **MyStorage**. Embed external fonts from **MyFonts** folder to the output file. 

**cURL Solution**

{{< tabs tabTotal="2" tabID="4" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Save the Slide**

```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/slides/4/Svg?outPath=MyImages/slide_4.svg&storage=MyStorage&fontsFolder=MyFonts" \
     -H "authorization: Bearer <access_token>" \
     -F "file=@MyPresentation.pptx" \
     -F "data=@request_data.json;filename="
```

request_data.json content:

```json
{
    "ExternalFontsHandling": "Embed"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

None

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="44" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

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
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        using var fileStream = File.OpenRead("MyPresentation.pptx");

        // Set the options for the output SVG file.
        var svgOptions = new SvgExportOptions
        {
            ExternalFontsHandling = SvgExportOptions.ExternalFontsHandlingEnum.Embed
        };

        // Extract the 4th slide and save it to the SVG file.
        api.SaveSlideOnline(fileStream, 4, SlideExportFormat.Svg, "MyImages/slide_4.svg", null, null, null, null, null, svgOptions);
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

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        byte[] fileData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));

        // Set the options for the output SVG file.
        SvgExportOptions svgOptions = new SvgExportOptions();
        svgOptions.setExternalFontsHandling(SvgExportOptions.ExternalFontsHandlingEnum.EMBED);

        // Extract the 4th slide and save it to the SVG file.
        slidesApi.saveSlideOnline(fileData, 4, SlideExportFormat.SVG, "MyImages/slide_4.svg", null, null, null, "MyStorage", "MyFonts", svgOptions);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SvgExportOptions;
use Aspose\Slides\Cloud\Sdk\Model\SlideExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

$fileStream = fopen("MyPresentation.pptx", 'r');

// Set the options for the output SVG file.
$svgOptions = new SvgExportOptions();
$svgOptions->setExternalFontsHandling("Embed");

// Extract the 4th slide and save it to the SVG file.
$slidesApi->saveSlideOnline($fileStream, 4, SlideExportFormat::SVG, "MyImages/slide_4.svg", null, null, null, "MyStorage", "MyFonts", $svgOptions);
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

file_data = File.binread("MyPresentation.pptx")

# Set the options for the output SVG file.
svg_options = SvgExportOptions.new
svg_options.external_fonts_handling = "Embed"

# Extract the 4th slide and save it to the SVG file.
slides_api.save_slide_online(file_data, 4, SlideExportFormat::SVG, "MyImages/slide_4.svg", nil, nil, nil, "MyStorage", "MyFonts", svg_options)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_export_format import SlideExportFormat
from asposeslidescloud.models.svg_export_options import SvgExportOptions

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Set the options for the output SVG file.
svg_options = SvgExportOptions()
svg_options.external_fonts_handling = "Embed"

# Extract the 4th slide and save it to the SVG file.
with open("MyPresentation.pptx", "rb") as file_stream:
    file_data = file_stream.read()
    slides_api.save_slide_online(file_data, 4, SlideExportFormat.SVG, "MyImages/slide_4.svg", None, None, None, "MyStorage", "MyFonts", svg_options)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

const fileStream = fs.createReadStream("MyPresentation.pptx");

// Set the options for the output SVG file.
const svgOptions = new cloud.SvgExportOptions();
svgOptions.externalFontsHandling = "Embed";

// Extract the 4th slide and save it to the SVG file.
slidesApi.saveSlideOnline(fileStream, 4, cloud.SlideExportFormat.Svg, "MyImages/slide_4.svg", null, null, null, "MyStorage", "MyFonts", svgOptions).then(() => {
});
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

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        byte[] fileData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));

        // Set the options for the output SVG file.
        SvgExportOptions svgOptions = new SvgExportOptions();
        svgOptions.setExternalFontsHandling(SvgExportOptions.ExternalFontsHandlingEnum.EMBED);

        // Extract the 4th slide and save it to the SVG file.
        slidesApi.saveSlideOnline(fileData, 4, SlideExportFormat.SVG, "MyImages/slide_4.svg", null, null, null, "MyStorage", "MyFonts", svgOptions);
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/SvgExportOptions.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"my_client_id", L"my_client_secret");

    // Prepare request data with the presentation.
    auto fileStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto fileContent = std::make_shared<HttpContent>();
    fileContent->setData(fileStream);

    // Set the options for the output SVG file.
    auto svgOptions = std::make_shared<SvgExportOptions>();
    svgOptions->setExternalFontsHandling(L"Embed");

    // Extract the 4th slide and save it to the SVG file.
    slidesApi->saveSlideOnline(
        fileContent, 4, L"svg", L"MyImages/slide_4.svg", NULL, NULL, L"", L"MyStorage", L"MyFonts", svgOptions).get();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SvgExportOptions;

use File::Slurp;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_data = read_file("MyPresentation.pptx", { binmode => ":raw" });

# Set the options for the output SVG file.
my $svg_options = AsposeSlidesCloud::Object::SvgExportOptions->new();
$svg_options->{external_fonts_handling} = "Embed";

# Extract the 4th slide and save it to the SVG file.
my %parameters = (document => $file_data, slide_index => 4, format => "svg", out_path => "MyImages/slide_4.svg", 
                  storage => "MyStorage", fonts_folder => "MyFonts", options => $svg_options);
$slides_api->save_slide_online(%parameters);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
