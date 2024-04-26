---
title: "Get Information about Slides"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- slide
type: docs
url: /get-information-about-slides/
weight: 5
---

## **Introduction**

This article describes methods to get basic information about slides from a PowerPoint presentation.

## **GetSlides**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides|GET|Retrieves basic information about slides from a presentation saved in a storage.|[GetSlides](https://reference.aspose.cloud/slides/#/Slides/GetSlides)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

Get references to slides from the **/MyFolder/MyPresentation.pptx** document saved in the **MyStorage** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Information about Slides**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder&storage=MyStorage" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

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

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string storageName = "MyStorage";
        string documentFolder = "MyFolder";
        string documentName = "MyPresentation.pptx";

        Slides slidesInfo = slidesApi.GetSlides(documentName, null, documentFolder, storageName);

        Console.WriteLine("Reference to slides: " + slidesInfo.SelfUri.Href);
        foreach (ResourceUri slideInfo in slidesInfo.SlideList)
        {
            Console.WriteLine("    Slide reference: " + slideInfo.Href);
        }
    }
}

// The output example:
//
// Reference to slides: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Slides;
import com.aspose.slides.model.ResourceUri;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String storageName = "MyStorage";
        String documentFolder = "MyFolder";
        String documentName = "MyPresentation.pptx";

        Slides slidesInfo = slidesApi.getSlides(documentName, null, documentFolder, storageName);

        System.out.println("Reference to slides: " + slidesInfo.getSelfUri().getHref());
        for (ResourceUri slideInfo : slidesInfo.getSlideList()) {
            System.out.println("    Slide reference: " + slideInfo.getHref());
        }
    }
}

// The output example:
//
// Reference to slides: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "MyStorage";
$documentFolder = "MyFolder";
$documentName = "MyPresentation.pptx";

$slidesInfo = $slidesApi->getSlides($documentName, null, $documentFolder, $storageName);

echo "Reference to slides: ", $slidesInfo->getSelfUri()->getHref(), "\n";
foreach ($slidesInfo->getSlideList() as $slideInfo)
{
    echo "    Slide reference: ", $slideInfo->getHref(), "\n";
}

// The output example:
//
// Reference to slides: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

storage_name = "MyStorage"
document_folder = "MyFolder"
document_name = "MyPresentation.pptx"

slides_info = slides_api.get_slides(document_name, nil, document_folder, storage_name)

puts "Reference to slides: #{slides_info.self_uri.href}"
slides_info.slide_list.each do |slide_info|
    puts "    Slide reference: #{slide_info.href}"
end

# The output example:
#
# Reference to slides: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

storage_name = "MyStorage"
document_folder = "MyFolder"
document_name = "MyPresentation.pptx"

slides_info = slides_api.get_slides(document_name, None, document_folder, storage_name)

print("Reference to slides:", slides_info.self_uri.href)
for slide_info in slides_info.slide_list:
    print("    Slide reference:", slide_info.href)

# The output example:
#
# Reference to slides: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

storageName = "MyStorage";
documentFolder = "MyFolder";
documentName = "MyPresentation.pptx";

slidesApi.getSlides(documentName, null, documentFolder, storageName).then(slidesInfo => {
    console.log("Reference to slides:", slidesInfo.body.selfUri.href);
    slidesInfo.body.slideList.forEach(slideInfo => {
        console.log("    Slide reference:", slideInfo.href);
    });
});

// The output example:
//
// Reference to slides: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* storageName = L"MyStorage";
    const wchar_t* documentFolder = L"MyFolder";
    const wchar_t* documentName = L"MyPresentation.pptx";

    std::shared_ptr<Slides> slidesInfo = slidesApi->getSlides(documentName, L"", documentFolder, storageName).get();

    std::wcout << "Reference to slides: " << slidesInfo->getSelfUri()->getHref() << "\n";
    for (std::shared_ptr<ResourceUri> slideInfo : slidesInfo->getSlideList())
    {
        std::wcout << "    Slide reference: " << slideInfo->getHref() << "\n";
    }
}

// The output example:
//
// Reference to slides: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder
//     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $storage_name = "MyStorage";
my $document_folder = "MyFolder";
my $document_name = "MyPresentation.pptx";

my $slides_info = $slides_api->get_slides(name => $document_name, folder => $document_folder, storage => $storage_name);

print("Reference to slides: ", $slides_info->{self_uri}->{href}, "\n");
for my $slide_info (@{$slides_info->{slide_list}}) {
    print("    Slide reference: ", $slide_info->{href}, "\n");
}

# The output example:
#
# Reference to slides: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder
#     Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3?folder=MyFolder
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **GetSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}|GET|Retrieves basic information about a slide from a presentation saved in a storage.|[GetSlide](https://reference.aspose.cloud/slides/#/Slides/GetSlide)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

Get the reference to the **second** slide from the **MyPresentation.pptx** document saved in the **default** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Information about the Slide**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "width": 960,
  "height": 540,
  "showMasterShapes": true,
  "layoutSlide": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1",
    "relation": "self"
  },
  "shapes": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes",
    "relation": "self",
    "slideIndex": 2
  },
  "theme": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/theme",
    "relation": "self",
    "slideIndex": 2
  },
  "placeholders": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/placeholders",
    "relation": "self",
    "slideIndex": 2
  },
  "images": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/images",
    "relation": "self",
    "slideIndex": 2
  },
  "comments": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/comments",
    "relation": "self",
    "slideIndex": 2
  },
  "background": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/background",
    "relation": "self",
    "slideIndex": 2
  },
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2",
    "relation": "self",
    "slideIndex": 2
  },
  "alternateLinks": [
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/jpeg",
      "relation": "alternate",
      "linkType": "image/jpeg",
      "title": "Download as Jpeg",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/gif",
      "relation": "alternate",
      "linkType": "image/gif",
      "title": "Download as Gif",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/bmp",
      "relation": "alternate",
      "linkType": "image/bmp",
      "title": "Download as Bmp",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/png",
      "relation": "alternate",
      "linkType": "image/png",
      "title": "Download as Png",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/tiff",
      "relation": "alternate",
      "linkType": "image/tiff",
      "title": "Download as Tiff",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/svg",
      "relation": "alternate",
      "linkType": "image/svg+xml",
      "title": "Download as Svg",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/odp",
      "relation": "alternate",
      "linkType": "application/vnd.oasis.opendocument.presentation",
      "title": "Download as Odp",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/fodp",
      "relation": "alternate",
      "linkType": "application/vnd.oasis.opendocument.presentation",
      "title": "Download as Fodp",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/otp",
      "relation": "alternate",
      "linkType": "application/vnd.oasis.opendocument.presentation-template",
      "title": "Download as Otp",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/ppt",
      "relation": "alternate",
      "linkType": "application/vnd.ms-powerpoint",
      "title": "Download as Ppt",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pptx",
      "relation": "alternate",
      "linkType": "application/vnd.openxmlformats-officedocument.presentationml.presentation",
      "title": "Download as Pptx",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pdf",
      "relation": "alternate",
      "linkType": "application/pdf",
      "title": "Download as Pdf",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/xps",
      "relation": "alternate",
      "linkType": "application/vnd.ms-xpsdocument",
      "title": "Download as Xps",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pps",
      "relation": "alternate",
      "linkType": "application/vnd.ms-powerpoint",
      "title": "Download as Pps",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/ppsx",
      "relation": "alternate",
      "linkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
      "title": "Download as Ppsx",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pptm",
      "relation": "alternate",
      "linkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
      "title": "Download as Pptm",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/ppsm",
      "relation": "alternate",
      "linkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
      "title": "Download as Ppsm",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pot",
      "relation": "alternate",
      "linkType": "application/vnd.ms-powerpoint",
      "title": "Download as Pot",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/potx",
      "relation": "alternate",
      "linkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
      "title": "Download as Potx",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/potm",
      "relation": "alternate",
      "linkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
      "title": "Download as Potm",
      "slideIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/html",
      "relation": "alternate",
      "linkType": "text/html",
      "title": "Download as Html",
      "slideIndex": 2
    }
  ]
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string documentName = "MyPresentation.pptx";
        int slideIndex = 2;

        Slide slideInfo = slidesApi.GetSlide(documentName, slideIndex);

        Console.WriteLine("Slide reference: " + slideInfo.SelfUri.Href);
    }
}

// The output example:
//
// Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Slide;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String documentName = "MyPresentation.pptx";
        int slideIndex = 2;

        Slide slideInfo = slidesApi.getSlide(documentName, slideIndex, null, null, null);

        System.out.println("Slide reference: " + slideInfo.getSelfUri().getHref());
    }
}

// The output example:
//
// Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$documentName = "MyPresentation.pptx";
$slideIndex = 2;

$slideInfo = $slidesApi->getSlide($documentName, $slideIndex);

echo "Slide reference: ", $slideInfo->getSelfUri()->getHref();

// The output example:
//
// Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

document_name = "MyPresentation.pptx"
slide_index = 2

slide_info = slides_api.get_slide(document_name, slide_index)

puts "Slide reference: #{slide_info.self_uri.href}"

# The output example:
#
# Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

document_name = "MyPresentation.pptx"
slide_index = 2

slide_info = slides_api.get_slide(document_name, slide_index)

print("Slide reference:", slide_info.self_uri.href)

# The output example:
#
# Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

documentName = "MyPresentation.pptx";
slideIndex = 2;

slidesApi.getSlide(documentName, slideIndex).then(slideInfo => {
    console.log("Slide reference:", slideInfo.body.selfUri.href);
});

// The output example:
//
// Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* documentName = L"MyPresentation.pptx";
    int slideIndex = 2;

    std::shared_ptr<Slide> slideInfo = slidesApi->getSlide(documentName, slideIndex).get();

    std::wcout << "Slide reference: " << slideInfo->getSelfUri()->getHref();
}

// The output example:
//
// Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $document_name = "MyPresentation.pptx";
my $slideIndex = 2;

my $slide_info = $slides_api->get_slide(name => $document_name, slide_index => $slide_index);

print("Slide reference: ", $slide_info->{self_uri}->{href});

# The output example:
#
# Slide reference: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
