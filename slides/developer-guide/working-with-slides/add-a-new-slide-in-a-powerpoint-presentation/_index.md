---
title: "Add a New Slide in a PowerPoint Presentation"
type: docs
url: /add-a-new-slide-in-a-powerpoint-presentation/
weight: 40
---

## **Introduction**

This article shows you how to add new slides in PowerPoint presentations using Aspose.Slides for Cloud API in your applications. A presentation must be already saved to a storage. You can add a new slide at the end of the presentation or at a specified position. When creating a new slide, a layout can be applied immediately.

## **CreateSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides|POST|Creates a new slide.|[CreateSlide](https://apireference.aspose.cloud/slides/#/Slides/CreateSlide)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of a presentation.|
|layoutAlias|string|query|false|The alias of a layout slide for a new slide. The alias may be a layout slide type, a layout slide name, or an index.|
|position|integer|query|false|The 1-based index for the new slide. If the position is not specified, the slide will be added to the end.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

**MyFolder/MyPresentation.pptx** document saved to **MyStorage** is containing two slides. Add a new slide at index **2** into the presentation and use the **third** layout for the new slide.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the New Slide**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?layoutAlias=3&position=2&folder=MyFolder&storage=MyStorage" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Length: 0"
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

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System;

class Application
{
    static void Main()
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Create a new slide.
        var response = api.CreateSlide("MyPresentation.pptx", "3", 2);

        // Print links to all slides.
        foreach (var slide in response.SlideList)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

        // Create a new slide.
        Slides response = slidesApi.createSlide("MyPresentation.pptx", "3", 2, null, "MyFolder", "MyStorage");

        // Print links to all slides.
        for (ResourceUri slide : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

// Create a new slide.
$response = $slidesApi->createSlide("MyPresentation.pptx", "3", 2, null, "MyFolder", "MyStorage");

// Print links to all slides.
foreach ($response->getSlideList() as $slide) {
    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

# Create a new slide.
response = slides_api.create_slide("MyPresentation.pptx", "3", 2, nil, "MyFolder", "MyStorage")

# Print links to all slides.
for slide in response.slide_list
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

# Create a new slide.
response = slides_api.create_slide("MyPresentation.pptx", "3", 2, None, "MyFolder", "MyStorage")

# Print links to all slides.
for slide in response.slide_list:
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print(slide.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret")

// Create a new slide.
slidesApi.createSlide("MyPresentation.pptx", "3", 2, null, "MyFolder", "MyStorage").then((response) => {
    // Print links to all slides.
    response.body.slideList.forEach(slide =>
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
        console.log(slide.href)
    )
})
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

        // Create a new slide.
        Slides response = slidesApi.createSlide("MyPresentation.pptx", "3", 2, null, "MyFolder", "MyStorage");

        // Print links to all slides.
        for (ResourceUri slide : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"my_client_id", L"my_client_secret");

    // Create a new slide.
    auto response = slidesApi->createSlide(L"MyPresentation.pptx", L"3", 2, L"", L"MyFolder", L"MyStorage").get();

    // Print links to all slides.
    for (auto slide : response->getSlideList()) {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
        std::wcout << slide->getHref() << std::endl;
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

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Create a new slide.
my %parameters = (name => "MyPresentation.pptx", layout_alias => "3", position => 2, folder => "MyFolder", storage => "MyStorage");
$response = $slides_api->create_slide(%parameters);

# Print links to all slides.
for my $slide (@{$response->{slide_list}}) {
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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
