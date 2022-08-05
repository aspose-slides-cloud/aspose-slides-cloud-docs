---
title: "Extract Shapes from a Slide Using Third Party Storage"
type: docs
url: /extract-shapes-from-a-slide-using-third-party-storage/
weight: 10
---

## **Introduction**

This article shows you how to extract shapes from a slide in PowerPoint presentation saved to third-party storage. The code examples below use `GetShapes` method described in [Extract Shapes from a Slide](/slides/extract-shapes-from-a-slide/).

{{% alert color="primary" %}}

You need to configure third-party storage with Aspose Cloud before using these examples. Follow the instructions at [this page](https://docs.aspose.cloud/display/storagecloud/How+to+Configure+3rd+Party+Cloud+Storages) to configure your required storage.

{{% /alert %}} 

## **Examples**

Read information about **all shapes** placed on the **second** slide from **MyFolder/MyPresentation.pptx** document saved to Google Drive Storage. The storage is called **MyGoogleStorage** in Aspose Cloud.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get All Shapes**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes?folder=MyFolder&storage=MyGoogleStorage" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "shapesLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1?folder=MyFolder",
            "relation": "self",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/2?folder=MyFolder",
            "relation": "self",
            "slideIndex": 2
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
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
using System;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all shapes from the second slide.
        var shapes = slidesApi.GetShapes("MyPresentation.pptx", 2, null, "MyFolder", "MyGoogleStorage");

        // Print the number of shapes.
        Console.WriteLine($"The second slide contains {shapes.ShapesLinks.Count} shapes.");
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
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all shapes from the second slide.
        var shapes = slidesApi.getShapes("MyPresentation.pptx", 2, null, "MyFolder", "MyGoogleStorage", null);

        // Print the number of shapes.
        System.out.println("The second slide contains " + shapes.getShapesLinks().size() + " shapes.");
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

// Get all shapes from the second slide.
$shapes = $slidesApi->getShapes("MyPresentation.pptx", 2, null, "MyFolder", "MyGoogleStorage");

// Print the number of shapes.
print("The second slide contains " . count($shapes->getShapesLinks()) . " shapes.");
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

# Get all shapes from the second slide.
shapes = slides_api.get_shapes("MyPresentation.pptx", 2, nil, "MyFolder", "MyGoogleStorage")

# Print the number of shapes.
print "The second slide contains #{shapes.shapes_links.length} shapes."
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get all shapes from the second slide.
shapes = slides_api.get_shapes("MyPresentation.pptx", 2, None, "MyFolder", "MyGoogleStorage")

# Print the number of shapes.
print(f"The second slide contains {len(shapes.shapes_links)} shapes.")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Get all shapes from the second slide.
slidesApi.getShapes("MyPresentation.pptx", 2, null, "MyFolder", "MyGoogleStorage").then((shapes) => {
    // Print the number of shapes.
    console.log("The second slide contains " + shapes.body.shapesLinks.length + " shapes.")
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
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Get all shapes from the second slide.
    auto shapes = slidesApi->getShapes(L"MyPresentation.pptx", 2, L"", L"MyFolder", L"MyGoogleStorage").get();

    // Print the number of shapes.
    std::wcout << "The second slide contains " << shapes->getShapesLinks().size() << " shapes.";

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

# Get all shapes from the second slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, folder => "MyFolder", storage => "MyGoogleStorage");
my $shapes = $slides_api->get_shapes(%parameters);

# Print the number of shapes.
print "The second slide contains " . scalar @{$shapes->{shapes_links}} . " shapes.";
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
