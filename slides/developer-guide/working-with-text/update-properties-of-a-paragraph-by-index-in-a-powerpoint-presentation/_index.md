---
title: "Update Properties of a Paragraph by Index in a PowerPoint Presentation"
type: docs
url: /update-properties-of-a-paragraph-by-index-in-a-powerpoint-presentation/
weight: 50
---

## **Introduction**
This article shows how you can update properties of a paragraph by index in PowerPoint presentations using Aspose.Slides for Cloud API. You can use our REST API with any language: .NET, Java, PHP, Ruby, Rails, Python, jQuery, and much more.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|PUT|Updates properties of a paragraph in a shape.|[UpdateParagraph](https://apireference.aspose.cloud/slides/#/Shapes/UpdateParagraph)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The presentation file name.|
|slideIndex|integer|path|true|The 1-based index of the presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|paragraphIndex|integer|path|true|The 1-based index of the paragraph.|
|dto|object|body|true|The data transfer object of the paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **cURL Example**
Update the second paragraph in the first shape on the first slide. Set text alignment to Justify. Set Margin Left to 30pt. Set Space Before to 20pt. The storage name is "Main". The folder name is "Data".

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```
curl -v -X PUT "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/1/paragraphs/2?folder=Data&storage=Main" -d "{'Alignment':'Justify','MarginLeft':30.0,'SpaceBefore':-20.0}" -H "Content-Type: application/json" -H %token% --ssl-no-revoke
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "marginLeft": 30.0,
    "spaceBefore": -20.0,
    "alignment": "Justify",
    "portionList": [
        {
            "text": "The second paragraph to demonstrate updating the paragraph settings.",
            "fontColor": "#FF000000",
            "highlightColor": "#0",
            "fontHeight": 18.0,
            "languageId": "en-US",
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/1/paragraphs/2/portions/1?folder=Data",
                "relation": "self"
            }
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/1/paragraphs/2?folder=Data",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](https://docs.aspose.cloud/slides/available-sdks/).

## **SDK Examples**
Update the second paragraph in the first shape on the first slide. Set text alignment to Justify. Set Margin Left to 30pt. Set Space Before to 20pt. The storage name is "Main". The folder name is "Data".

{{< tabs tabTotal="11" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Test
{
    static void Main()
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var folderName = "Data";
        var fileName = "example.pptx";
        var slideIndex = 1;
        var shapeIndex = 1;
        var paragraphIndex = 2;
        var password = "";
        
        // Get a paragraph from the presentation.
        var paragraph = slidesApi.GetParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName);

        // Change some paragraph settings.
        paragraph.Alignment = Paragraph.AlignmentEnum.Justify;
        paragraph.MarginLeft = 30;
        paragraph.SpaceBefore = -20; // The negative value means it is in points.

        // Update the paragraph settings.
        slidesApi.UpdateParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, paragraph, password, folderName, storageName);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Paragraph;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var folderName = "Data";
        var fileName = "example.pptx";
        var slideIndex = 1;
        var shapeIndex = 1;
        var paragraphIndex = 2;
        var password = "";

        // Get a paragraph from the presentation.
        var paragraph = slidesApi.getParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName);

        // Change some paragraph settings.
        paragraph.setAlignment(Paragraph.AlignmentEnum.JUSTIFY);
        paragraph.setMarginLeft(30.0);
        paragraph.setSpaceBefore(-20.0); // The negative value means it is in points.

        // Update the paragraph settings.
        slidesApi.updateParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, paragraph, password, folderName, storageName);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$storageName = "Main";
$folderName = "Data";
$fileName = "example.pptx";
$slideIndex = 1;
$shapeIndex = 1;
$paragraphIndex = 2;
$password = "";

// Get a paragraph from the presentation.
$paragraph = $slidesApi->getParagraph($fileName, $slideIndex, $shapeIndex, $paragraphIndex, $password, $folderName, $storageName);

// Change some paragraph settings.
$paragraph->setAlignment(Model\Paragraph::ALIGNMENT_JUSTIFY);
$paragraph->setMarginLeft(30);
$paragraph->setSpaceBefore(-20); // The negative value means it is in points.

// Update the paragraph settings.
$slidesApi->updateParagraph($fileName, $slideIndex, $shapeIndex, $paragraphIndex, $paragraph, $password, $folderName, $storageName);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.paragraph import Paragraph

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

storageName = "Main"
folderName = "Data"
fileName = "example.pptx"
slideIndex = 1
shapeIndex = 1
paragraphIndex = 2
password = ""

# Get a paragraph from the presentation.
paragraph = slides_api.get_paragraph(fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName)

# Change some paragraph settings.
paragraph.alignment = "Justify"
paragraph.margin_left = 30
paragraph.space_before = -20 # The negative value means it is in points.

# Update the paragraph settings.
slides_api.update_paragraph(fileName, slideIndex, shapeIndex, paragraphIndex, paragraph, password, folderName, storageName)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const api = require("asposeslidescloud")

const slidesApi = new api.SlidesApi("my_client_id", "my_client_key")

const storageName = "Main"
const folderName = "Data"
const fileName = "example.pptx"
const slideIndex = 1
const shapeIndex = 1
const paragraphIndex = 2
const password = ""

// Get a paragraph from the presentation.
slidesApi.getParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName).then((paragraph) => {
    // Change some paragraph settings.
    paragraph.alignment = "Justify"
    paragraph.marginLeft = 30
    paragraph.spaceBefore = -20 // The negative value means it is in points.

    // Update the paragraph settings.
    slidesApi.updateParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, paragraph, password, folderName, storageName).then((response) => {
        console.log(JSON.stringify(response))
    })
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Paragraph;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var storageName = "Main";
        var folderName = "Data";
        var fileName = "example.pptx";
        var slideIndex = 1;
        var shapeIndex = 1;
        var paragraphIndex = 2;
        var password = "";

        // Get a paragraph from the presentation.
        var paragraph = slidesApi.getParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName);

        // Change some paragraph settings.
        paragraph.setAlignment(Paragraph.AlignmentEnum.JUSTIFY);
        paragraph.setMarginLeft(30.0);
        paragraph.setSpaceBefore(-20.0); // The negative value means it is in points.

        // Update the paragraph settings.
        slidesApi.updateParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, paragraph, password, folderName, storageName);
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
	auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("my_client_key"));

	auto storageName = to_string_t("Main");
	auto folderName = to_string_t("Data");
	auto fileName = to_string_t("example.pptx");
	auto slideIndex = 1;
	auto shapeIndex = 1;
	auto paragraphIndex = 2;
	auto password = to_string_t("");

    // Get a paragraph from the presentation.
    auto paragraph = slidesApi->getParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName).get();

    // Change some paragraph settings.
    paragraph->setAlignment(to_string_t("Justify"));
    paragraph->setMarginLeft(30);
    paragraph->setSpaceBefore(-20); // The negative value means it is in points.

    // Update the paragraph settings.
    slidesApi->updateParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, paragraph, password, folderName, storageName).get();
	
	return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go

```

{{< /tab >}}

{{< /tabs >}}
