---
title: "Render a Paragraph to an Image"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- text
- paragraph
- render a paragraph
- paragraph to image
- paragraph to PNG
- paragraph to JPEG
- export a paragraph
type: docs
url: /render-a-paragraph-to-an-image/
weight: 80
---

## **Introduction**

Aspose.Slides Cloud API allows you to render a single paragraph of a shape to an image. This is useful when you need a picture of a specific piece of text from a slide, for example, to show a preview of it or to embed it into another document. The paragraph can be rendered to JPEG, PNG, GIF, BMP, or TIFF format. You can either get the image in the response or save it to a storage.

{{% alert color="primary" %}} 
There is [a similar method](/slides/render-a-table-cell-paragraph-to-an-image/) for rendering paragraphs in table cells.
{{% /alert %}}

## **DownloadParagraph**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/{format}|POST|Renders a paragraph from a presentation saved in a storage to the specified image format and returns the image in the response.|[DownloadParagraph](https://reference.aspose.cloud/slides/#/Shapes/DownloadParagraph)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|format|string|path|true|The format of the output image (**Jpeg**, **Png**, **Gif**, **Bmp**, or **Tiff**).|
|scaleX|number|query|false|The scale ratio along the X axis.|
|scaleY|number|query|false|The scale ratio along the Y axis.|
|quality|integer|query|false|The image quality from 1 to 100; applies to JPEG only. The default value is 100.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage containing the `folder`.|
|fontsFolder|string|query|false|The path to the storage folder containing external fonts.|
|subShape|string|query|false|The path to a shape inside a group shape or a SmartArt object (e.g. "3", "3/shapes/2").|

### **Examples**

In the **default** storage, the document **MyFolder/MyPresentation.pptx** contains a text box (the **first** shape) on the **first** slide. Render the **second** paragraph of the text box to a PNG image scaled **2** times and save it to a local file.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Render the Paragraph**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs/2/Png?scaleX=2&scaleY=2&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -o paragraph.png
```

{{< /tab >}}

{{< tab tabNum="2" >}}

The paragraph image.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="8" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-.NET

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System.IO;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Render paragraph 2 of shape 1 on slide 1 to PNG, scaled 2 times.
        using var imageStream = slidesApi.DownloadParagraph("MyPresentation.pptx", 1, 1, 2, ImageExportFormat.Png, 2, 2, folder: "MyFolder");

        // Save the image to a file.
        using var outputStream = File.Create("paragraph.png");
        imageStream.CopyTo(outputStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ImageExportFormat;

import java.io.File;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Render paragraph 2 of shape 1 on slide 1 to PNG, scaled 2 times.
        File imageFile = slidesApi.downloadParagraph("MyPresentation.pptx", 1, 1, 2, ImageExportFormat.PNG, 2.0, 2.0, null, null, "MyFolder", null, null, null);

        System.out.println("The paragraph image was saved to " + imageFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-PHP

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ImageExportFormat;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $config);

// Render paragraph 2 of shape 1 on slide 1 to PNG, scaled 2 times.
$imageFile = $slidesApi->downloadParagraph("MyPresentation.pptx", 1, 1, 2, ImageExportFormat::PNG, 2, 2, null, null, "MyFolder");

echo "The paragraph image was saved to ", $imageFile->getPathname();
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Render paragraph 2 of shape 1 on slide 1 to PNG, scaled 2 times.
image_data = slides_api.download_paragraph("MyPresentation.pptx", 1, 1, 2, ImageExportFormat::PNG, 2, 2, nil, nil, "MyFolder")

# Save the image to a file.
File.binwrite("paragraph.png", image_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Render paragraph 2 of shape 1 on slide 1 to PNG, scaled 2 times.
image_file_path = slides_api.download_paragraph("MyPresentation.pptx", 1, 1, 2, "Png", 2, 2, None, None, "MyFolder")

print("The paragraph image was saved to", image_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Node.js

const cloud = require("asposeslidescloud");
const fs = require("fs");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Render paragraph 2 of shape 1 on slide 1 to PNG, scaled 2 times.
slidesApi.downloadParagraph("MyPresentation.pptx", 1, 1, 2, cloud.ImageExportFormat.Png, 2, 2, null, null, "MyFolder").then(response => {
    // Save the image to a file.
    fs.writeFile("paragraph.png", response.body, (error) => {
        if (error) throw error;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Render paragraph 2 of shape 1 on slide 1 to PNG, scaled 2 times.
    auto imageContent = slidesApi->downloadParagraph(L"MyPresentation.pptx", 1, 1, 2, L"Png", 2.0, 2.0, boost::none, L"", L"MyFolder").get();

    // Save the image to a file.
    std::ofstream imageStream("paragraph.png", std::ofstream::binary);
    imageContent.writeTo(imageStream);

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Perl

use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Render paragraph 2 of shape 1 on slide 1 to PNG, scaled 2 times.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, shape_index => 1, paragraph_index => 2, format => "Png", scale_x => 2, scale_y => 2, folder => "MyFolder");
my $image_data = $slides_api->download_paragraph(%parameters);

# Save the image to a file.
write_file("paragraph.png", {binmode => ":raw"}, $image_data);
```

{{< /tab >}}

{{< /tabs >}}

## **SaveParagraph**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/{format}|PUT|Renders a paragraph from a presentation saved in a storage to the specified image format and saves the image to the storage.|[SaveParagraph](https://reference.aspose.cloud/slides/#/Shapes/SaveParagraph)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|format|string|path|true|The format of the output image (**Jpeg**, **Png**, **Gif**, **Bmp**, or **Tiff**).|
|outPath|string|query|true|The path to the output image in the storage.|
|scaleX|number|query|false|The scale ratio along the X axis.|
|scaleY|number|query|false|The scale ratio along the Y axis.|
|quality|integer|query|false|The image quality from 1 to 100; applies to JPEG only. The default value is 100.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage containing the `folder`.|
|fontsFolder|string|query|false|The path to the storage folder containing external fonts.|
|subShape|string|query|false|The path to a shape inside a group shape or a SmartArt object (e.g. "3", "3/shapes/2").|

### **Examples**

In the **default** storage, the document **MyFolder/MyPresentation.pptx** contains a text box (the **first** shape) on the **first** slide. Render the **second** paragraph of the text box to a JPEG image with quality **80** and save it to **MyFolder/paragraph.jpg** in the storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Render the Paragraph and Save the Image**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs/2/Jpeg?outPath=MyFolder/paragraph.jpg&quality=80&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

The response has the **200 OK** status code and an empty body.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="8" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-.NET

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Render paragraph 2 of shape 1 on slide 1 to JPEG and save it to the storage.
        slidesApi.SaveParagraph("MyPresentation.pptx", 1, 1, 2, ImageExportFormat.Jpeg, "MyFolder/paragraph.jpg", quality: 80, folder: "MyFolder");
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ImageExportFormat;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Render paragraph 2 of shape 1 on slide 1 to JPEG and save it to the storage.
        slidesApi.saveParagraph("MyPresentation.pptx", 1, 1, 2, ImageExportFormat.JPEG, "MyFolder/paragraph.jpg", null, null, 80, null, "MyFolder", null, null, null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-PHP

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ImageExportFormat;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $config);

// Render paragraph 2 of shape 1 on slide 1 to JPEG and save it to the storage.
$slidesApi->saveParagraph("MyPresentation.pptx", 1, 1, 2, ImageExportFormat::JPEG, "MyFolder/paragraph.jpg", null, null, 80, null, "MyFolder");
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Render paragraph 2 of shape 1 on slide 1 to JPEG and save it to the storage.
slides_api.save_paragraph("MyPresentation.pptx", 1, 1, 2, ImageExportFormat::JPEG, "MyFolder/paragraph.jpg", nil, nil, 80, nil, "MyFolder")
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Render paragraph 2 of shape 1 on slide 1 to JPEG and save it to the storage.
slides_api.save_paragraph("MyPresentation.pptx", 1, 1, 2, "Jpeg", "MyFolder/paragraph.jpg", None, None, 80, None, "MyFolder")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Node.js

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Render paragraph 2 of shape 1 on slide 1 to JPEG and save it to the storage.
slidesApi.saveParagraph("MyPresentation.pptx", 1, 1, 2, cloud.ImageExportFormat.Jpeg, "MyFolder/paragraph.jpg", null, null, 80, null, "MyFolder").then(() => {
    console.log("The paragraph image was saved to the storage.");
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Render paragraph 2 of shape 1 on slide 1 to JPEG and save it to the storage.
    slidesApi->saveParagraph(L"MyPresentation.pptx", 1, 1, 2, L"Jpeg", L"MyFolder/paragraph.jpg", boost::none, boost::none, 80, L"", L"MyFolder").wait();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-slides-cloud/Aspose.Slides-Cloud-SDK-for-Perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Render paragraph 2 of shape 1 on slide 1 to JPEG and save it to the storage.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, shape_index => 1, paragraph_index => 2, format => "Jpeg", out_path => "MyFolder/paragraph.jpg", quality => 80, folder => "MyFolder");
$slides_api->save_paragraph(%parameters);
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
