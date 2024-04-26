---
title: "Get Image Information from a Slide"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- slide
- image
type: docs
url: /get-image-information-from-a-slide/
weight: 20
---

## **Introduction**

The following API method allows you to easily read information about images placed on a slide in a PowerPoint document. You can find out the following image properties: width, height, type, etc.

## **GetSlideImages**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/images|GET|Returns information about the images placed on a slide.|[GetSlideImages](https://apireference.aspose.cloud/slides/#/Images/GetSlideImages)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read information about the images placed on the **first** slide in **MyFolder/MyPresentation.pptx** file saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read Image Information**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/images?folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "list": [
        {
            "width": 1021,
            "height": 308,
            "contentType": "image/png",
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/1?folder=MyFolder",
                "relation": "self"
            },
            "alternateLinks": [
                {
                    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/1/jpeg?folder=MyFolder",
                    "relation": "alternate"
                },
                {
                    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/1/png?folder=MyFolder",
                    "relation": "alternate"
                },
                {
                    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/1/gif?folder=MyFolder",
                    "relation": "alternate"
                }
            ]
        },
        {
            "width": 430,
            "height": 368,
            "contentType": "image/jpeg",
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/2?folder=MyFolder",
                "relation": "self"
            },
            "alternateLinks": [
                {
                    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/2/jpeg?folder=MyFolder",
                    "relation": "alternate"
                },
                {
                    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/2/png?folder=MyFolder",
                    "relation": "alternate"
                },
                {
                    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/2/gif?folder=MyFolder",
                    "relation": "alternate"
                }
            ]
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/images?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System.Diagnostics;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Read information about the images placed on the first slide.
        var imagesInfo = slidesApi.GetSlideImages("MyPresentation.pptx", 1, null, "MyFolder");

        // Print information about the images.
        foreach (var imageInfo in imagesInfo.List)
        {
            Debug.WriteLine($"{imageInfo.Width}x{imageInfo.Height}, {imageInfo.ContentType}");
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
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Read information about the images placed on the first slide.
        Images imagesInfo = slidesApi.getSlideImages("MyPresentation.pptx", 1, null, "MyFolder", null);

        // Print information about the images.
        for (Image imageInfo : imagesInfo.getList()) {
            System.out.printf("%sx%s, %s\n", imageInfo.getWidth(), imageInfo.getHeight(), imageInfo.getContentType());
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
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Read information about the images placed on the first slide.
$imagesInfo = $slidesApi->getSlideImages("MyPresentation.pptx", 1, null, "MyFolder");

// Print information about the images.
foreach ($imagesInfo->getList() as $imageInfo) {
    echo sprintf("%sx%s, %s\n", $imageInfo->getWidth(), $imageInfo->getHeight(), $imageInfo->getContentType());
}
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

# Read information about the images placed on the first slide.
images_info = slides_api.get_slide_images("MyPresentation.pptx", 1, nil, "MyFolder")

# Print information about the images.
for image_info in images_info.list
    puts "#{image_info.width}x#{image_info.height}, #{image_info.content_type}"
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Read information about the images placed on the first slide.
images_info = slides_api.get_slide_images("MyPresentation.pptx", 1, None, "MyFolder")

# Print information about the images.
for image_info in images_info.list:
    print(f"{image_info.width}x{image_info.height}, {image_info.content_type}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Read information about the images placed on the first slide.
slidesApi.getSlideImages("MyPresentation.pptx", 1, null, "MyFolder").then(imagesInfo => {
    // Print information about the images.
    imagesInfo.body.list.forEach(imageInfo => {
        console.log(imageInfo.width + "x" + imageInfo.height + ", " + imageInfo.contentType);
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Read information about the images placed on the first slide.
    auto imagesInfo = slidesApi->getSlideImages(L"MyPresentation.pptx", 1, L"", L"MyFolder").get();

    // Print information about the images.
    for (auto imageInfo : imagesInfo->getList()) {
        std::wcout << imageInfo->getWidth() << "x" << imageInfo->getHeight() << ", " << imageInfo->getContentType() << std::endl;
    }

    std::cin.get();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Read information about the images placed on the first slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, folder => "MyFolder");
my $images_info = $slides_api->get_slide_images(%parameters);

# Print information about the images.
for my $image_info (@{$images_info->{list}}) {
    print("$image_info->{width}x$image_info->{height}, $image_info->{content_type}\n");
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
