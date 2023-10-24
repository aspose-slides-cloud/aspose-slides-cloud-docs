---
title: "Read Information about Layout Slides"
type: docs
url: /read-information-about-layout-slides/
weight: 10
---

## **Introduction**

Slide layouts contain formatting, positioning, and placeholder boxes for all of the content that appears on a slide. The following method allows you to read information of all layout slides from a PowerPoint presentation.

## **GetLayoutSlides**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/layoutSlides|GET|Reads information of layout slides from a presentation.|[GetLayoutSlides](https://apireference.aspose.cloud/slides/#/LayoutSlides/GetLayoutSlides)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read titles of layout slides from the document **MyFolder/MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read Information of Layout Slides**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "slideList": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1?folder=MyFolder",
            "relation": "self",
            "title": "Title Slide, Type: Title"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/2?folder=MyFolder",
            "relation": "self",
            "title": "Title and Content, Type: TitleAndObject"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/3?folder=MyFolder",
            "relation": "self",
            "title": "Section Header, Type: SectionHeader"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides?folder=MyFolder",
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
using System;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Read information of layout slides from the document MyFolder/MyPresentation.pptx.
        var layoutSlides = slidesApi.GetLayoutSlides("MyPresentation.pptx", null, "MyFolder");

        // Print titles of the layout slides.
        foreach (var slide in layoutSlides.SlideList)
        {
            Console.WriteLine(slide.Title);
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

        // Read information of layout slides from the document MyFolder/MyPresentation.pptx.
        LayoutSlides layoutSlides = slidesApi.getLayoutSlides("MyPresentation.pptx", null, "MyFolder", null);

        // Print titles of the layout slides.
        for (ResourceUri slide : layoutSlides.getSlideList()) {
            System.out.println(slide.getTitle());
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

// Read information of layout slides from the document MyFolder/MyPresentation.pptx.
$layoutSlides = $slidesApi->getLayoutSlides("MyPresentation.pptx", null, "MyFolder");

// Print titles of the layout slides.
foreach ($layoutSlides->getSlideList() as $slide) {
    echo $slide->getTitle(), PHP_EOL;
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

# Read information of layout slides from the document MyFolder/MyPresentation.pptx.
layout_slides = slides_api.get_layout_slides("MyPresentation.pptx", nil, "MyFolder")

# Print titles of the layout slides.
for slide in layout_slides.slide_list
    puts slide.title
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Read information of layout slides from the document MyFolder/MyPresentation.pptx.
layout_slides = slides_api.get_layout_slides("MyPresentation.pptx", None, "MyFolder")

# Print titles of the layout slides.
for slide in layout_slides.slide_list:
    print(slide.title)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Read information of layout slides from the document MyFolder/MyPresentation.pptx.
slidesApi.getLayoutSlides("MyPresentation.pptx", null, "MyFolder").then((layoutSlides) => {
    // Print titles of the layout slides.
    layoutSlides.body.slideList.forEach(slide =>
        console.log(slide.title)
    )
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
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Read information of layout slides from the document MyFolder/MyPresentation.pptx.
    auto layoutSlides = slidesApi->getLayoutSlides(L"MyPresentation.pptx", L"", L"MyFolder").get();

    // Print titles of the layout slides.
    for (auto slide : layoutSlides->getSlideList()) {
        std::wcout << slide->getTitle() << std::endl;
    }

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

# Read information of layout slides from the document MyFolder/MyPresentation.pptx.
my %parameters = (name => "MyPresentation.pptx", folder => "MyFolder");
my $layout_slides = $slides_api->get_layout_slides(%parameters);

# Print titles of the layout slides.
for my $slide (@{$layout_slides->{slide_list}}) {
    print($slide->{title}, "\n");
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
