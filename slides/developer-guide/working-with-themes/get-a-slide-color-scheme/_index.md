---
title: "Get a Slide Color Scheme"
keywords: "PowerPoint, presentation, REST API, Cloud API, slide, color, scheme, color scheme, text color, background color, accent color, hyperlink color, light"
type: docs
url: /get-a-slide-color-scheme/
weight: 40
---

## **Introduction**

Theme colors contain text and background colors, accent colors, and hyperlink colors. With Aspose.Slides Cloud, you can use the following API method to read information of a slide color scheme from a PowerPoint presentation.

## **GetColorScheme**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/theme/colorScheme|GET|Retrieves a color scheme from a presentation slide.|[GetColorScheme](https://apireference.aspose.cloud/slides/#/Theme/GetColorScheme)|

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

Read information of the color scheme of the **first** slide from the document **MyFolder/MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read the Color Scheme**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/theme/colorScheme?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "accent1": "#FFE48312",
    "accent2": "#FFBD582C",
    "accent3": "#FF865640",
    "accent4": "#FF9B8357",
    "accent5": "#FFC2BC80",
    "accent6": "#FF94A088",
    "dark1": "#FF000000",
    "dark2": "#FF637052",
    "followedHyperlink": "#FF8C8C8C",
    "hyperlink": "#FF2998E3",
    "light1": "#FFFFFFFF",
    "light2": "#FFCCDDEA",
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/theme/colorScheme?folder=MyFolder",
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
using System;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Read the color scheme applied to the first slide.
        var colorScheme = slidesApi.GetColorScheme("MyPresentation.pptx", 1, null, "MyFolder");

        // Print a hyperlink color.
        Console.WriteLine("Hyperlink color: " + colorScheme.Hyperlink);
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

        // Read the color scheme applied to the first slide.
        ColorScheme colorScheme = slidesApi.getColorScheme("MyPresentation.pptx", 1, null, "MyFolder", null);

        // Print a hyperlink color.
        System.out.println("Hyperlink color: " + colorScheme.getHyperlink());
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

// Read the color scheme applied to the first slide.
$colorScheme = $slidesApi->getColorScheme("MyPresentation.pptx", 1, null, "MyFolder");

// Print a hyperlink color.
echo "Hyperlink color: ", $colorScheme->getHyperlink();
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

# Read the color scheme applied to the first slide.
color_scheme = slides_api.get_color_scheme("MyPresentation.pptx", 1, nil, "MyFolder")

# Print a hyperlink color.
print "Hyperlink color: ", color_scheme.hyperlink
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Read the color scheme applied to the first slide.
color_scheme = slides_api.get_color_scheme("MyPresentation.pptx", 1, None, "MyFolder")

# Print a hyperlink color.
print("Hyperlink color:", color_scheme.hyperlink)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Read the color scheme applied to the first slide.
slidesApi.getColorScheme("MyPresentation.pptx", 1, null, "MyFolder").then(colorScheme => {
    // Print a hyperlink color.
    console.log("Hyperlink color:",  colorScheme.body.hyperlink);
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
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Read the color scheme applied to the first slide.
    auto colorScheme = slidesApi->getColorScheme(L"MyPresentation.pptx", 1, L"", L"MyFolder").get();

    // Print a hyperlink color.
    std::wcout << "Hyperlink color: " << colorScheme->getHyperlink();

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

# Read the color scheme applied to the first slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, folder => "MyFolder");
my $color_scheme = $slides_api->get_color_scheme(%parameters);

# Print a hyperlink color.
print "Hyperlink color: ", $color_scheme->{hyperlink};
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
