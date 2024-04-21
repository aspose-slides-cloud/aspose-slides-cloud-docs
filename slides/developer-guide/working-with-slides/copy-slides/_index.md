---
title: "Copy Slides"
keywords: "PowerPoint, presentation, REST API, Cloud API, slide, copy a slide"
type: docs
url: /copy-slides/
weight: 50
---

## **Introduction**

Aspose.Slides Cloud lets you easily copy a slide with its content to create a new slide in a PowerPoint presentation. The presentation must be already saved to a storage. You can copy a slide at the end of the presentation or at a specified position. You can copy a slide either within the same presentation or by specifying an original one. In the second case, the original presentation must also be in the Cloud storage. Both presentations can be password protected and you can specify passwords. 

## **CopySlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/copy|POST|Copies a slide to create a new slide.|[CopySlide](https://apireference.aspose.cloud/slides/#/Slides/CopySlide)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
|slideToCopy|integer|query|true|The 1-based index of the slide to be copied from the source presentation.|
|position|integer|query|false|The 1-based index for the new slide. If the position is not specified, the slide will be added to the end.|
|source|string|query|false|The name of the presentation file to copy the slide from. If not specified, the slide is copied from the current presentation.|
|sourcePassword|string|header|false|The password for the presentation to copy the slide from.|
|sourceStorage|string|query|false|The name of the storage contaning the source presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Copy a slide at index **4** from **MyResources/MyCharts.pptx** file saved to the default storage and paste it at index **2** into **MyFolder/MyPresentation.pptx** file saved to **MyStorage**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Copy the Slide**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/copy?slideToCopy=4&position=2&source=MyResources/MyCharts.pptx&folder=MyFolder&storage=MyStorage" \
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
        var api = new SlidesApi("my_client_id", "my_client_secret");

        // Copy the fourth slide.
        var response = api.CopySlide("MyPresentation.pptx", 4, 2, "MyResources/MyCharts.pptx", null, null, null, "MyFolder", "MyStorage");

        // Print links to all slides from MyPresentation.pptx.
        foreach (var resourceUri in response.SlideList)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
            Console.WriteLine(resourceUri.Href);
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

        // Copy the fourth slide.
        Slides response = slidesApi.copySlide("MyPresentation.pptx", 4, 2, "MyResources/MyCharts.pptx", null, null, null, "MyFolder", "MyStorage");

        // Print links to all slides from MyPresentation.pptx.
        for (ResourceUri resourceUri : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
            System.out.println(resourceUri.getHref());
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

// Copy the fourth slide.
$response = $slidesApi->copySlide("MyPresentation.pptx", 4, 2, "MyResources/MyCharts.pptx", null, null, null, "MyFolder", "MyStorage");

// Print links to all slides from MyPresentation.pptx.
foreach ($response->getSlideList() as $resourceUri) {
    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    echo $resourceUri->getHref(), "\n";
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

# Copy the fourth slide.
response = slides_api.copy_slide("MyPresentation.pptx", 4, 2, "MyResources/MyCharts.pptx", nil, nil, nil, "MyFolder", "MyStorage")

# Print links to all slides from MyPresentation.pptx.
for resource_uri in response.slide_list
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    puts resource_uri.href
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Copy the fourth slide.
response = slides_api.copy_slide("MyPresentation.pptx", 4, 2, "MyResources/MyCharts.pptx", None, None, None, "MyFolder", "MyStorage")

# Print links to all slides from MyPresentation.pptx.
for resource_uri in response.slide_list:
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print(resource_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Copy the fourth slide.
slidesApi.copySlide("MyPresentation.pptx", 4, 2, "MyResources/MyCharts.pptx", null, null, null, "MyFolder", "MyStorage").then(response => {
    // Print links to all slides from MyPresentation.pptx.
    response.body.slideList.forEach(resourceUri => {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
        console.log(resourceUri.href);
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
        var slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Copy the fourth slide.
        var response = slidesApi.copySlide("MyPresentation.pptx", 4, 2, "MyResources/MyCharts.pptx", null, null, null, "MyFolder", "MyStorage");

        // Print links to all slides from MyPresentation.pptx.
        for (var resourceUri : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
            System.out.println(resourceUri.getHref());
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

    // Copy the fourth slide.
    auto response = slidesApi->copySlide(
        L"MyPresentation.pptx", 4, 2, L"MyResources/MyCharts.pptx", L"", L"", L"", L"MyFolder", L"MyStorage").get();

    // Print links to all slides from MyPresentation.pptx.
    for (auto resourceUri : response->getSlideList()) {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
        std::wcout << resourceUri->getHref() << std::endl;
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

# Copy the fourth slide.
my %parameters = (name => "MyPresentation.pptx", slide_to_copy => 4, position => 2, 
                  source => "MyResources/MyCharts.pptx", folder => "MyFolder", storage => "MyStorage");
my $response = $slides_api->copy_slide(%parameters);

# Print links to all slides from MyPresentation.pptx.
for my $resource_uri (@{$response->{slide_list}}) {
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print $resource_uri->{href}, "\n";
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
