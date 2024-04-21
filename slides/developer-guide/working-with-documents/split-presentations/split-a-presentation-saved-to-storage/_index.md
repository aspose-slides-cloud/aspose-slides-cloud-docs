---
title: "Split a Presentation Saved to Storage"
keywords: "PowerPoint, presentation, REST API, Cloud API, split a presentation, split slides"
type: docs
url: /split-a-presentation-saved-to-storage/
weight: 10
---

## **Introduction**

The article shows you how to split a PowerPoint presentation saved in storage.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/split|POST|Splits a presentation file and stores the output parts on a storage.|[Split](https://apireference.aspose.cloud/slides/#/Document/Split)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the presentation in a storage.|
|options|object|body|false|The [format-specific options](/slides/conversion-options/) for the output files.|
|format|string|query|false|The format for output files. See [the table](/slides/split-presentations#available-formats-for-output-files/) for available formats. The default value is `jpeg`.|
|width|integer|query|false|The width of each slide in the output files. Does not affect the HTML format.|
|height|integer|query|false|The height of each slide in the output files. Does not affect the HTML format.|
|from|integer|query|false|The 1-based starting slide number for the splitting. If it is not specified, the splitting starts from the first slide of the presentation.|
|to|integer|query|false|The 1-based last slide number for the splitting. If it is not specified, the splitting ends at the last slide of the presentation.|
|destFolder|string|query|false|The storage folder where the output files will be uploaded. If it is not specified, the files will be uploaded to the folder where the presentation is saved.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder path where the presentation is saved.|
|storage|string|query|false|The name of the storage where the presentation is saved. If it is not specified, the default storage is assumed.|
|fontsFolder|string|query|false|The path to the storage folder containing custom fonts that can be used in the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **Splitting All Slides**

Split **MyFolder/MyPresentation.pptx** file from a default storage into a set of JPEG images and save them to the same folder.

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
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/split?folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "slides": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg",
            "relation": "self",
            "linkType": "image/jpeg",
            "title": "Slide 1"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_2.jpeg",
            "relation": "self",
            "linkType": "image/jpeg",
            "title": "Slide 2"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_3.jpeg",
            "relation": "self",
            "linkType": "image/jpeg",
            "title": "Slide 3"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

``` csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split all slides in the presentation.
        var response = slidesApi.Split("MyPresentation.pptx", folder: "MyFolder");

        foreach (var slide in response.Slides)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split all slides in the presentation.
        SplitDocumentResult response = slidesApi.split("MyPresentation.pptx", null, null, null, null, null, null, null, null, "MyFolder", null, null);

        for (ResourceUri slide : response.getSlides())
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
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

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Split all slides in the presentation.
$response = $slidesApi->split("MyPresentation.pptx", null, null, null, null, null, null, null, null, "MyFolder");

foreach ($response->getSlides() as $slide)
{
    // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
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

# Split all slides in the presentation.
response = slides_api.split("MyPresentation.pptx", nil, nil, nil, nil, nil, nil, nil, nil, "MyFolder")

for slide in response.slides
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
    puts slide.href
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Split all slides in the presentation.
response = slides_api.split("MyPresentation.pptx", None, None, None, None, None, None, None, None, "MyFolder")

for slide in response.slides:
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
    print(slide.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Split all slides in the presentation.
slidesApi.split("MyPresentation.pptx", null, null, null, null, null, null, null, null, "MyFolder").then(response => {
    response.body.slides.forEach(slide => {
        // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split all slides in the presentation.
        SplitDocumentResult response = slidesApi.split("MyPresentation.pptx", null, null, null, null, null, null, null, null, "MyFolder", null, null);

        for (ResourceUri slide : response.getSlides())
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
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

    // Split all slides in the presentation.
    auto response = slidesApi->split(
        to_string_t("MyPresentation.pptx"), std::nullptr_t(), string_t(), boost::none, boost::none, boost::none, boost::none, 
        string_t(), string_t(), to_string_t("MyFolder")).get();

    for (auto slide : response->getSlides())
    {
        // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
        std::cout << to_utf8string(slide->getHref()) << std::endl;
    }

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";
my $slidesApi = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Split all slides in the presentation.
my %splitParams = ("name" => "MyPresentation.pptx", "folder" => "MyFolder");
my $response = $slidesApi->split(%splitParams);

for $slide (@{$response->{slides}}) {
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyFolder/MyPresentation_1.jpeg, etc.
    print $slide->{href}, "\n";
}
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **Splitting a Range of Slides**

Split the 2nd and 3rd slides from **MyFolder/MyPresentation.pptx** file, convert the slides to PNG format, and store them to **MyImages** folder.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Split the Presentation**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/split?format=Png&from=2&to=3&destFolder=MyImages&folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "slides": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png",
            "relation": "self",
            "linkType": "image/png",
            "title": "Slide 2"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_3.png",
            "relation": "self",
            "linkType": "image/png",
            "title": "Slide 3"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

``` csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split the 2nd and 3rd slides and save them to PNG format.
        var response = slidesApi.Split("MyPresentation.pptx", format: SlideExportFormat.Png, from: 2, to: 3, destFolder: "MyImages", folder: "MyFolder");

        foreach (ResourceUri slide in response.Slides)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split the 2nd and 3rd slides and save them to PNG format.
        SplitDocumentResult response = slidesApi.split("MyPresentation.pptx", null, SlideExportFormat.PNG, null, null, 2, 3, "MyImages", null, "MyFolder", null, null);

        for (ResourceUri slide : response.getSlides())
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
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

// Split the 2nd and 3rd slides and save them to PNG format.
$response = $slidesApi->split("MyPresentation.pptx", null, SlideExportFormat::PNG, null, null, 2, 3, "MyImages", null, "MyFolder");

foreach ($response->getSlides() as $slide)
{
    // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
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

# Split the 2nd and 3rd slides and save them to PNG format.
response = slides_api.split("MyPresentation.pptx", nil, SlideExportFormat::PNG, nil, nil, 2, 3, "MyImages", nil, "MyFolder")

for slide in response.slides
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
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

# Split the 2nd and 3rd slides and save them to PNG format.
response = slides_api.split("MyPresentation.pptx", None, SlideExportFormat.PNG, None, None, 2, 3, "MyImages", None, "MyFolder")

for slide in response.slides:
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
    print(slide.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Split the 2nd and 3rd slides and save them to PNG format.
slidesApi.split("MyPresentation.pptx", null, "png", null, null, 2, 3, "MyImages", null, "MyFolder").then(response => {
    response.body.slides.forEach(slide => {
        // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Split the 2nd and 3rd slides and save them to PNG format.
        SplitDocumentResult response = slidesApi.split("MyPresentation.pptx", null, SlideExportFormat.PNG, null, null, 2, 3, "MyImages", null, "MyFolder", null, null);

        for (ResourceUri slide : response.getSlides())
        {
            // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
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

    // Split the 2nd and 3rd slides and save them to PNG format.
    auto response = slidesApi->split(
        to_string_t("MyPresentation.pptx"), std::nullptr_t(), to_string_t("png"), boost::none, boost::none, 2, 3, 
        to_string_t("MyImages"), string_t(), to_string_t("MyFolder")).get();

    for (auto slide : response->getSlides())
    {
        // Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
        std::cout << to_utf8string(slide->getHref()) << std::endl;
    }

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";
my $slidesApi = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Split the 2nd and 3rd slides and save them to PNG format.
my %splitParams = ("name" => "MyPresentation.pptx", "format" => "png", "from" => 2, "to" => 3, "dest_folder" => "MyImages", "folder" => "MyFolder");
my $response = $slidesApi->split(%splitParams);

for $slide (@{$response->{slides}}) {
    # Output: https://api.aspose.cloud/v3.0/slides/storage/file/MyImages/MyPresentation_2.png, etc.
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
