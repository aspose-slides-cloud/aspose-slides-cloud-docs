---
title: "Merge Selected Slides into a Presentation in Storage"
keywords: "PowerPoint, presentation, REST API, Cloud API, merge presentations, merge slides"
type: docs
url: /merge-selected-slides-into-a-presentation-in-storage/
weight: 20
---

## **Introduction**

The article shows you how to merge PowerPoint presentations saved to a storage. You can merge entire presentations or specify separate slides. For protected presentations, passwords can be specified.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/merge|PUT|Merges a presentation with other presentations or some of their slides.|[OrderedMerge](https://apireference.aspose.cloud/slides/#/MergeDocument/OrderedMerge)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the initial presentation into which other presentations are merged.|
|request|object|body|true|The information about presentations to merge (paths, passwords, slide indices, etc.).|
|password|string|header|false|The password to open the initial presentation.|
|folder|string|query|false|The storage folder path where the initial presentation was saved.|
|storage|string|query|false|The storage name where the initial presentation was saved.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **Merging Selected Slides**

Example: Merge **MyFolder/MyPresentation.pptx** document with the second slide and the first slide from **MyResources/example.pptx** presentation. Both presentations were saved to a default storage. Use **mypassword01** string to open the second presentation.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Merge the Presentations**

```java
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/merge?folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -d @request_data.json
```

request_data.json content:

```json
{
    "Presentations": [
        {
            "Path": "MyResources/example.pptx",
            "Password": "mypassword01",
            "Slides": [2, 1]
        }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
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

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;
using System.Collections.Generic;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare information for the second presentation to merge.
        var presentationToMerge = new PresentationToMerge
        {
            Path = "MyResources/example.pptx",
            Slides = new List<int> { 2, 1 }
        };

        // Prepare request data for the presentations to merge.
        var request = new OrderedMergeRequest
        {
            Presentations = new List<PresentationToMerge> { presentationToMerge }
        };

        // Merge the presentations.
        var response = api.OrderedMerge("MyPresentation.pptx", request);

        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx
        Console.WriteLine(response.SelfUri.Href);
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

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Prepare information for the second presentation to merge.
        PresentationToMerge presentationToMerge = new PresentationToMerge();
        presentationToMerge.setPath("MyResources/example.pptx");
        presentationToMerge.setPassword("mypassword01");
        presentationToMerge.setSlides(Arrays.asList(2, 1));

        // Prepare request data for the presentations to merge.
        OrderedMergeRequest request = new OrderedMergeRequest();
        request.setPresentations(Arrays.asList(presentationToMerge));

        // Merge the presentations.
        Document response = slidesApi.orderedMerge("MyPresentation.pptx", request, null, "MyFolder", null);

        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
        System.out.println(response.getSelfUri().getHref());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\PresentationToMerge;
use Aspose\Slides\Cloud\Sdk\Model\OrderedMergeRequest;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare information for the second presentation to merge.
$presentationToMerge = new PresentationToMerge();
$presentationToMerge->setPath("MyResources/example.pptx");
$presentationToMerge->setPassword("mypassword01");
$presentationToMerge->setSlides([2, 1]);

// Prepare request data for the presentations to merge.
$request = new OrderedMergeRequest();
$request->setPresentations([$presentationToMerge]);

// Merge the presentations.
$response = $slidesApi->orderedMerge("MyPresentation.pptx", $request, null, "MyFolder");

// Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
echo $response->getSelfUri()->getHref();
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_secret"

slides_api = SlidesApi.new(configuration)

# Prepare information for the second presentation to merge.
presentation_to_merge = PresentationToMerge.new
presentation_to_merge.path = "MyResources/example.pptx"
presentation_to_merge.password = "mypassword01"
presentation_to_merge.slides = [2, 1]

# Prepare request data for the presentations to merge.
request = OrderedMergeRequest.new
request.presentations = [presentation_to_merge]

# Merge the presentations.
response = slides_api.ordered_merge("MyPresentation.pptx", request, nil, "MyFolder")

# Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
print response.self_uri.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.ordered_merge_request import OrderedMergeRequest
from asposeslidescloud.models.presentation_to_merge import PresentationToMerge

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Prepare information for the second presentation to merge.
presentation_to_merge = PresentationToMerge()
presentation_to_merge.path = "MyResources/example.pptx"
presentation_to_merge.password = "mypassword01"
presentation_to_merge.slides = [2, 1]

# Prepare request data for the presentations to merge.
request = OrderedMergeRequest()
request.presentations = [presentation_to_merge]

# Merge the presentations.
response = slides_api.ordered_merge("MyPresentation.pptx", request, None, "MyFolder")

# Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
print(response.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Prepare information for the second presentation to merge.
const presentationToMerge = new cloud.PresentationToMerge();
presentationToMerge.path = "MyResources/example.pptx";
presentationToMerge.password = "mypassword01";
presentationToMerge.slides = [2, 1];

// Prepare request data for the presentations to merge.
const request = new cloud.OrderedMergeRequest();
request.presentations = [presentationToMerge];

// Merge the presentations.
slidesApi.orderedMerge("MyPresentation.pptx", request, null, "MyFolder").then(response => {
    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
    console.log(response.body.selfUri.href);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Prepare information for the second presentation to merge.
        PresentationToMerge presentationToMerge = new PresentationToMerge();
        presentationToMerge.setPath("MyResources/example.pptx");
        presentationToMerge.setPassword("mypassword01");
        presentationToMerge.setSlides(Arrays.asList(2, 1));

        // Prepare request data for the presentations to merge.
        OrderedMergeRequest request = new OrderedMergeRequest();
        request.setPresentations(Arrays.asList(presentationToMerge));

        // Merge the presentations.
        Document response = slidesApi.orderedMerge("MyPresentation.pptx", request, null, "MyFolder", null);

        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
        System.out.println(response.getSelfUri().getHref());
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility;
using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(to_string_t("my_client_id"), to_string_t("my_client_secret"));

    // Prepare information for the second presentation to merge.
    auto presentationToMerge = std::make_shared<PresentationToMerge>();
    presentationToMerge->setPath(to_string_t("MyResources/example.pptx"));
    presentationToMerge->setPassword(to_string_t("mypassword01"));
    presentationToMerge->setSlides({ 2, 1 });

    // Prepare request data for the presentations to merge.
    auto request = std::make_shared<OrderedMergeRequest>();
    request->setPresentations({ presentationToMerge });

    // Merge the presentations.
    auto response = slidesApi->orderedMerge(
        to_string_t("MyPresentation.pptx"), request, string_t(), to_string_t("MyFolder")).get();

    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
    std::cout << to_utf8string(response->getSelfUri()->getHref());

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::PresentationToMerge;
use AsposeSlidesCloud::Object::OrderedMergeRequest;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare information for the second presentation to merge.
my $presentation_to_merge = AsposeSlidesCloud::Object::PresentationToMerge->new();
$presentation_to_merge->{path} = "MyResources/example.pptx";
$presentation_to_merge->{password} = "mypassword01";
@{$presentation_to_merge->{slides}} = (2, 1);

# Prepare request data for the presentations to merge.
my $request = AsposeSlidesCloud::Object::OrderedMergeRequest->new();
@{$request->{presentations}} = ($presentation_to_merge);

# Merge the presentations.
my %merge_params = ("name" => "MyPresentation.pptx", "request" => $request, "folder" => "MyFolder");
my $response = $slides_api->ordered_merge(%merge_params);

# Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
print $response->{self_uri}->{href};
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
