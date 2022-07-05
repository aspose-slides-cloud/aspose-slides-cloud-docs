---
title: "Get the Number of Slides from a PowerPoint Presentation"
type: docs
url: /get-the-number-of-slides-from-a-powerpoint-presentation/
weight: 90
---

## **Introduction**

This article shows you how to get the number of slides from a PowerPoint document using Aspose.Slides for Cloud API in your applications. The code examples below use the [GetSlides](https://apireference.aspose.cloud/slides/#/Slides/GetSlides) method.

## **Examples**

Get the number of slides from **MyFolder/MyPresentation.pptx** document saved to the default Cloud storage. Use **MyPassword** string to open the password-protected presentation.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Information about Slides**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "password: MyPassword"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "slideList": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder",
            "relation": "self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder",
            "relation": "self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder",
            "relation": "self"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder",
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

        // Get information about presentation slides.
        var slidesInfo = slidesApi.GetSlides("MyPresentation.pptx", "MyPassword", "MyFolder");

        // Print the number of slides.
        Debug.WriteLine(slidesInfo.SlideList.Count);
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

        // Get information about presentation slides.
        var slidesInfo = slidesApi.getSlides("MyPresentation.pptx", "MyPassword", "MyFolder", null);

        // Print the number of slides.
        System.out.println(slidesInfo.getSlideList().size());
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

// Get information about presentation slides.
$slidesInfo = $slidesApi->getSlides("MyPresentation.pptx", "MyPassword", "MyFolder");

// Print the number of slides.
echo count($slidesInfo->getSlideList());
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

# Get information about presentation slides.
slides_info = slides_api.get_slides("MyPresentation.pptx", "MyPassword", "MyFolder")

# Print the number of slides.
print slides_info.slide_list.count()
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get information about presentation slides.
slides_info = slides_api.get_slides("MyPresentation.pptx", "MyPassword", "MyFolder")

# Print the number of slides.
print(len(slides_info.slide_list))
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Get information about presentation slides.
slidesApi.getSlides("MyPresentation.pptx", "MyPassword", "MyFolder").then((slidesInfo) => {
    // Print the number of slides.
    console.log(slidesInfo.body.slideList.length)
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

    // Get information about presentation slides.
    auto slidesInfo = slidesApi->getSlides(L"MyPresentation.pptx", L"MyPassword", L"MyFolder").get();

    // Print the number of slides.
    std::wcout << slidesInfo->getSlideList().size();

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

# Get information about presentation slides.
my %parameters = (name => "MyPresentation.pptx", password => "MyPassword", folder => "MyFolder");
my $slides_info = $slides_api->get_slides(%parameters);

# Print the number of slides.
print scalar @{$slides_info->{slide_list}};
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
