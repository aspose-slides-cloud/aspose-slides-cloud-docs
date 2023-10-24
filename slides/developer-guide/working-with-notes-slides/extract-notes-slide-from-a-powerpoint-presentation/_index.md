---
title: "Extract Notes Slide from a PowerPoint Presentation"
type: docs
url: /extract-notes-slide-from-a-powerpoint-presentation/
weight: 30
---

## **Introduction**

Aspose.Slides Cloud API allows you to extract a Notes slide from a PowerPoint presentation. You can use the following methods in your applications to retrieve notes from a presentation slide and convert the result to the specified format. The output file format can be image format, PowerPoint format, PDF, HTML, etc. The default width and height of output images or pages can also be changed if you wish. If some custom fonts are used for the notes, you can specify a path to the folder containing the fonts for displaying the text of the notes, as in the original Notes Page of the presentation.

## **DownloadNotesSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/notesSlide/{format}|GET|Retrieves a Notes slide from a presentation slide in the specified format.|[DownloadNotesSlide](https://apireference.aspose.cloud/slides/#/NotesSlide/DownloadNotesSlide)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of the presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|format|string|path|true|The output file format. Available values: `Jpeg`, `Png`, `Gif`, `Bmp`, `Tiff`, `Html`, `Pdf`, `Xps`, `Pptx`, `Odp`, `Otp`, `Ppt`, `Pps`, `Ppsx`, `Pptm`, `Ppsm`, `Potx`, `Pot`, `Potm`, `Svg`, `Fodp`, `Xaml`, `Html5`. The default value is `Jpeg`.|
|width|integer|query|false|The width of the output image or page. The slide width is used by default.|
|height|integer|query|false|The height of the output image or page. The slide height is used by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
|fontsFolder|string|query|false|The storage folder containing custom fonts used with the notes on the Notes Page.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Extract a Notes slide from the **second** slide in the document **MyFolder/MyPresentation.pptx** saved to the default storage. Save the result to a **PDF** file.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Extract the Slide Notes**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/notesSlide/Pdf?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -o SlideNotes2.pdf
```

{{< /tab >}}

{{< tab tabNum="2" >}}

File

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

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
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Extract slide notes from the first slide as a PDF document.
        using var pdfStream = slidesApi.DownloadNotesSlide("MyPresentation.pptx", 1, NotesSlideExportFormat.Pdf, folder: "MyFolder");

        // Save the PDF document to a file.
        using var fileStream = File.OpenWrite("SlideNotes2.pdf");
        pdfStream.CopyTo(fileStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import java.nio.file.Files;
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Extract slide notes from the first slide as a PDF document.
        File pdfFile = slidesApi.downloadNotesSlide("MyPresentation.pptx", 1, NotesSlideExportFormat.PDF, null, null, null, "MyFolder", null, null);

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
use Aspose\Slides\Cloud\Sdk\Model\NotesSlideExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Extract slide notes from the first slide as a PDF document.
$pdfFile = $slidesApi->downloadNotesSlide("MyPresentation.pptx", 1, NotesSlideExportFormat::PDF, null, null, null, "MyFolder");

echo "The PDF document was saved to ", $pdfFile->getPathname();
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

# Extract slide notes from the first slide as a PDF document.
pdf_data = slides_api.download_notes_slide("MyPresentation.pptx", 1, NotesSlideExportFormat::PDF, nil, nil, nil, "MyFolder")

# Save the PDF document to a file.
File.binwrite("SlideNotes2.pdf", pdf_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.notes_slide_export_format import NotesSlideExportFormat

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Extract slide notes from the first slide as a PDF document.
pdf_file_path = slides_api.download_notes_slide("MyPresentation.pptx", 1, NotesSlideExportFormat.PDF, None, None, None, "MyFolder")

print("The PDF document was saved to", pdf_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Extract slide notes from the first slide as a PDF document.
slidesApi.downloadNotesSlide("MyPresentation.pptx", 1, "Pdf", null, null, null, "MyFolder").then((pdfFile) => {
    // Save the PDF document to a file.
    fs.writeFile("SlideNotes2.pdf", pdfFile.body, (error) => {
        if (error) throw error
    })
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Extract slide notes from the first slide as a PDF document.
    auto pdfContent = slidesApi->downloadNotesSlide(L"MyPresentation.pptx", 1, L"Pdf", NULL, NULL, L"", L"MyFolder").get();

    // Save the PDF document to a file.
    std::ofstream fileStream("SlideNotes2.pdf", std::ofstream::binary);
    pdfContent.writeTo(fileStream);

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

use File::Slurp;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Extract slide notes from the first slide as a PDF document.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, format => "Pdf", folder => "MyFolder");
my $pdf_data = $slides_api->download_notes_slide(%parameters);

# Save the PDF document to a file.
write_file("SlideNotes2.pdf", {binmode => ":raw"}, $pdf_data);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **DownloadNotesSlideOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/slides/{slideIndex}/notesSlide/{format}|POST|Retrieves a Notes slide from a presentation slide in the specified format.|[DownloadNotesSlideOnline](https://apireference.aspose.cloud/slides/#/NotesSlide/DownloadNotesSlideOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The document data of the presentation.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|format|string|path|true|The output file format. Available values: `Jpeg`, `Png`, `Gif`, `Bmp`, `Tiff`, `Html`, `Pdf`, `Xps`, `Pptx`, `Odp`, `Otp`, `Ppt`, `Pps`, `Ppsx`, `Pptm`, `Ppsm`, `Potx`, `Pot`, `Potm`, `Svg`, `Fodp`, `Xaml`, `Html5`. The default value is `Jpeg`.|
|width|integer|query|false|The width of the output image or page. The slide width is used by default.|
|height|integer|query|false|The height of the output image or page. The slide height is used by default.|
|password|string|header|false|The password to open the presentation.|
|fontsFolder|string|query|false|The storage folder containing custom fonts used with the notes on the Notes Page.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Extract a Notes slide from the **second** slide in the local file **MyPresentation.pptx**. Save the result to an **XPS** file.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Extract the Slide Notes**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/slides/2/notesSlide/Xps" \
     -H "authorization: Bearer MyAccessToken" \
     -F "file=@MyPresentation.pptx" \
     -o SlideNotes2.xps
```

{{< /tab >}}

{{< tab tabNum="2" >}}

File

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

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
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Extract slide notes from the first slide as an XPS document.
        using var pptStream = File.OpenRead("MyPresentation.pptx");
        using var xpsStream = slidesApi.DownloadNotesSlideOnline(pptStream, 1, NotesSlideExportFormat.Xps);

        // Save the XPS document to a file.
        using var fileStream = File.OpenWrite("SlideNotes2.xps");
        xpsStream.CopyTo(fileStream);
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
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Extract slide notes from the first slide as an XPS document.
        byte[] pptData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        File xpsFile = slidesApi.downloadNotesSlideOnline(pptData, 1, NotesSlideExportFormat.XPS, null, null, null, null);

        System.out.println("The XPS document was saved to " + xpsFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\NotesSlideExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Extract slide notes from the first slide as an XPS document.
$pptStream = fopen("MyPresentation.pptx", 'r');
$xpsFile = $slidesApi->downloadNotesSlideOnline($pptStream, 1, NotesSlideExportFormat::XPS);

echo "The XPS document was saved to ", $xpsFile->getPathname();
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

# Extract slide notes from the first slide as an XPS document.
ppt_data = File.binread("MyPresentation.pptx")
xps_data = slides_api.download_notes_slide_online(ppt_data, 1, NotesSlideExportFormat::XPS)

# Save the XPS document to a file.
File.binwrite("SlideNotes2.xps", xps_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.notes_slide_export_format import NotesSlideExportFormat

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Extract slide notes from the first slide as an XPS document.
with open("MyPresentation.pptx", "rb") as ppt_stream:
    xps_file_path = slides_api.download_notes_slide_online(ppt_stream, 1, NotesSlideExportFormat.XPS)

print("The XPS document was saved to", xps_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Extract slide notes from the first slide as an XPS document.
const pptStream = fs.createReadStream("MyPresentation.pptx")
slidesApi.downloadNotesSlideOnline(pptStream, 1, "Xps").then((xpsFile) => {
    // Save the XPS document to a file.
    fs.writeFile("SlideNotes2.xps", xpsFile.body, (error) => {
        if (error) throw error
    })
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Prepare request data with the presentation.
    auto pptStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto pptContent = std::make_shared<HttpContent>();
    pptContent->setData(pptStream);

    // Extract slide notes from the first slide as an XPS document.
    auto xpsContent = slidesApi->downloadNotesSlideOnline(pptContent, 1, L"Xps").get();

    // Save the XPS document to a file.
    std::ofstream fileStream("SlideNotes2.xps", std::ofstream::binary);
    xpsContent.writeTo(fileStream);

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

use File::Slurp;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Extract slide notes from the first slide as an XPS document.
my $ppt_data = read_file("MyPresentation.pptx", { binmode => ":raw" });
my %parameters = (document => $ppt_data, slide_index => 1, format => "Xps");
my $xps_data = $slides_api->download_notes_slide_online(%parameters);

# Save the XPS document to a file.
write_file("SlideNotes2.xps", {binmode => ":raw"}, $xps_data);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
