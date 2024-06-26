---
title: "Edit Paragraphs within Grouped Shapes"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- text
- paragraph
- group shape
- edit a paragraph
type: docs
url: /edit-paragraphs-within-grouped-shapes/
weight: 50
---

## **Introduction**

This article shows you how to format and edit paragraphs within a grouped shape using Aspose.Slides Cloud API in your applications. **UpdateParagraph** method has an optional **subShape** parameter that allows to specify path to the sub-shape that contains the target pararaph. The sub-shape path is a string that contains shape index (e.g., "1") or a path in case of more than one level of grouping (e.g. "1/shapes/1").

### **Examples**

**MyFolder/MyPresentation.pptx** document contains a group shape of **two** shapes at index **3** on the **first** slide. Set italic style for the **fifth** paragraph in the **second** shape inside the group shape.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Update the Paragraph**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/4/paragraphs/1?subshape=2&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @ParagraphProperties.json
```

ParagraphProperties.json content:

```json
{
    "DefaultPortionFormat": {
        "FontItalic": "True"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "alignment": "Center",
    "portionList": [
        {
            "text": "The fifth paragraph",
            "highlightColor": "#0",
            "fontHeight": "NaN",
            "languageId": "en-US",
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/4/shapes/2/paragraphs/1/portions/1?folder=MyFolder",
                "relation": "self",
                "slideIndex": 1,
                "shapeIndex": 2
            }
        }
    ],
    "defaultPortionFormat": {
        "fontItalic": "True",
        "highlightColor": "#0",
        "fontHeight": "NaN"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/4/shapes/2/paragraphs/1?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1,
        "shapeIndex": 2
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
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the paragraph options.
        var paragraph = new Paragraph
        {
            DefaultPortionFormat = new PortionFormat
            { 
                FontItalic = PortionFormat.FontItalicEnum.True
            }
        };

        // Update the 1st paragraph in the 2nd shape within the 4th group shape on the 1st slide.
        var updatedParagraph = slidesApi.UpdateParagraph("MyPresentation.pptx", 1, 4, 1, paragraph, null, "MyFolder", null, "2");

        // Check if italic style has been applied to the paragraph.
        Console.WriteLine("Italic style: " + updatedParagraph.DefaultPortionFormat.FontItalic);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the paragraph options.
        Paragraph paragraph = new Paragraph();
        paragraph.setDefaultPortionFormat(new PortionFormat());
        paragraph.getDefaultPortionFormat().setFontItalic(PortionFormat.FontItalicEnum.TRUE);

        // Update the 1st paragraph in the 2nd shape within the 4th group shape on the 1st slide.
        Paragraph updatedParagraph = slidesApi.updateParagraph("MyPresentation.pptx", 1, 4, 1, paragraph, null, "MyFolder", null, "2");

        // Check if italic style has been applied to the paragraph.
        System.out.println("Italic style: " + updatedParagraph.getDefaultPortionFormat().getFontItalic());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Paragraph;
use Aspose\Slides\Cloud\Sdk\Model\PortionFormat;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare the paragraph options.
$paragraph = new Paragraph();
$paragraph->setDefaultPortionFormat(new PortionFormat());
$paragraph->getDefaultPortionFormat()->setFontItalic("True");

// Update the 1st paragraph in the 2nd shape within the 4th group shape on the 1st slide.
$updatedParagraph = $slidesApi->updateParagraph("MyPresentation.pptx", 1, 4, 1, $paragraph, null, "MyFolder", null, "2");

// Check if italic style has been applied to the paragraph.
echo "Italic style: ", $updatedParagraph->getDefaultPortionFormat()->getFontItalic();
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

# Prepare the paragraph options.
paragraph = Paragraph.new
paragraph.default_portion_format = PortionFormat.new
paragraph.default_portion_format.font_italic = "True"

# Update the 1st paragraph in the 2nd shape within the 4th group shape on the 1st slide.
updated_paragraph = slides_api.update_paragraph("MyPresentation.pptx", 1, 4, 1, paragraph, nil, "MyFolder", nil, "2")

# Check if italic style has been applied to the paragraph.
print "Italic style: " + updated_paragraph.default_portion_format.font_italic
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.paragraph import Paragraph
from asposeslidescloud.models.portion_format import PortionFormat

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare the paragraph options.
paragraph = Paragraph()
paragraph.default_portion_format = PortionFormat()
paragraph.default_portion_format.font_italic = "True"

# Update the 1st paragraph in the 2nd shape within the 4th group shape on the 1st slide.
updated_paragraph = slides_api.update_paragraph("MyPresentation.pptx", 1, 4, 1, paragraph, None, "MyFolder", None, "2")

# Check if italic style has been applied to the paragraph.
print("Italic style: " + updated_paragraph.default_portion_format.font_italic)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Prepare the paragraph options.
var paragraph = new cloud.Paragraph();
paragraph.defaultPortionFormat = new cloud.PortionFormat();
paragraph.defaultPortionFormat.fontItalic = "True";

// Update the 1st paragraph in the 2nd shape within the 4th group shape on the 1st slide.
slidesApi.updateParagraph("MyPresentation.pptx", 1, 4, 1, paragraph, null, "MyFolder", null, "2").then(updatedParagraph => {
    // Check if italic style has been applied to the paragraph.
    console.log("Italic style: " + updatedParagraph.body.defaultPortionFormat.fontItalic);
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
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Prepare the paragraph options.
    auto paragraph = std::make_shared<Paragraph>();
    paragraph->setDefaultPortionFormat(std::make_shared<PortionFormat>());
    paragraph->getDefaultPortionFormat()->setFontItalic(L"True");

    // Update the 1st paragraph in the 2nd shape within the 4th group shape on the 1st slide.
    auto updatedParagraph = slidesApi->updateParagraph(L"MyPresentation.pptx", 1, 2, 1, paragraph, L"", L"MyFolder", L"", L"2").get();

    // Check if italic style has been applied to the paragraph.
    std::wcout << "Italic style: " << updatedParagraph->getDefaultPortionFormat()->getFontItalic();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Paragraph;
use AsposeSlidesCloud::Object::PortionFormat;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare the paragraph options.
my $paragraph =  AsposeSlidesCloud::Object::Paragraph->new();
$paragraph->{default_portion_format} =  AsposeSlidesCloud::Object::PortionFormat->new();
$paragraph->{default_portion_format}->{font_italic} = "True";

# Update the 1st paragraph in the 2nd shape within the 4th group shape on the 1st slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, 
                  shape_index => 4, paragraph_index => 1, dto => $paragraph, folder => "MyFolder", sub_shape=>"2");
my $updated_paragraph = $slides_api->update_paragraph(%parameters);

# Check if italic style has been applied to the paragraph.
print("Italic style: " . $updated_paragraph->{default_portion_format}->{font_italic});
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
