---
title: "Merging Presentations from Various Sources into a Local File"
type: docs
url: /merging-presentations-from-various-sources-into-a-local-file/
weight: 30
---

## **Introduction**

The article shows you how to merge PowerPoint presentations from different sources: local files, storage, and remote resources. The final presentation will be received as a local file. You can specify slide indices to merge presentations in parts. Passwords can be specified to open protected presentations. The request method below allows you to merge presentation files stored in different ways: locally, in storage, and remotely.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/merge|POST|Merges presentations or some of their slides. Returns the result file in the response.|[MergeOnline](https://apireference.aspose.cloud/slides/#/MergeDocument/MergeOnline)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|files|array|formData|false|The array of presentation files to merge.|
|request|object|body|false|The information about presentations to merge (paths, passwords, slide indices, etc.).|
|storage|string|query|false|The name of the storage where the presentations specified in the `request` parameter were saved.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **Merging Presentations from Various Sources**

Example: Merge **local.pptx** saved to local file, **storage.pptx** saved on storage, **remote presentation** and receive the result as a local file.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Merge the Presentations**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/merge" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -d @request_data.json \
     -F "file1=@local.pptx" \
     -o MyPresentation.pptx
```

request_data.json
```json
{
    "Presentations": [
        {
            "Path": "local.pptx",
            "Slides": [1, 2],
        },
        {
            "Path": "storage.pptx",
            "Password": "my_password",
            "Source": "Storage"
        },
        {
            "Path": "https://drive.google.com/uc?export=download&id=remote.pptx",
            "Slides": [1],
            "Source": "Url"
        }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

Presentation file.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System.Collections.Generic;
using System.IO;

using FileInfo = Aspose.Slides.Cloud.Sdk.FileInfo;

class Application
{
    static void Main()
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Collect the presentations to merge.
        var fileInfo = new Sdk.FileInfo { Content = File.OpenRead("local.pptx"), Name = "local.pptx" };
        var files = new List<Sdk.FileInfo> { fileInfo};

        // Prepare information for the second presentation to merge.
        var presentation1 = new PresentationToMerge
        {
            Path = "local.pptx",
            Slides = new List<int> { 1, 2 }
        };

        // Prepare information for the second presentation to merge.
        var presentation2 = new PresentationToMerge
        {
            Path = "storage.pptx",
            Password = "my_password",
            Source = PresentationToMerge.SourceEnum.Storage
        };

        // Prepare information for the second presentation to merge.
        var presentation3 = new PresentationToMerge
        {
            Path = "https://drive.google.com/uc?export=download&id=remote.pptx",
            Slides = new List<int> { 1 },
            Source = PresentationToMerge.SourceEnum.Url
        };

         // Prepare the merge request.
        var request = new OrderedMergeRequest();
        request.Presentations = new List<PresentationToMerge> { presentation1, presentation2, presentation3 };

        // Merge the presentations.
        using var resultStream = api.MergeOnline(files, request);

        // Save the result to a file.
        using var outputStream = File.Open("MyPresentation.pptx", FileMode.Create);
        resultStream.CopyTo(outputStream);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.FileInfo;
import com.aspose.slides.api.SlidesApi;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.ArrayList;

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Collect the presentations to merge.
        FileInfo fileInfo = new FileInfo();
        fileInfo.setData(Files.readAllBytes(Paths.get("local.pptx")));
        fileInfo.setName("local.pptx");

        List<FileInfo> files = new ArrayList<FileInfo>();
        files.add(fileInfo);

        // Prepare information for the first presentation to merge.
        PresentationToMerge presentation1 = new PresentationToMerge();
        presentation1.setPath("local.pptx");
        presentation1.setSlides(Arrays.asList(1, 2));
       
        // Prepare information for the first presentation to merge.
        PresentationToMerge presentation2 = new PresentationToMerge();
        presentation2.setPath("storage.pptx");
        presentation2.setPassword("my_password");
        presentation2.setSource(PresentationToMerge.SourceEnum.STORAGE);

        // Prepare information for the first presentation to merge.
        PresentationToMerge presentation3 = new PresentationToMerge();
        presentation3.setPath("https://drive.google.com/uc?export=download&id=remote.pptx");
        presentation3.setSlides(Arrays.asList(1));
        presentation3.setSource(PresentationToMerge.SourceEnum.URL);

         // Prepare the merge request.
        OrderedMergeRequest request = new OrderedMergeRequest();
        request.setPresentations(Arrays.asList(presentation1, presentation2, presentation3));

        // Merge the presentations.
        File resultFile = slidesApi.mergeOnline(files, request, null);

        System.out.println("The output presentation was saved to " + resultFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\PresentationToMerge;
use Aspose\Slides\Cloud\Sdk\Model\OrderedMergeRequest;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Collect the presentations to merge.
$file = fopen("local.pptx", 'r');
$files = [$file];

// Prepare information for the first presentation to merge.
$presentation1 = new PresentationToMerge();
$presentation1->setPath("local.pptx");
$presentation1->setSlides([1, 2]);

// Prepare information for the first presentation to merge.
$presentation2 = new PresentationToMerge();
$presentation2->setPath("storage.pptx");
$presentation2->setPassword("my_password");
$presentation2->setSource("Storage");

// Prepare information for the first presentation to merge.
$presentation3 = new PresentationToMerge();
$presentation3->setPath("https://drive.google.com/uc?export=download&id=remote.pptx");
$presentation3->setSlides([1]);
$presentation3->setSource("Url");

// Prepare the merge request.
$request = new OrderedMergeRequest();
$request->setPresentations([$presentation1, $presentation2, $presentation3]);

// Merge the presentations.
$resultFile = $slidesApi->mergeOnline($files, $request);

// Save the result to a file.
echo "The output presentation was saved to ", $resultFile->getPathname();
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

# Collect the presentations to merge.
file_data = File.binread("local.pptx")
files = [file_data]

# Prepare information for the first presentation to merge.
presentation1 = PresentationToMerge.new
presentation1.path = "local.pptx"
presentation1.slides = [1, 2]

# Prepare information for the first presentation to merge.
presentation2 = PresentationToMerge.new
presentation2.path = "storage.pptx"
presentation2.password = "my_password"
presentation2.source = "Storage"

# Prepare information for the first presentation to merge.
presentation3 = PresentationToMerge.new
presentation3.path = "https://drive.google.com/uc?export=download&id=remote.pptx"
presentation1.slides = [1]
presentation3.source = "Url"

# Prepare the merge request.
request = OrderedMergeRequest.new
request.presentations = [presentation1, presentation2, presentation3]

# Merge the presentations.
result_data = slides_api.merge_online(files, request)

# Save the result to a file.
File.binwrite("MyPresentation.pptx", result_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.ordered_merge_request import OrderedMergeRequest
from asposeslidescloud.models.presentation_to_merge import PresentationToMerge

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Collect the presentations to merge.
with open("local.pptx", "rb") as file1_stream:
    file_data = file1_stream.read()
files = [file_data]

# Prepare information for the first presentation to merge.
presentation1 = PresentationToMerge()
presentation1.path = "local.pptx"
presentation1.slides = [1, 2]
presentation1.source = "Storage"

# Prepare information for the first presentation to merge.
presentation2 = PresentationToMerge()
presentation2.path = "storage.pptx"
presentation2.password = "my_password"
presentation2.source = "Storage"

# Prepare information for the first presentation to merge.
presentation3 = PresentationToMerge()
presentation3.path = "https://drive.google.com/uc?export=download&id=remote.pptx"
presentation3.slides = [1]
presentation3.source = "Url"

# Prepare the merge request.
request = OrderedMergeRequest()
request.presentations = [presentation1, presentation2, presentation3]

# Merge the presentations.
result_file_path = slides_api.merge_online(files, request)

print("The output presentation was saved to ", result_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret")

// Collect the presentations to merge.
const fileStream = fs.createReadStream("local.pptx")
const files = [fileStream]

// Prepare information for the first presentation to merge.
const presentation1 = new cloud.PresentationToMerge()
presentation1.path = "local.pptx"
presentation1.slides = [1, 2]

// Prepare information for the first presentation to merge.
const presentation2 = new cloud.PresentationToMerge()
presentation2.path = "storage.pptx"
presentation2.password = "my_password"
presentation2.source = "Storage"

// Prepare information for the first presentation to merge.
const presentation3 = new cloud.PresentationToMerge()
presentation3.path = "https://drive.google.com/uc?export=download&id=remote.pptx"
presentation3.source = "Url"

// Prepare the merge request.
const request = new cloud.OrderedMergeRequest()
request.presentations = [presentation1, presentation2, presentation3]

// Merge the presentations.
slidesApi.mergeOnline(files, request).then((response) => {
    // Save the result to a file.
    fs.writeFile("MyPresentation.pptx", response.body, (error) => {
        if (error) throw error
    })
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.FileInfo;
import com.aspose.slides.api.SlidesApi;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.ArrayList;

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Collect the presentations to merge.
        FileInfo fileInfo = new FileInfo();
        fileInfo.setData(Files.readAllBytes(Paths.get("local.pptx")));

        List<FileInfo> files = new ArrayList<FileInfo>();
        files.add(fileInfo);

         // Prepare information for the first presentation to merge.
        PresentationToMerge presentation1 = new PresentationToMerge();
        presentation1.setPath("local.pptx");
        presentation1.setSlides(Arrays.asList(1, 2));

        // Prepare information for the second presentation to merge.
        PresentationToMerge presentation2 = new PresentationToMerge();
        presentation2.setPath("storage.pptx");
        presentation2.setPassword("my_password");
        presentation2.setSource(PresentationToMerge.SourceEnum.STORAGE);

        PresentationToMerge presentation3 = new PresentationToMerge();
        presentation3.setPath("https://drive.google.com/uc?export=download&id=remote.pptx");
        presentation3.setSlides(Arrays.asList(1));
        presentation3.setSource(PresentationToMerge.SourceEnum.URL);

        // Prepare the merge request.
        OrderedMergeRequest request = new OrderedMergeRequest();
        request.setPresentations(Arrays.asList(presentation1, presentation2, presentation3));

        // Merge the presentations.
        File resultFile = slidesApi.mergeOnline(files, request, null);

        System.out.println("The output presentation was saved to " + resultFile.getPath());
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
    auto slidesApi = new SlidesApi(to_string_t("my_client_id"), to_string_t("my_client_secret"));

    // Collect the presentations to merge.
    auto fileStream = std::make_shared<std::ifstream>("TestData/example1.pptx", std::ios::binary);
    auto fileContent = std::make_shared<HttpContent>();
    fileContent->setData(fileStream);
    auto files = { fileContent };

    // Prepare information for the first presentation to merge.
    auto presentation1 = std::make_shared<PresentationToMerge>();
    presentation1->setPath(to_string_t("lodal.pptx"));
    presentation1->setSlides({ 1, 2 });

    // Prepare information for the second presentation to merge.
    auto presentation2 = std::make_shared<PresentationToMerge>();
    presentation2->setPath(to_string_t("storage.pptx"));
    presentation2->setPassword(to_string_t("my_password"));
    presentation2->setSource(to_string_t("Storage"));

    // Prepare information for the second presentation to merge.
    auto presentation3 = std::make_shared<PresentationToMerge>();
    presentation3->setPath(to_string_t("
https://drive.google.com/uc?export=download&id=remote.pptx"));
    presentation3->setSlides({ 1 });
    presentation3->setSource(to_string_t("Url"));

    // Prepare the merge request.
    auto request = std::make_shared<OrderedMergeRequest>();
    request->setPresentations({ presentation1, presentation2, presentation3 });

    // Merge the presentations.
    auto resultContent = slidesApi->mergeOnline(files, request).get();

    // Save the result to a file.
    std::ofstream outputStream("MyPresentation.pptx", std::ofstream::binary);
    resultContent.writeTo(outputStream);

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
use AsposeSlidesCloud::Object::OrderedMergeRequest;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Collect the presentations to merge.
my $file_data = read_file("TestData/example1.pptx", { binmode => ":raw" });
my @files = [$file_data];

# Prepare information for the first presentation to merge.
my $presentation1 = AsposeSlidesCloud::Object::PresentationToMerge->new();
$presentation1->{path} = "local.pptx";
@{$presentation1->{slides}} = (1, 2);

# Prepare information for the second presentation to merge.
my $presentation2 = AsposeSlidesCloud::Object::PresentationToMerge->new();
$presentation2->{path} = "storage.pptx";
$presentation2->{password} = "my_password";
$presentation2->{source} = "Storage";

# Prepare information for the second presentation to merge.
my $presentation3 = AsposeSlidesCloud::Object::PresentationToMerge->new();
$presentation3->{path} = "https://drive.google.com/uc?export=download&id=remote.pptx";
@{$presentation3->{slides}} = (1);
$presentation3->{source} = "Url";

# Prepare the merge request.
my $request = AsposeSlidesCloud::Object::OrderedMergeRequest->new();
@{$request->{presentations}} = ($presentation1, $presentation2, $presentation3);

# Merge the presentations.
my %merge_params = ("files" => @files, "request" => $request);
my $result_data = $slides_api->merge_online(%merge_params);

# Save the result to a file.
write_file("MyPresentation.pptx", {binmode => ":raw"}, $result_data);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
