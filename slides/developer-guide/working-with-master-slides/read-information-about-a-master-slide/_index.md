---
title: "Read Information about a Master Slide"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- design
- slide
- master
type: docs
url: /read-information-about-a-master-slide/
weight: 20
---

## **Introduction**

Aspose.Slides Cloud API allows you to read information of a master slide from a PowerPoint presentation. With the following method, you can read the slide name, layout slides of the master slide, depending slides, etc.

## **GetMasterSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/masterSlides/{slideIndex}|GET|Reads information of a master slide from a presentation.|[GetMasterSlide](https://apireference.aspose.cloud/slides/#/MasterSlides/GetMasterSlide)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the master slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read the name of the **second** master slide and titles of the layout slides depending on the master slide from the document **MyFolder/MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read Information of the Master Slide**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides/2?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "name": "Custom Design",
    "layoutSlides": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/2?folder=MyFolder",
            "relation": "self",
            "title": "Title Slide, Type: Title"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/3?folder=MyFolder",
            "relation": "self",
            "title": "Title and Content, Type: TitleAndObject"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/4?folder=MyFolder",
            "relation": "self",
            "title": "Section Header, Type: SectionHeader"
        }
    ],
    "dependingSlides": [],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides/2?folder=MyFolder",
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
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Read information of the first master slide from the document MyFolder/MyPresentation.pptx.
        var masterSlide = slidesApi.GetMasterSlide("MyPresentation.pptx", 1, null, "MyFolder");

        Console.WriteLine($"Master slide name: {masterSlide.Name}");

        Console.WriteLine("\r\nTitles of the layout slides:");
        foreach (var layoutSlide in masterSlide.LayoutSlides)
        {
            Console.WriteLine($"\t{layoutSlide.Title}");
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

        // Read information of the first master slide from the document MyFolder/MyPresentation.pptx.
        MasterSlide masterSlide = slidesApi.getMasterSlide("MyPresentation.pptx", 1, null, "MyFolder", null);

        System.out.println("Master slide name: " + masterSlide.getName());

        System.out.println("\r\nTitles of the layout slides:");
        for (ResourceUri layoutSlide : masterSlide.getLayoutSlides()) {
            System.out.println("\t" + layoutSlide.getTitle());
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

// Read information of the first master slide from the document MyFolder/MyPresentation.pptx.
$masterSlide = $slidesApi->getMasterSlide("MyPresentation.pptx", 1, null, "MyFolder");

echo "Master slide name: ", $masterSlide->getName(), PHP_EOL;

echo PHP_EOL, "Titles of the layout slides:", PHP_EOL;
foreach ($masterSlide->getLayoutSlides() as $layoutSlide) {
    echo "\t", $layoutSlide->getTitle(), PHP_EOL;
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

# Read information of the first master slide from the document MyFolder/MyPresentation.pptx.
master_slide = slides_api.get_master_slide("MyPresentation.pptx", 1, nil, "MyFolder")

puts "Master slide name: #{master_slide.name}"

puts "\nTitles of the layout slides:"
for layout_slide in master_slide.layout_slides
    puts "\t #{layout_slide.title}"
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Read information of the first master slide from the document MyFolder/MyPresentation.pptx.
master_slide = slides_api.get_master_slide("MyPresentation.pptx", 1, None, "MyFolder")

print(f"Master slide name: {master_slide.name}\n")

print("Titles of the layout slides:")
for layout_slide in master_slide.layout_slides:
    print(f"\t {layout_slide.title}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Read information of the first master slide from the document MyFolder/MyPresentation.pptx.
slidesApi.getMasterSlide("MyPresentation.pptx", 1, null, "MyFolder").then(masterSlide => {
    console.log("Master slide name: ", masterSlide.body.name);

    console.log("\nTitles of the layout slides:");
    masterSlide.body.layoutSlides.forEach(layoutSlide => {
        console.log("\t", layoutSlide.title);
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
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Read information of the first master slide from the document MyFolder/MyPresentation.pptx.
    auto masterSlide = slidesApi->getMasterSlide(L"MyPresentation.pptx", 1, L"", L"MyFolder").get();

    std::wcout << "Master slide name: " << masterSlide->getName() << std::endl;

    std::wcout << std::endl << "Titles of the layout slides:" << std::endl;
    for (auto layoutSlide : masterSlide->getLayoutSlides()) {
        std::wcout << "\t" << layoutSlide->getTitle() << std::endl;
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

# Read information of the second master slide from the document MyFolder/MyPresentation.pptx.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, folder => "MyFolder");
my $master_slide = $slides_api->get_master_slide(%parameters);

print("Master slide name: $master_slide->{name}\n");

print("\nTitles of the layout slides:\n");
for my $layout_slide (@{$master_slide->{layout_slides}}) {
    print("\t$layout_slide->{title}\n");
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
