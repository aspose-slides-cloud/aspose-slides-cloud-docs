---
title: "Get a Slide Format Scheme"
type: docs
url: /get-a-slide-format-scheme/
weight: 20
---

## **Introduction**

With Aspose.Slides Cloud, you can easily read information about a format scheme specified for slide elements in a PowerPoint presentation. The API method below allows you to get the following data specifying a slide's major appearance defined in a design theme:
- background styles
- effect styles (shadow, reflection, glow, etc.)
- fill styles
- line styles

## **GetFormatScheme**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/theme/formatScheme|GET|Retrieves a format scheme from a presentation slide.|[GetFormatScheme](https://apireference.aspose.cloud/slides/#/Theme/GetFormatScheme)|

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

Read information about the format scheme of the **second** slide from the document **MyFolder/MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read the Format Scheme**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/theme/formatScheme?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "backgroundStyles": [
        {
            "type": "Solid",
            "color": "#FF000000"
        },
        {
            "type": "Gradient",
            "direction": "FromCorner1",
            "shape": "Linear",
            "stops": [
                {
                    "color": "#FF626262",
                    "position": 0.0
                },
                {
                    "color": "#FF000000",
                    "position": 1.0
                }
            ],
            "linearAngle": 90.0,
            "isScaled": false,
            "tileFlip": "NoFlip"
        },
        {
            "type": "Picture",
            "cropBottom": 0.0,
            "cropLeft": 0.0,
            "cropRight": 0.0,
            "cropTop": 0.0,
            "dpi": -1,
            "image": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/6?folder=MyFolder",
                "relation": "self"
            },
            "pictureFillMode": "Stretch"
        }
    ],
    "effectStyles": [
        {},
        {
            "innerShadow": {
                "direction": 225.0,
                "distance": 1.0,
                "blurRadius": 2.0,
                "shadowColor": "#73000000"
            }
        },
        {
            "outerShadow": {
                "direction": 90.0,
                "distance": 2.0,
                "blurRadius": 3.0,
                "shadowColor": "#99000000"
            }
        }
    ],
    "fillStyles": [
        {
            "type": "Solid",
            "color": "#FF000000"
        },
        {
            "type": "Gradient",
            "direction": "FromCorner1",
            "shape": "Linear",
            "stops": [
                {
                    "color": "#FFBBBBBB",
                    "position": 0.0
                },
                {
                    "color": "#FF767676",
                    "position": 1.0
                }
            ],
            "linearAngle": 90.0,
            "isScaled": false,
            "tileFlip": "NoFlip"
        },
        {
            "type": "Picture",
            "cropBottom": 0.0,
            "cropLeft": 0.0,
            "cropRight": 0.0,
            "cropTop": 0.0,
            "dpi": -1,
            "image": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/5?folder=MyFolder",
                "relation": "self"
            },
            "pictureFillMode": "Tile",
            "imageTransformList": [
                {
                    "type": "Duotone",
                    "color1": "#FF000000",
                    "color2": "#FF484848"
                }
            ]
        }
    ],
    "lineStyles": [
        {
            "alignment": "Center",
            "capStyle": "Flat",
            "dashStyle": "Solid",
            "joinStyle": "Round",
            "style": "Single",
            "beginArrowHead": {
                "length": "Medium",
                "style": "None",
                "width": "Medium"
            },
            "endArrowHead": {
                "length": "Medium",
                "style": "None",
                "width": "Medium"
            },
            "fillFormat": {
                "type": "Solid",
                "color": "#FF000000"
            },
            "miterLimit": 10.0,
            "width": 0.75
        },
        {
            "alignment": "Center",
            "capStyle": "Flat",
            "dashStyle": "Solid",
            "joinStyle": "Round",
            "style": "Single",
            "beginArrowHead": {
                "length": "Medium",
                "style": "None",
                "width": "Medium"
            },
            "endArrowHead": {
                "length": "Medium",
                "style": "None",
                "width": "Medium"
            },
            "fillFormat": {
                "type": "Solid",
                "color": "#FF000000"
            },
            "miterLimit": 10.0,
            "width": 1.25
        },
        {
            "alignment": "Center",
            "capStyle": "Flat",
            "dashStyle": "Solid",
            "joinStyle": "Round",
            "style": "Single",
            "beginArrowHead": {
                "length": "Medium",
                "style": "None",
                "width": "Medium"
            },
            "endArrowHead": {
                "length": "Medium",
                "style": "None",
                "width": "Medium"
            },
            "fillFormat": {
                "type": "Solid",
                "color": "#FF000000"
            },
            "miterLimit": 10.0,
            "width": 2.0
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/theme/formatScheme?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
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

        // Read the format scheme for the second slide.
        var formatScheme = slidesApi.GetFormatScheme("MyPresentation.pptx", 2, null, "MyFolder");

        // Print the number of background styles from the format scheme.
        var backgroundStyles = formatScheme.BackgroundStyles.Count;
        Console.WriteLine("The number of background styles: " + backgroundStyles);
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

        // Read the format scheme for the second slide.
        FormatScheme formatScheme = slidesApi.getFormatScheme("MyPresentation.pptx", 2, null, "MyFolder", null);

        // Print the number of background styles from the format scheme.
        int backgroundStyles = formatScheme.getBackgroundStyles().size();
        System.out.println("The number of background styles: " + backgroundStyles);
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

// Read the format scheme for the second slide.
$formatScheme = $slidesApi->getFormatScheme("MyPresentation.pptx", 2, null, "MyFolder");

// Print the number of background styles from the format scheme.
$backgroundStyles = count($formatScheme->getBackgroundStyles());
echo "The number of background styles: " . $backgroundStyles;
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

# Read the format scheme for the second slide.
format_scheme = slides_api.get_format_scheme("MyPresentation.pptx", 2, nil, "MyFolder")

# Print the number of background styles from the format scheme.
background_styles = format_scheme.background_styles.length()
print "The number of background styles: ", background_styles
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Read the format scheme for the second slide.
format_scheme = slides_api.get_format_scheme("MyPresentation.pptx", 2, None, "MyFolder")

# Print the number of background styles from the format scheme.
background_styles = len(format_scheme.background_styles)
print("The number of background styles:", background_styles)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Read the format scheme for the second slide.
slidesApi.getFormatScheme("MyPresentation.pptx", 2, null, "MyFolder").then((formatScheme) => {
    // Print the number of background styles from the format scheme.
    const backgroundStyles = formatScheme.body.backgroundStyles.length
    console.log("The number of background styles:", backgroundStyles)
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

    // Read the format scheme for the second slide.
    auto formatScheme = slidesApi->getFormatScheme(L"MyPresentation.pptx", 2, L"", L"MyFolder").get();

    // Print the number of background styles from the format scheme.
    auto backgroundStyles = formatScheme->getBackgroundStyles().size();
    std::wcout << "The number of background styles: " <<  backgroundStyles;

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

# Read the format scheme for the second slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, folder => "MyFolder");
my $format_scheme = $slides_api->get_format_scheme(%parameters);

# Print the number of background styles from the format scheme.
my $background_styles = @{$format_scheme->{background_styles}};
print "The number of background styles: " . $background_styles;
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
