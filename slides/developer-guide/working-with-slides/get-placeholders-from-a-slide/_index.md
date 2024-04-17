---
title: "Get Placeholders from a Slide"
type: docs
url: /get-placeholders-from-a-slide/
weight: 30
---

## **Introduction**

Aspose.Slides Cloud allows you to read placeholder information from a PowerPoint presentation. The presentation file must be already saved to a storage folder. Using the request methods below, you can get information about a specified placeholder or all placeholders on a slide.

## **GetPlaceholders**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/placeholders|GET|Returns a list of all placeholders from a presentation slide.|[GetPlaceholders](https://apireference.aspose.cloud/slides/#/Placeholders/GetPlaceholders)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of a presentation.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Get information about **all placeholders** on the **first** slide in **MyFolder/MyPresentation.pptx** file saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Information about Placeholders**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders?folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "placeholderLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder",
            "relation": "self",
            "slideIndex": 1
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/2?folder=MyFolder",
            "relation": "self",
            "slideIndex": 1
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1
    }
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
using System;

class Application
{
    static void Main()
    {
       	SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Get information about all placeholders on the first slide.
        var response = api.GetPlaceholders("MyPresentation.pptx", 1);

        // Print placeholder links from the response.
        foreach (var resourceUri in response.PlaceholderLinks)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1 etc.
            Console.WriteLine(resourceUri.Href);
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
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Get information about all placeholders on the first slide.
        Placeholders response = slidesApi.getPlaceholders("MyPresentation.pptx", 1, null, "MyFolder", null);

        // Print placeholder links from the response.
        for (ResourceUri resourceUri : response.getPlaceholderLinks()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder etc.
            System.out.println(resourceUri.getHref());
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
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Get information about all placeholders on the first slide.
$response = $slidesApi->getPlaceholders("MyPresentation.pptx", 1, null, "MyFolder");

// Print placeholder links from the response.
foreach ($response->getPlaceholderLinks() as $resourceUri) {
    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder etc.
    echo $resourceUri->getHref(), "\n";
}
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

# Get information about all placeholders on the first slide.
response = slides_api.get_placeholders("MyPresentation.pptx", 1, nil, "MyFolder")

# Print placeholder links from the response.
for resource_uri in response.placeholder_links
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder etc.
    puts resource_uri.href
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Get information about all placeholders on the first slide.
response = slides_api.get_placeholders("MyPresentation.pptx", 1, None, "MyFolder")

# Print placeholder links from the response.
for resource_uri in response.placeholder_links:
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder etc.
    print(resource_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Get information about all placeholders on the first slide.
const response = slidesApi.getPlaceholders("MyPresentation.pptx", 1, null, "MyFolder").then(response => {
    // Print placeholder links from the response.
    response.body.placeholderLinks.forEach(resourceUri => {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder etc.
        console.log(resourceUri.href);
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Get information about all placeholders on the first slide.
        Placeholders response = slidesApi.getPlaceholders("MyPresentation.pptx", 1, null, "MyFolder", null);

        // Print placeholder links from the response.
        for (var resourceUri : response.getPlaceholderLinks()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder etc.
            System.out.println(resourceUri.getHref());
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"my_client_id", L"my_client_secret");

    // Get information about all placeholders on the first slide.
    auto response = slidesApi->getPlaceholders(L"MyPresentation.pptx", 1, L"", L"MyFolder").get();

    // Print placeholder links from the response.
    for (auto resourceUri : response->getPlaceholderLinks()) {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder etc.
        std::wcout << resourceUri->getHref() << std::endl;
    }

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Get information about all placeholders on the first slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, folder => "MyFolder");
my $response = $slides_api->get_placeholders(%parameters);

# Print placeholder links from the response.
for my $resource_uri (@{$response->{placeholder_links}}) {
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/placeholders/1?folder=MyFolder etc.
    print $resource_uri->{href}, "\n";
}
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **GetPlaceholder**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/placeholders/{placeholderIndex}|GET|Returns information about a placeholder.|[GetPlaceholder](https://apireference.aspose.cloud/slides/#/Placeholders/GetPlaceholder)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of a presentation.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|placeholderIndex|integer|path|true|The 1-based index of a placeholder.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Get information about the **first** placeholder on the **second** slide from **MyPresentation.pptx** file saved to **MyStorage**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get Information about the Placeholder**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/placeholders/1?storage=MyStorage" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "index": 1,
    "orientation": "Horizontal",
    "size": "Full",
    "type": "CenteredTitle",
    "shape": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1",
        "relation": "self",
        "slideIndex": 2,
        "shapeIndex": 1
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/placeholders/1",
        "relation": "self",
        "slideIndex": 2
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System;

class Application
{
    static void Main()
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Get information about the placeholder.
        var response = api.GetPlaceholder("MyPresentation.pptx", 2, 1);

        Console.WriteLine(response.ToString());
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
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Get information about the placeholder.
        Placeholder response = slidesApi.getPlaceholder("MyPresentation.pptx", 2, 1, null, null, "MyStorage");

        System.out.println(response.toString());
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
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$slidesApi = new SlidesApi(null, $configuration);

// Get information about the placeholder.
$response = $slidesApi->getPlaceholder("MyPresentation.pptx", 2, 1, null, null, "MyStorage");

echo $response;
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

# Get information about the placeholder.
response = slides_api.get_placeholder("MyPresentation.pptx", 2, 1, nil, nil, "MyStorage")

print response
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Get information about the placeholder.
response = slides_api.get_placeholder("MyPresentation.pptx", 2, 1, None, None, "MyStorage")

print(response)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Get information about the placeholder.
slidesApi.getPlaceholder("MyPresentation.pptx", 2, 1, null, null, "MyStorage").then(response => {
    console.log(response.body);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Get information about the placeholder.
        Placeholder response = slidesApi.getPlaceholder("MyPresentation.pptx", 2, 1, null, null, "MyStorage");

        System.out.println(response.toString());
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"my_client_id", L"my_client_secret");
    
    // Get information about the placeholder.
    auto response = slidesApi->getPlaceholder(L"MyPresentation.pptx", 2, 1, L"", L"", L"MyStorage").get();

    std::wcout << response->toJson();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Get information about the placeholder.
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, placeholder_index => 1, storage => "MyStorage");
my $response = $slides_api->get_placeholder(%parameters);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
