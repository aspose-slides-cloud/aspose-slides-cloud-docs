---
title: "Get Image Information from a Presentation"
type: docs
url: /get-image-information-from-a-presentation/
weight: 10
---

## **Introduction**

The following API method allows you to easily read information about all images contained in a PowerPoint document. You can find out the following image properties: width, height, type, etc.

## **GetPresentationImages**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/images|GET|Returns all image information from a PowerPoint document.|[GetPresentationImages](https://apireference.aspose.cloud/slides/#/Images/GetPresentationImages)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read information about all images contained in **MyFolder/MyPresentation.pptx** file saved to the default storage.

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
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images?folder=MyFolder" \
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
            "width": 426,
            "height": 361,
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
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images?folder=MyFolder",
        "relation": "self"
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

        // Read information about all images.
        var imagesInfo = slidesApi.GetPresentationImages("MyPresentation.pptx", null, "MyFolder");

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

        // Read information about all images.
        Images imagesInfo = slidesApi.getPresentationImages("MyPresentation.pptx", null, "MyFolder", null);

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

// Read information about all images.
$imagesInfo = $slidesApi->getPresentationImages("MyPresentation.pptx", null, "MyFolder");

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

# Read information about all images.
images_info = slides_api.get_presentation_images("MyPresentation.pptx", nil, "MyFolder")

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

# Read information about all images.
images_info = slides_api.get_presentation_images("MyPresentation.pptx", None, "MyFolder")

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

// Read information about all images.
slidesApi.getPresentationImages("MyPresentation.pptx", null, "MyFolder").then(imagesInfo => {
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

    // Read information about all images.
    auto imagesInfo = slidesApi->getPresentationImages(L"MyPresentation.pptx", L"", L"MyFolder").get();

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

# Read information about all images.
my %parameters = (name => "MyPresentation.pptx", folder => "MyFolder");
my $images_info = $slides_api->get_presentation_images(%parameters);

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
