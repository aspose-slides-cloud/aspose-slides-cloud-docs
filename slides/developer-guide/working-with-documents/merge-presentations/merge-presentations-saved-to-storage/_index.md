---
title: "Merge Presentations Saved to Storage"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- merge presentations
- merge slides
type: docs
url: /merge-presentations-saved-to-storage/
weight: 10
---

## **Introduction**

The article shows you how to merge PowerPoint presentations saved to a storage. To merge protected presentations, passwords can be specified to open them.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/merge|POST|Merges a presentation with other presentations saved in a storage.|[Merge](https://apireference.aspose.cloud/slides/#/MergeDocument/Merge)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the initial presentation into which other presentations are merged.|
|request|object|body|true|The information about presentations to merge (paths, passwords).|
|password|string|header|false|The password to open the initial presentation.|
|folder|string|query|false|The storage folder path where the initial presentation was saved.|
|storage|string|query|false|The storage name where the initial presentation was saved.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **Merging Presentations**

Example: Merge presentations **MyResources/example1.pptx** and **MyResources/example2.pptx** into document **MyFolder/MyPresentation.pptx**. Use **password1** to open the first presentation and **my_password** to open the initial presentation.

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
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/merge?folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "password: my_password" \
     -H "Content-Type: application/json" \
     -d @request_data.json
```

request_data.json content:

```json
{ 
    "PresentationPaths": [
        "MyResources/example1.pptx", "MyResources/example2.pptx" 
    ], 
    "PresentationPasswords": [ 
        "password1"
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

{{< tabs tabTotal="11" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

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

        // Prepare request data for presentations to merge.
        var request = new PresentationsMergeRequest
        {
            PresentationPaths = new List<string> { "MyResources/example1.pptx", "MyResources/example2.pptx" }
        };

        // Merge the presentations.
        var response = api.Merge("MyPresentation.pptx", request);

        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
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

        // Prepare request data for presentations to merge.
        PresentationsMergeRequest request = new PresentationsMergeRequest();
        request.setPresentationPaths(Arrays.asList("MyResources/example1.pptx", "MyResources/example2.pptx"));
        request.setPresentationPasswords(Arrays.asList("password1"));

        // Merge the presentations.
        Document response = slidesApi.merge("MyPresentation.pptx", request, "my_password", "MyFolder", null);

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
use Aspose\Slides\Cloud\Sdk\Model\PresentationsMergeRequest;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare request data for presentations to merge.
$request = new PresentationsMergeRequest();
$request->setPresentationPaths(["MyResources/example1.pptx", "MyResources/example2.pptx"]);
$request->setPresentationPasswords(["my_password1"]);

// Merge the presentations.
$response = $slidesApi->merge("MyPresentation.pptx", $request, "my_password", "MyFolder");

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

# Prepare request data for presentations to merge.
request = PresentationsMergeRequest.new
request.presentation_paths = ["MyResources/example1.pptx", "MyResources/example2.pptx"]
request.presentation_passwords = ["password1"]

# Merge the presentations.
response = slides_api.merge("MyPresentation.pptx", request, "my_password", "MyFolder")

# Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
print response.self_uri.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.presentations_merge_request import PresentationsMergeRequest

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Prepare request data for presentations to merge.
request = PresentationsMergeRequest()
request.presentation_paths = ["MyResources/example1.pptx", "MyResources/example2.pptx"]
request.presentation_passwords = ["password1"]

# Merge the presentations.
response = slides_api.merge("MyPresentation.pptx", request, "my_password", "MyFolder")

# Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
print (response.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Prepare request data for presentations to merge.
const request = new cloud.PresentationsMergeRequest();
request.presentationPaths = ["MyResources/example1.pptx", "MyResources/example2.pptx"];
request.presentationPasswords = ["password1"];

// Merge the presentations.
slidesApi.merge("MyPresentation.pptx", request, "my_password", "MyFolder").then(response => {
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
        var slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Prepare request data for presentations to merge.
        var request = new PresentationsMergeRequest();
        request.setPresentationPaths(Arrays.asList("MyResources/example1.pptx", "MyResources/example2.pptx"));
        request.setPresentationPasswords(Arrays.asList("password1"));

        // Merge the presentations.
        var response = slidesApi.merge("MyPresentation.pptx", request, "my_password", "MyFolder", null);

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

    // Prepare request data for presentations to merge.
    auto request = std::make_shared<PresentationsMergeRequest>();
    request->setPresentationPaths({ to_string_t("MyResources/example1.pptx"), to_string_t("MyResources/example2.pptx") });
    request->setPresentationPasswords({ to_string_t("password1") });

    // Merge the presentations.
    auto response = slidesApi->merge(to_string_t("MyPresentation.pptx"), request, to_string_t("my_password"), to_string_t("MyFolder")).get();

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
use AsposeSlidesCloud::Object::PresentationsMergeRequest;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare request data for presentations to merge.
my $request = AsposeSlidesCloud::Object::PresentationsMergeRequest->new();
@{$request->{presentation_paths}} = ("MyResources/example1.pptx", "MyResources/example2.pptx");
@{$request->{presentation_passwords}} = ("password1");

# Merge the presentations.
my %merge_params = ("name" => "MyPresentation.pptx", "request" => $request, "password" => "my_password", "folder" => "MyFolder");
my $response = $slides_api->merge(%merge_params);

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
