---
title: "Converting a Presentation to a Specified Format"
type: docs
url: /converting-a-presentation-to-a-specified-format/
weight: 10
---

## **Introduction**

The following method allows you to convert a PowerPoint presentation to a specified format by passing a local file. The result of the conversion will be obtained immediately for saving to a local file as well. In addition, you can also specify a folder in a storage containing external fonts that can be used in the presentation, and other options.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/convert/{format}|POST|Converts a passed presentation to a specified format and returns the result of the conversion.|[Convert](https://apireference.aspose.cloud/slides/#/Document/Convert)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The data of the presentation.|
|format|string|path|true|The desired format for the conversion.|
|password|string|header|false|The password to open the presentation.|
|storage|string|query|false|The name of the storage containing the external fonts.|
|fontsFolder|string|query|false|The path to the storage folder containing the external fonts.|
|slides|string|query|false|The 1-based indices of the slides to be converted. If it is not specified, all slides are converted by default.|
|options|object|body|false|The format-specific options for the conversion.|

To use **fontsFolder** parameter, you can create storage folders and upload font files to them using Slides Cloud API.

You can [convert parts of presentations](/slides/convert-selected-document-slides/) using the optional **slides** parameter.

You can specify [format-specific options](/slides/conversion-options/) using the **options** parameter.

## **cURL Examples**

Create **MyFonts** storage folder in **Main** storage, add **custom.ttf** font to the folder, convert **example.pptx** presentation to PDF format, and save the PDF document to **output.pdf** file.

{{< tabs tabTotal="2" tabID="1" tabName1="Requests" tabName2="Responses" >}}

{{< tab tabNum="1" >}}

**Creating the storage folder**
```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/folder/MyFonts?storageName=Main" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Length: 0"
```

**Adding the font to the folder**
```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/storage/file/MyFonts/custom.ttf?storageName=Main" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/octet-stream" \
     --data-binary @custom.ttf
```

**Converting the presentation**
```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/convert/Pdf?storage=Main&fontsFolder=MyFonts" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/octet-stream" \
     --data-binary @example.pptx \
     -o output.pdf
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Creating the storage folder**

no data

**Adding the font to the folder**
```json
{
    "uploaded": [
        "custom.ttf"
    ],
    "errors": []
}
```

**Converting the presentation**

no data

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**

Create **MyFonts** storage folder in **Main** storage, add **custom.ttf** font to the folder, convert **example.pptx** presentation to PDF format.

{{< tabs tabTotal="11" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

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
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        const string storageName = "Main";
        const string fontFolderName = "MyFonts";
        const string fontFileName = "custom.ttf";

        // Create the font folder in the storage.
        slidesApi.CreateFolder(fontFolderName, storageName);

        // Add the font to the font folder.
        using var fontStream = File.OpenRead(fontFileName);
        slidesApi.UploadFile($"{fontFolderName}/{fontFileName}", fontStream, storageName);

        // Convert the presentation to PDF format.
        using var fileStream = File.OpenRead("example.pptx");
        using var responseStream = slidesApi.Convert(fileStream, ExportFormat.Pdf, null, storageName, fontFolderName);

        // Save the PDF document to a file.
        using var pdfStream = File.Create("output.pdf");
        responseStream.CopyTo(pdfStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        final String storageName = "Main";
        final String fontFolderName = "MyFonts";
        final String fontFileName = "custom.ttf";

        // Create the font folder in the storage.
        slidesApi.createFolder(fontFolderName, storageName);

        // Add the font to the font folder.
        var fontData = Files.readAllBytes(Paths.get("custom.ttf"));
        slidesApi.uploadFile(fontFolderName + "/" + fontFileName, fontData, storageName);

        // Convert the presentation to PDF format.
        var fileData = Files.readAllBytes(Paths.get("example.pptx"));
        var response = slidesApi.convert(fileData, ExportFormat.PDF, null, storageName, fontFolderName, null, null);

        System.out.println("The PDF file was saved to " + response.getPath());
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

$storageName = "Main";
$fontFolderName = "MyFonts";
$fontFileName = "custom.ttf";

// Create the font folder in the storage.
$slidesApi->createFolder($fontFolderName, $storageName);

// Add the font to the font folder.
$fontStream = fopen("custom.ttf", "r");
$slidesApi->uploadFile($fontFolderName . "/" . $fontFileName, $fontStream, $storageName);

// Convert the presentation to PDF format.
$fileStream = fopen("example.pptx", "r");
$response = $slidesApi->convert($fileStream, "pdf", null, $storageName, $fontFolderName, null, null);

print("The PDF file was saved to " . $response->getPathname());
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

storage_name = "Main"
font_folder_name = "MyFonts"
font_file_name = "custom.ttf"

# Create the font folder in the storage.
slides_api.create_folder(font_folder_name, storage_name)

# Add the font to the font folder.
font_data = File.binread("custom.ttf")
slides_api.upload_file(font_folder_name + "/" + font_file_name, font_data, storage_name)

# Convert the presentation to PDF format.
file_data = File.binread("example.pptx")
pdf_data = slides_api.convert(file_data, "pdf", nil, storage_name, font_folder_name)

# Save the PDF document to a file.
File.binwrite("output.pdf", pdf_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

storage_name = "Main"
font_folder_name = "MyFonts"
font_file_name = "custom.ttf"

# Create the font folder in the storage.
slides_api.create_folder(font_folder_name, storage_name)

# Add the font to the font folder.
with open("custom.ttf", "rb") as font_stream:
    slides_api.upload_file(font_folder_name + "/" + font_file_name, font_stream, storage_name)

# Convert the presentation to PDF format.
with open("example.pptx", "rb") as file_stream:
    pdf_path = slides_api.convert(file_stream, "pdf", None, storage_name, font_folder_name)

print("The PDF file was saved to " + pdf_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key")

const storageName = "Main"
const fontFolderName = "MyFonts"
const fontFileName = "custom.ttf"

// Create the font folder in the storage.
slidesApi.createFolder(fontFolderName, storageName).then(() => {

    // Add the font to the font folder.
    const fontStream = fs.createReadStream(fontFileName)
    slidesApi.uploadFile(fontFolderName + "/" + fontFileName, fontStream, storageName).then(() => {

        // Convert the presentation to PDF format.
        const fileStream = fs.createReadStream("example.pptx")
        slidesApi.convert(fileStream, "pdf", null, storageName, fontFolderName).then((response) => {

            // Save the PDF document to a file.
            fs.writeFile("output.pdf", response.body, (error) => {
                if (error) throw error
            })
        })
    })
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        final String storageName = "Main";
        final String fontFolderName = "MyFonts";
        final String fontFileName = "custom.ttf";

        // Create the font folder in the storage.
        slidesApi.createFolder(fontFolderName, storageName);

        // Add the font to the font folder.
        var fontData = Files.readAllBytes(Paths.get("custom.ttf"));
        slidesApi.uploadFile(fontFolderName + "/" + fontFileName, fontData, storageName);

        // Convert the presentation to PDF format.
        var fileData = Files.readAllBytes(Paths.get("example.pptx"));
        var response = slidesApi.convert(fileData, ExportFormat.PDF, null, storageName, fontFolderName, null, null);

        System.out.println("The PDF file was saved to " + response.getPath());
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

    auto storageName = to_string_t("Main");
    auto fontFolderName = to_string_t("MyFonts");
    auto fontFileName = to_string_t("custom.ttf");

    // Create the font folder in the storage.
    slidesApi->createFolder(fontFolderName, storageName).get();

    // Add the font to the font folder.
    auto fontStream = std::make_shared<std::ifstream>(fontFileName, std::ios::binary);
    auto fontContent = std::make_shared<HttpContent>();
    fontContent->setData(fontStream);
    auto fontFilePath = fontFolderName;
    fontFilePath.append(to_string_t("/")).append(fontFileName);
    slidesApi->uploadFile(fontFilePath, fontContent, storageName).get();

    // Convert the presentation to PDF format.
    auto fileStream = std::make_shared<std::ifstream>("example.pptx", std::ios::binary);
    auto fileContent = std::make_shared<HttpContent>();
    fileContent->setData(fileStream);
    auto responseContent = slidesApi->convert(fileContent, to_string_t("pdf"), utility::string_t(), storageName, fontFolderName).get();

    // Save the PDF document to a file.
    std::ofstream pdfStream("output.pdf", std::ofstream::binary);
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

storageName := "Main"
fontFolderName := "customFonts"
fontFileName := "custom.ttf"

// Create the font folder in the storage.
_, e := c.SlidesApi.CreateFolder(fontFolderName, storageName)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fontData, e := ioutil.ReadFile(fontFileName)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

// Add the font to the font folder.
_, e = c.SlidesApi.UploadFile(fontFolderName + "/" + fontFileName, fontData, storageName)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fileData, e := ioutil.ReadFile("example.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

// Convert the presentation to PDF format.
response, _, e := c.SlidesApi.Convert(fileData, "pdf", "", storageName, fontFolderName, nil, nil)
if e != nil {
    fmt.Printf("Error: %v.", e)
}

fmt.Printf("The PDF file was saved to  %v.", response.Name())
```

{{< /tab >}}

{{< /tabs >}}
