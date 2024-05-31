---
title: "Read Information about a Presentation"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
type: docs
url: /read-information-about-a-presentation/
weight: 20
---

## **Introduction**
The following method returns a JSON/XML representation of a presentation. The different representations of a presentation are basically the formats the presentation can be converted to. So, in order to achieve a conversion, all the user has to do is use one of the links.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}|GET|Reads information about a presentation.|[GetPresentation](https://apireference.aspose.cloud/slides/#/Document/GetPresentation)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of the presentation.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder path where the presentation file is located.|
|storage|string|query|false|The storage name where the presentation file is located.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **cURL Examples**
Read information about a presentation **Data/Sales.pptx** from a **Main** storage.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

Request JSON information:
```java
curl -X GET "https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data&storage=Main" \
     -H "accept: application/json" \
     -H "authorization: Bearer <access_token>"
```

Request XML information:
```java
curl -X GET "https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data&storage=Main" \
     -H "accept: application/xml" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

Full resource representation:

{{< expand-list title="JSON" >}}

```json
{
    "documentProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/documentProperties?folder=Data",
        "relation": "self"
    },
    "viewProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/viewProperties?folder=Data",
        "relation": "self"
    },
    "slides": {
        "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/slides?folder=Data",
        "relation": "self"
    },
    "images": {
        "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/images?folder=Data",
        "relation": "self"
    },
    "layoutSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/layoutSlides?folder=Data",
        "relation": "self"
    },
    "masterSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/masterSlides?folder=Data",
        "relation": "self"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data",
        "relation": "self"
    },
    "alternateLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/odp?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Odp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/fodp?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Fodp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/ppt?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Ppt"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/pdf?folder=Data",
            "relation": "alternate",
            "linkType": "application/pdf",
            "title": "Download as Pdf"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/tiff?folder=Data",
            "relation": "alternate",
            "linkType": "image/tiff",
            "title": "Download as Tiff"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/xps?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-xpsdocument",
            "title": "Download as Xps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/pps?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/ppsx?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "title": "Download as Ppsx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/pptm?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "title": "Download as Pptm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/ppsm?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "title": "Download as Ppsm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/pot?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pot"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/potx?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
            "title": "Download as Potx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/potm?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
            "title": "Download as Potm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/otp?folder=Data",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation-template",
            "title": "Download as Otp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/Sales.pptx/html?folder=Data",
            "relation": "alternate",
            "linkType": "text/html",
            "title": "Download as Html"
        }
    ]
}
```
{{< /expand-list >}}

{{< expand-list title="XML" >}}

```xml
<Document xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data" rel="self" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/odp?folder=Data" rel="alternate" type="application/vnd.oasis.opendocument.presentation" title="Download as Odp" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/fodp?folder=Data" rel="alternate" type="application/vnd.oasis.opendocument.presentation" title="Download as Fodp" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/ppt?folder=Data" rel="alternate" type="application/vnd.ms-powerpoint" title="Download as Ppt" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/pdf?folder=Data" rel="alternate" type="application/pdf" title="Download as Pdf" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/tiff?folder=Data" rel="alternate" type="image/tiff" title="Download as Tiff" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/xps?folder=Data" rel="alternate" type="application/vnd.ms-xpsdocument" title="Download as Xps" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/pps?folder=Data" rel="alternate" type="application/vnd.ms-powerpoint" title="Download as Pps" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/ppsx?folder=Data" rel="alternate" type="application/vnd.openxmlformats-officedocument.presentationml.slideshow" title="Download as Ppsx" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/pptm?folder=Data" rel="alternate" type="application/vnd.ms-powerpoint.presentation.macroEnabled.12" title="Download as Pptm" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/ppsm?folder=Data" rel="alternate" type="application/vnd.ms-powerpoint.slideshow.macroEnabled.12" title="Download as Ppsm" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/pot?folder=Data" rel="alternate" type="application/vnd.ms-powerpoint" title="Download as Pot" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/potx?folder=Data" rel="alternate" type="application/vnd.openxmlformats-officedocument.presentationml.template" title="Download as Potx" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/potm?folder=Data" rel="alternate" type="application/vnd.ms-powerpoint.template.macroEnabled.12" title="Download as Potm" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/otp?folder=Data" rel="alternate" type="application/vnd.oasis.opendocument.presentation-template" title="Download as Otp" />
    <link href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/html?folder=Data" rel="alternate" type="text/html" title="Download as Html" />
    <DocumentProperties href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/documentProperties?folder=Data" rel="self" />
    <ViewProperties href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/viewProperties?folder=Data" rel="self" />
    <Slides href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/slides?folder=Data" rel="self" />
    <Images href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/images?folder=Data" rel="self" />
    <LayoutSlides href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/layoutSlides?folder=Data" rel="self" />
    <MasterSlides href="https://api.aspose.cloud/v3.0/slides/Sales.pptx/masterSlides?folder=Data" rel="self" />
</Document>
```

{{< /expand-list >}}

{{< /tab >}}

{{< /tabs >}}

## **SDK Examples**
Read information about a presentation **Data/Sales.pptx** from a **Main** storage.

{{< tabs tabTotal="11" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System;
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        var response = api.GetPresentation("Sales.pptx");
        Console.WriteLine(response.SelfUri.Href); // https://api.aspose.cloud/v3.0/slides/Sales.pptx
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_key");

        Document response = slidesApi.getPresentation("Sales.pptx", null, null, null);
        System.out.println(response.getSelfUri().getHref()); // https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/aspose-slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$response = $slidesApi->getPresentation("Sales.pptx");
echo $response->getSelfUri()->getHref(); // https://api.aspose.cloud/v3.0/slides/Sales.pptx
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require 'aspose_slides_cloud'

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_key"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

response = slides_api.get_presentation("Sales.pptx")
print response.self_uri.href # https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

response = slides_api.get_presentation("Sales.pptx")
print(response.self_uri.href) # https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_key");

slidesApi.getPresentation("Sales.pptx").then(response => {
    console.log(response.body.selfUri.href); // https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.ApiException;

public class Main {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var response = slidesApi.getPresentation("Sales.pptx", null, null, null);
        System.out.println(response.getSelfUri().getHref()); // https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data
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

    auto response = slidesApi->getPresentation(L"Sales.pptx").get();

    std::cout << to_utf8string(response->getSelfUri()->getHref()); // https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=Data

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

## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
