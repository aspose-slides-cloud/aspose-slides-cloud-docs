---
title: "Get a Slide Theme"
type: docs
url: /get-a-slide-theme/
weight: 5
---

## **Introduction**

The main properties of presentation design elements are determined by a presentation theme. Each theme uses its own unique set of colors, fonts and effects to create the overall look of your slides. The following API method allows you to read information about a slide theme from a PowerPoint presentation. 

## **GetTheme**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/theme|GET|Retrieves a slide theme from a presentation.|[GetTheme](https://apireference.aspose.cloud/slides/#/Theme/GetTheme)|

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

Read information about a theme of the **third** slide from the document **MyFolder/MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read the Slide Theme**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/theme?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "name": "Title Slide",
    "colorScheme": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/theme/colorScheme?folder=MyFolder",
        "relation": "self",
        "slideIndex": 3
    },
    "fontScheme": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/theme/fontScheme?folder=MyFolder",
        "relation": "self",
        "slideIndex": 3
    },
    "formatScheme": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/theme/formatScheme?folder=MyFolder",
        "relation": "self",
        "slideIndex": 3
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/theme?folder=MyFolder",
        "relation": "self",
        "slideIndex": 3
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

        // Read a theme from the third slide.
        var slideTheme = slidesApi.GetTheme("MyPresentation.pptx", 3, null, "MyFolder");

        // Print resource references to color scheme, font scheme and format scheme.
        Console.WriteLine(slideTheme.ColorScheme.Href);
        Console.WriteLine(slideTheme.FontScheme.Href);
        Console.WriteLine(slideTheme.FormatScheme.Href);
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

        // Read a theme from the third slide.
        Theme slideTheme = slidesApi.getTheme("MyPresentation.pptx", 3, null, "MyFolder", null);

        // Print resource references to color scheme, font scheme and format scheme.
        System.out.println(slideTheme.getColorScheme().getHref());
        System.out.println(slideTheme.getFontScheme().getHref());
        System.out.println(slideTheme.getFormatScheme().getHref());
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

// Read a theme from the third slide.
$slideTheme = $slidesApi->getTheme("MyPresentation.pptx", 3, null, "MyFolder");

// Print resource references to color scheme, font scheme and format scheme.
echo $slideTheme->getColorScheme()->getHref() . PHP_EOL;
echo $slideTheme->getFontScheme()->getHref() . PHP_EOL;
echo $slideTheme->getFormatScheme()->getHref();
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

# Read a theme from the third slide.
slide_theme = slides_api.get_theme("MyPresentation.pptx", 3, nil, "MyFolder")

# Print resource references to color scheme, font scheme and format scheme.
puts slide_theme.color_scheme.href
puts slide_theme.font_scheme.href
puts slide_theme.format_scheme.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Read a theme from the third slide.
slide_theme = slides_api.get_theme("MyPresentation.pptx", 3, None, "MyFolder")

# Print resource references to color scheme, font scheme and format scheme.
print(slide_theme.color_scheme.href)
print(slide_theme.font_scheme.href)
print(slide_theme.format_scheme.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Read a theme from the third slide.
slidesApi.getTheme("MyPresentation.pptx", 3, null, "MyFolder").then(slideTheme => {
    // Print resource references to color scheme, font scheme and format scheme.
    console.log(slideTheme.body.colorScheme.href);
    console.log(slideTheme.body.fontScheme.href);
    console.log(slideTheme.body.formatScheme.href);
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

    // Read a theme from the third slide.
    auto slideTheme = slidesApi->getTheme(L"MyPresentation.pptx", 3, L"", L"MyFolder").get();

    // Print resource references to color scheme, font scheme and format scheme.
    std::wcout << slideTheme->getColorScheme()->getHref() << std::endl;
    std::wcout << slideTheme->getFontScheme()->getHref() << std::endl;
    std::wcout << slideTheme->getFormatScheme()->getHref();

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

# Read a theme from the third slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 3, folder => "MyFolder");
my $slide_theme = $slides_api->get_theme(%parameters);

# Print resource references to color scheme, font scheme and format scheme.
print($slide_theme->{color_scheme}->{href} . "\n");
print($slide_theme->{font_scheme}->{href} . "\n");
print($slide_theme->{format_scheme}->{href});
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
