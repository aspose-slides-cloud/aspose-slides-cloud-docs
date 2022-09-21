---
title: "Copy Layout Slide from a PowerPoint Presentation"
type: docs
url: /copy-layout-slide-from-a-powerpoint-presentation/
weight: 30
---

## **Introduction**

With Aspose.Slides Cloud, you can copy a layout slide from one PowerPoint presentation to another. The following method allows you to specify file names of the presentations and an index of the layout slide to be copied.

## **CopyLayoutSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/layoutSlides|POST|Copies a layout slide from one presentation to another.|[CopyLayoutSlide](https://apireference.aspose.cloud/slides/#/LayoutSlides/CopyLayoutSlide)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a destination presentation file.|
|cloneFrom|string|query|true|The name of a source presentation file.|
|cloneFromPosition|integer|query|true|The index of the layout slide.|
|cloneFromPassword|string|header|false|The password to open the source presentation.|
|cloneFromStorage|string|query|false|The name of the storage containing the source presentation.|
|password|string|header|false|The password to open the destination presentation.|
|folder|string|query|false|The path to the folder containing the destination presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{% alert color="primary" %}} 

The related master slide is automatically copied from the source presentation to the destination presentation.

{{% /alert %}} 

### **Examples**

Copy the **third** layout slide from the presentation **MyTemplates/SalesTemplate.pptx** to the document **MyFolder/MyPresentation.pptx**. Both presentations have been saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Copy the Layout Slide**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides?cloneFrom=MyTemplates/SalesTemplate.pptx&cloneFromPosition=3&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "name": "Section Header",
    "type": "SectionHeader",
    "masterSlide": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides/2?folder=MyFolder",
        "relation": "self"
    },
    "dependingSlides": [],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/2?folder=MyFolder",
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

        // Copy the third layout slide.
        var layoutSlide = slidesApi.CopyLayoutSlide("MyPresentation.pptx", "MyTemplates/SalesTemplate.pptx", 3, folder: "MyFolder");

        // Print the layout slide name.
        Console.WriteLine(layoutSlide.Name);
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

        // Copy the third layout slide.
        var layoutSlide = slidesApi.copyLayoutSlide("MyPresentation.pptx", "MyTemplates/SalesTemplate.pptx", 3, null, null, null, "MyFolder", null);

        // Print the layout slide name.
        System.out.println(layoutSlide.getName());
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

// Copy the third layout slide.
$layoutSlide = $slidesApi->copyLayoutSlide("MyPresentation.pptx", "MyTemplates/SalesTemplate.pptx", 3, null, null, null, "MyFolder");

// Print the layout slide name.
echo $layoutSlide->getName();
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

# Copy the third layout slide.
layout_slide = slides_api.copy_layout_slide("MyPresentation.pptx", "MyTemplates/SalesTemplate.pptx", 3, nil, nil, nil, "MyFolder")

# Print the layout slide name.
print layout_slide.name
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Copy the third layout slide.
layout_slide = slides_api.copy_layout_slide("MyPresentation.pptx", "MyTemplates/SalesTemplate.pptx", 3, None, None, None, "MyFolder")

# Print the layout slide name.
print(layout_slide.name)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Copy the third layout slide.
slidesApi.copyLayoutSlide("MyPresentation.pptx", "MyTemplates/SalesTemplate.pptx", 3, null, null, null, "MyFolder").then((layoutSlide) => {
    // Print the layout slide name.
    console.log(layoutSlide.body.name)
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

    // Copy the third layout slide.
    auto layoutSlide = slidesApi->copyLayoutSlide(L"MyPresentation.pptx", L"MyTemplates/SalesTemplate.pptx", 3, L"", L"", L"", L"MyFolder").get();

    // Print the layout slide name.
    std::wcout << layoutSlide->getName();

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

# Copy the third layout slide.
my %parameters = (name => "MyPresentation.pptx", clone_from => "MyTemplates/SalesTemplate.pptx", clone_from_position => 3, folder => "MyFolder");
my $layout_slide = $slides_api->copy_layout_slide(%parameters);

# Print the layout slide name.
print $layout_slide->{name};
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
