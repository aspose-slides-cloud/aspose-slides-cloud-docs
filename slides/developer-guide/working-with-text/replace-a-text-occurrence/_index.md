---
title: "Replace a Text Occurrence"
type: docs
url: /replace-a-text-occurrence/
weight: 80
---

## **Introduction**

Using Aspose.Slides Cloud, you can easily replace all occurrences of text. Aspose.Slides Cloud provides you with the following methods for replacing text on a single slide or in an entire presentation.

## **ReplacePresentationText**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/replaceText|POST|Replaces text in a presentation.|[ReplacePresentationText](https://apireference.aspose.cloud/slides/#/Text/ReplacePresentationText)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|oldValue|string|query|true|The text string to be replaced.|
|newValue|string|query|true|The text string to replace with.|
|ignoreCase|boolean|query|false|Indicates whether to ignore character case. False by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Replace every word **banana** with the word **orange** in the document **MyFolder/MyPresentation.pptx**. Ignore character case.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Replace the Text**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/replaceText?oldValue=banana&newValue=orange&ignoreCase=true&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "matches": 4,
    "documentProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties?folder=MyFolder",
        "relation": "self"
    },
    "viewProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/viewProperties?folder=MyFolder",
        "relation": "self"
    },
    "slides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder",
        "relation": "self"
    },
    "images": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images?folder=MyFolder",
        "relation": "self"
    },
    "layoutSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides?folder=MyFolder",
        "relation": "self"
    },
    "masterSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides?folder=MyFolder",
        "relation": "self"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder",
        "relation": "self"
    },
    "alternateLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/odp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Odp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fodp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Fodp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppt?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Ppt"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pdf?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/pdf",
            "title": "Download as Pdf"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/tiff?folder=MyFolder",
            "relation": "alternate",
            "linkType": "image/tiff",
            "title": "Download as Tiff"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/xps?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-xpsdocument",
            "title": "Download as Xps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pps?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppsx?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "title": "Download as Ppsx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pptm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "title": "Download as Pptm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppsm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "title": "Download as Ppsm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pot?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pot"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/potx?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
            "title": "Download as Potx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/potm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
            "title": "Download as Potm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/otp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation-template",
            "title": "Download as Otp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/html?folder=MyFolder",
            "relation": "alternate",
            "linkType": "text/html",
            "title": "Download as Html"
        }
    ]
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

        // Replace the specified text, ignoring case.
        var result = slidesApi.ReplacePresentationText("MyPresentation.pptx", "banana", "orange", true, null, "MyFolder");
        
        Console.WriteLine($"Replaced {result.Matches} matches.");
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

        // Replace the specified text, ignoring case.
        DocumentReplaceResult result = slidesApi.replacePresentationText("MyPresentation.pptx", "banana", "orange", true, null, "MyFolder", null);

        System.out.println("Replaced " + result.getMatches() + " matches.");
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

// Replace the specified text, ignoring case.
$result = $slidesApi->replacePresentationText("MyPresentation.pptx", "banana", "orange", true, null, "MyFolder");

echo "Replaced ", $result->getMatches(), " matches.";
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

# Replace the specified text, ignoring case.
result = slides_api.replace_presentation_text("MyPresentation.pptx", "banana", "orange", true, nil, "MyFolder")

print "Replaced ", result.matches, " matches."
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Replace the specified text, ignoring case.
result = slides_api.replace_presentation_text("MyPresentation.pptx", "banana", "orange", True, None, "MyFolder")

print("Replaced", result.matches, "matches.")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Replace the specified text, ignoring case.
slidesApi.replacePresentationText("MyPresentation.pptx", "banana", "orange", true, null, "MyFolder").then((result) => {
    console.log("Replaced", result.body.matches, "matches.")
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

    // Replace the specified text, ignoring case.
    auto result = slidesApi->replacePresentationText(L"MyPresentation.pptx", L"banana", L"orange", true, L"", L"MyFolder").get();

    std::wcout << "Replaced " << result->getMatches() << " matches.";

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

# Replace the specified text, ignoring case.
my %parameters = (name => "MyPresentation.pptx", old_value => "banana", new_value => "orange", ignore_case => true, folder => "MyFolder");
my $result = $slides_api->replace_presentation_text(%parameters);

print "Replaced ", $result->{matches}, " matches.";
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-go

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

// Replace the specified text, ignoring case.
var ignoreCase bool = true
result, _, e := api.SlidesApi.ReplacePresentationText("MyPresentation.pptx", "banana", "orange", &ignoreCase, "", "MyFolder", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Replaced %v matches.", result.GetMatches())
```

{{< /tab >}}

{{< /tabs >}}

## **ReplaceSlideText**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/replaceText|POST|Replaces text on a presentation slide.|[ReplaceSlideText](https://apireference.aspose.cloud/slides/#/Text/ReplaceSlideText)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|oldValue|string|query|true|The text string to be replaced.|
|newValue|string|query|true|The text string to replace with.|
|ignoreCase|boolean|query|false|Indicates whether to ignore character case. False by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Replace every word **banana** with the word **orange** on the **second** slide in the document **MyFolder/MyPresentation.pptx**. Characters must be case sensitive.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Replace the Text**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/replaceText?oldValue=banana&newValue=orange&ignoreCase=false&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "matches": 1,
    "width": 960.0,
    "height": 540.0,
    "showMasterShapes": true,
    "layoutSlide": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1?folder=MyFolder",
        "relation": "self"
    },
    "shapes": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    },
    "theme": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/theme?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    },
    "placeholders": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/placeholders?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    },
    "images": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/images?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    },
    "comments": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/comments?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    },
    "background": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/background?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    },
    "notesSlide": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/notesSlide?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2?folder=MyFolder",
        "relation": "self"
    },
    "alternateLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/jpeg?folder=MyFolder",
            "relation": "alternate",
            "linkType": "image/jpeg",
            "title": "Download as Jpeg",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/gif?folder=MyFolder",
            "relation": "alternate",
            "linkType": "image/gif",
            "title": "Download as Gif",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/bmp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "image/bmp",
            "title": "Download as Bmp",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/png?folder=MyFolder",
            "relation": "alternate",
            "linkType": "image/png",
            "title": "Download as Png",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/tiff?folder=MyFolder",
            "relation": "alternate",
            "linkType": "image/tiff",
            "title": "Download as Tiff",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/svg?folder=MyFolder",
            "relation": "alternate",
            "linkType": "image/svg+xml",
            "title": "Download as Svg",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/odp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Odp",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/fodp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Fodp",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/otp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation-template",
            "title": "Download as Otp",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/ppt?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Ppt",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pptx?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.presentation",
            "title": "Download as Pptx",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pdf?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/pdf",
            "title": "Download as Pdf",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/xps?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-xpsdocument",
            "title": "Download as Xps",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pps?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pps",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/ppsx?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "title": "Download as Ppsx",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pptm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "title": "Download as Pptm",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/ppsm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "title": "Download as Ppsm",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/pot?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pot",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/potx?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
            "title": "Download as Potx",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/potm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
            "title": "Download as Potm",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/html?folder=MyFolder",
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

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

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

        // Replace the specified text on the second slide.
        var result = slidesApi.ReplaceSlideText("MyPresentation.pptx", 2, "banana", "orange", null, null, "MyFolder");
        
        Console.WriteLine($"Replaced {result.Matches} matches.");
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

        // Replace the specified text on the second slide.
        SlideReplaceResult result = slidesApi.replaceSlideText("MyPresentation.pptx", 2, "banana", "orange", null, null, "MyFolder", null);

        System.out.println("Replaced " + result.getMatches() + " matches.");
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

// Replace the specified text on the second slide.
$result = $slidesApi->replaceSlideText("MyPresentation.pptx", 2, "banana", "orange", null, null, "MyFolder");

echo "Replaced ", $result->getMatches(), " matches.";
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

# Replace the specified text on the second slide.
result = slides_api.replace_slide_text("MyPresentation.pptx", 2, "banana", "orange", nil, nil, "MyFolder")

print "Replaced ", result.matches, " matches."
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Replace the specified text on the second slide.
result = slides_api.replace_slide_text("MyPresentation.pptx", 2, "banana", "orange", None, None, "MyFolder")

print("Replaced", result.matches, "matches.")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Replace the specified text on the second slide.
slidesApi.replaceSlideText("MyPresentation.pptx", 2, "banana", "orange", null, null, "MyFolder").then((result) => {
    console.log("Replaced", result.body.matches, "matches.")
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

    // Replace the specified text on the second slide.
    auto result = slidesApi->replaceSlideText(L"MyPresentation.pptx", 2, L"banana", L"orange", NULL, L"", L"MyFolder").get();

    std::wcout << "Replaced " << result->getMatches() << " matches.";

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

# Replace the specified text on the second slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, old_value => "banana", new_value => "orange", folder => "MyFolder");
my $result = $slides_api->replace_slide_text(%parameters);

print "Replaced ", $result->{matches}, " matches.";
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
