---
title: "Copy a Master Slide"
type: docs
url: /copy-a-master-slide/
weight: 30
---

## **Introduction**

With Aspose.Slides Cloud, you can copy a master slide from one PowerPoint presentation to another. The following method allows you to specify file names of the presentations and an index of the master slide to be copied. You can also apply the master slide to all presentation slides at once.

## **CopyMasterSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/masterSlides|POST|Copies a master slide from one presentation to another.|[CopyMasterSlide](https://apireference.aspose.cloud/slides/#/MasterSlides/CopyMasterSlide)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a destination presentation file.|
|cloneFrom|string|query|true|The name of a source presentation file.|
|cloneFromPosition|integer|query|true|The 1-based index of the master slide.|
|cloneFromPassword|string|header|false|The password to open the source presentation.|
|cloneFromStorage|string|query|false|The name of the storage containing the source presentation.|
|applyToAll|boolean|query|false|Specifies whether to apply the master slide to every presentation slide. False by default.|
|password|string|header|false|The password to open the destination presentation.|
|folder|string|query|false|The path to the folder containing the destination presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{% alert color="primary" %}} 

The related layout slides are automatically copied from the source presentation to the destination presentation.

{{% /alert %}} 

### **Examples**

Copy the **first** master slide from the document **MyTemplates/MainTemplate.pptx** to the document **MyFolder/MyPresentation.pptx**. Apply the master slide to all slides. The presentation files are saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Copy the Master Slide**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides?cloneFrom=MyTemplates/MainTemplate.pptx&cloneFromPosition=1&applyToAll=true&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "name": "Custom Design",
    "layoutSlides": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/4?folder=MyFolder",
            "relation": "self",
            "title": "Title Slide, Type: Title"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/5?folder=MyFolder",
            "relation": "self",
            "title": "Title and Content, Type: TitleAndObject"
        }
    ],
    "dependingSlides": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder",
            "relation": "self"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides/3?folder=MyFolder",
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

        // Copy the first master slide from MyTemplates/MainTemplate.pptx to MyFolder/MyPresentation.pptx and apply the master slide to all slides.
        var masterSlide = slidesApi.CopyMasterSlide("MyPresentation.pptx", "MyTemplates/MainTemplate.pptx", 1, null, null, true, null, "MyFolder");

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

        // Copy the first master slide from MyTemplates/MainTemplate.pptx to MyFolder/MyPresentation.pptx and apply the master slide to all slides.
        MasterSlide masterSlide = slidesApi.copyMasterSlide("MyPresentation.pptx", "MyTemplates/MainTemplate.pptx", 1, null, null, true, null, "MyFolder", null);

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

// Copy the first master slide from MyTemplates/MainTemplate.pptx to MyFolder/MyPresentation.pptx and apply the master slide to all slides.
$masterSlide = $slidesApi->copyMasterSlide("MyPresentation.pptx", "MyTemplates/MainTemplate.pptx", 1, null, null, true, null, "MyFolder");

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

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Copy the first master slide from MyTemplates/MainTemplate.pptx to MyFolder/MyPresentation.pptx and apply the master slide to all slides.
master_slide = slides_api.copy_master_slide("MyPresentation.pptx", "MyTemplates/MainTemplate.pptx", 1, nil, nil, true, nil, "MyFolder")

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

# Copy the first master slide from MyTemplates/MainTemplate.pptx to MyFolder/MyPresentation.pptx and apply the master slide to all slides.
master_slide = slides_api.copy_master_slide("MyPresentation.pptx", "MyTemplates/MainTemplate.pptx", 1, None, None, True, None, "MyFolder")

print(f"Master slide name: {master_slide.name}\n")

print("Titles of the layout slides:")
for layout_slide in master_slide.layout_slides:
    print(f"\t {layout_slide.title}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Copy the first master slide from MyTemplates / MainTemplate.pptx to MyFolder / MyPresentation.pptx and apply the master slide to all slides.
slidesApi.copyMasterSlide("MyPresentation.pptx", "MyTemplates/MainTemplate.pptx", 1, null, null, true, null, "MyFolder").then(masterSlide => {
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

    // Copy the first master slide from MyTemplates / MainTemplate.pptx to MyFolder / MyPresentation.pptx and apply the master slide to all slides.
    auto masterSlide = slidesApi->copyMasterSlide(L"MyPresentation.pptx", L"MyTemplates/MainTemplate.pptx", 1, L"", L"", true, L"", L"MyFolder").get();

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

# Copy the first master slide from MyTemplates/MainTemplate.pptx to MyFolder/MyPresentation.pptx and apply the master slide to all slides.
my %parameters = (name => "MyPresentation.pptx", clone_from => "MyTemplates/MainTemplate.pptx", clone_from_position => 1, apply_to_all => true, folder => "MyFolder");
my $master_slide = $slides_api->copy_master_slide(%parameters);

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
