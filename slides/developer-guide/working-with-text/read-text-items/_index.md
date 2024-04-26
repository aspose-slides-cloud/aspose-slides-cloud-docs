---
title: "Read Text Items"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- text
- get text
- extract text
type: docs
url: /read-text-items/
weight: 70
---

## **Introduction**

Aspose.Slides Cloud lets you easily read all text items from a PowerPoint presentation. This article shows REST methods for reading text items both from a single slide and from an entire presentation at once. You can specify whether empty items should also be considered. The methods below take into account any presentation object containing a text frame.

## **GetPresentationTextItems**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/textItems|GET|Reads text items from a PowerPoint presentation.|[GetPresentationTextItems](https://apireference.aspose.cloud/slides/#/Text/GetPresentationTextItems)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|withEmpty|boolean|query|false|Indicates whether empty text items should be considered. The default value is `false`.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Get all text items, including empty ones, from **MyFolder/MyPresentation.pptx** document saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Text Items**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/textItems?withEmpty=true&folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "items": [
        {
            "uri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1?folder=MyFolder",
                "relation": "parent",
                "slideIndex": 1
            },
            "text": "This is a text box on slide 1."
        },
        {
            "uri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1?folder=MyFolder",
                "relation": "parent",
                "slideIndex": 2
            },
            "text": "This is a circle on slide 2."
        },
        {
            "uri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/2?folder=MyFolder",
                "relation": "parent",
                "slideIndex": 2
            },
            "text": ""
        },
        {
            "uri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/3?folder=MyFolder",
                "relation": "parent",
                "slideIndex": 2
            },
            "text": "This is a WordArt on slide 2."
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/textItems?folder=MyFolder",
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
using System.Diagnostics;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all text items from the presentation.
        var textItems = slidesApi.GetPresentationTextItems("MyPresentation.pptx", true, null, "MyFolder");

        // Print the texts.
        foreach (var textItem in textItems.Items)
        {
            Debug.WriteLine(textItem.Text);
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

        // Get all text items from the presentation.
        TextItems textItems = slidesApi.getPresentationTextItems("MyPresentation.pptx", true, null, "MyFolder", null);

        // Print the texts.
        for (TextItem textItem : textItems.getItems()) {
            System.out.println(textItem.getText());
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

// Get all text items from the presentation.
$textItems = $slidesApi->getPresentationTextItems("MyPresentation.pptx", TRUE, null, "MyFolder");

// Print the texts.
foreach ($textItems->getItems() as $textItem) {
    echo $textItem->getText(), "\n";
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

# Get all text items from the presentation.
text_items = slides_api.get_presentation_text_items("MyPresentation.pptx", true, nil, "MyFolder")

# Print the texts.
for text_item in text_items.items
    puts text_item.text
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get all text items from the presentation.
text_items = slides_api.get_presentation_text_items("MyPresentation.pptx", True, None, "MyFolder")

# Print the texts.
for text_item in text_items.items:
    print(text_item.text)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Get all text items from the presentation.
slidesApi.getPresentationTextItems("MyPresentation.pptx", true, null, "MyFolder").then(textItems => {
    // Print the texts.
    textItems.body.items.forEach(textItem => {
        console.log(textItem.text);
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
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Get all text items from the presentation.
    auto textItems = slidesApi->getPresentationTextItems(L"MyPresentation.pptx", true, L"", L"MyFolder").get();

    // Print the texts.
    for (auto textItem : textItems->getItems()) {
        std::wcout << textItem->getText() << std::endl;
    }

    std::cin.get();

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

# Get all text items from the presentation.
my %parameters = (name => "MyPresentation.pptx", with_empty => true, folder => "MyFolder");
my $text_items = $slides_api->get_presentation_text_items(%parameters);

# Print the texts.
for my $text_item (@{$text_items->{items}}) {
    print $text_item->{text}, "\n";
}
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

var withEmpty bool = true
// Get all text items from the presentation.
textItems, _, e := api.SlidesApi.GetPresentationTextItems("MyPresentation.pptx", &withEmpty, "", "MyFolder", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

// Print the number of the text items.
fmt.Printf("Found %v items.", len(textItems.GetItems()))
```

{{< /tab >}}

{{< /tabs >}}

## **GetSlideTextItems**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/textItems|GET|Reads text items from a presentation slide.|[GetSlideTextItems](https://apireference.aspose.cloud/slides/#/Text/GetSlideTextItems)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide to read text items.|
|withEmpty|boolean|query|false|Indicates whether empty text items should be considered. The default value is `false`.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Get all text items from the **second** slide of **MyFolder/MyPresentation.pptx** document saved to the default storage. Ignore empty items.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Text Items**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/textItems?folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "items": [
        {
            "uri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1?folder=MyFolder",
                "relation": "parent",
                "slideIndex": 2
            },
            "text": "This is a circle on slide 2."
        },
        {
            "uri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/3?folder=MyFolder",
                "relation": "parent",
                "slideIndex": 2
            },
            "text": "This is a WordArt on slide 2."
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/textItems?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    }
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
using System.Diagnostics;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all text items from the second slide, except empty ones.
        var textItems = slidesApi.GetSlideTextItems("MyPresentation.pptx", 2, null, null, "MyFolder");

        // Print the texts.
        foreach (var textItem in textItems.Items)
        {
            Debug.WriteLine(textItem.Text);
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

        // Get all text items from the second slide, except empty ones.
        TextItems textItems = slidesApi.getSlideTextItems("MyPresentation.pptx", 2, null, null, "MyFolder", null);

        // Print the texts.
        for (TextItem textItem : textItems.getItems()) {
            System.out.println(textItem.getText());
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

// Get all text items from the second slide, except empty ones.
$textItems = $slidesApi->getSlideTextItems("MyPresentation.pptx", 2, null, null, "MyFolder");

// Print the texts.
foreach ($textItems->getItems() as $textItem) {
    echo $textItem->getText(), "\n";
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

# Get all text items from the second slide, except empty ones.
text_items = slides_api.get_slide_text_items("MyPresentation.pptx", 2, nil, nil, "MyFolder")

# Print the texts.
for text_item in text_items.items
    puts text_item.text
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get all text items from the second slide, except empty ones.
text_items = slides_api.get_slide_text_items("MyPresentation.pptx", 2, None, None, "MyFolder")

# Print the texts.
for text_item in text_items.items:
    print(text_item.text)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Get all text items from the second slide, except empty ones.
slidesApi.getSlideTextItems("MyPresentation.pptx", 2, null, null, "MyFolder").then(textItems => {
    // Print the texts.
    textItems.body.items.forEach(textItem => {
        console.log(textItem.text);
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
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Get all text items from the second slide, except empty ones.
    auto textItems = slidesApi->getSlideTextItems(L"MyPresentation.pptx", 2, NULL, L"", L"MyFolder").get();

    // Print the texts.
    for (auto textItem : textItems->getItems()) {
        std::wcout << textItem->getText() << std::endl;
    }

    std::cin.get();

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

# Get all text items from the second slide, except empty ones.
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, folder => "MyFolder");
my $text_items = $slides_api->get_slide_text_items(%parameters);

# Print the texts.
for my $text_item (@{$text_items->{items}}) {
    print $text_item->{text}, "\n";
}
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

// Get all text items from the second slide, except empty ones.
textItems, _, e := api.SlidesApi.GetSlideTextItems("MyPresentation.pptx", 1, nil, "", "MyFolder", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

// Print the number of the text items.
fmt.Printf("Found %v items.", len(textItems.GetItems()))
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
