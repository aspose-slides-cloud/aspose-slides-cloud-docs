---
title: "Move a Slide"
keywords: "PowerPoint, presentation, REST API, Cloud API, slide, move a slide, slide position, reorder slides"
type: docs
url: /move-a-slide/
weight: 60
---

## **Introduction**

Aspose.Slides Cloud lets you move a slide to a new position within a PowerPoint presentation. The following methods allow you to both move a single slide and change the order of multiple slides at the same time.

## **MoveSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/move|POST|Moves a presentation slide to a new position.|[MoveSlide](https://apireference.aspose.cloud/slides/#/Slides/MoveSlide)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide to be moved.|
|newPosition|integer|query|true|The new index for the slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

**MyFolder/MyPresentation.pptx** file saved to **MyStorage** contains four slides. Move the **third** slide to the **first** position.   

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Move the Slide**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/move?newPosition=1&folder=MyFolder&storage=MyStorage" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

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
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/4?folder=MyFolder",
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

        // Move the third slide to the first position.
        var response = api.MoveSlide("MyPresentation.pptx", 3, 1);

        // Print links to all slides.
        foreach (var resourceUri in response.SlideList)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
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

        // Move the third slide to the first position.
        Slides response = slidesApi.moveSlide("MyPresentation.pptx", 3, 1, null, "MyFolder", "MyStorage");

        // Print links to all slides.
        for (ResourceUri resourceUri : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

// Move the third slide to the first position.
$response = $slidesApi->moveSlide("MyPresentation.pptx", 3, 1, null, "MyFolder", "MyStorage");

// Print links to all slides.
foreach ($response->getSlideList() as $resourceUri) {
    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

# Move the third slide to the first position.
response = slides_api.move_slide("MyPresentation.pptx", 3, 1, nil, "MyFolder", "MyStorage")

# Print links to all slides.
for resource_uri in response.slide_list
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

# Move the third slide to the first position.
response = slides_api.move_slide("MyPresentation.pptx", 3, 1, None, "MyFolder", "MyStorage")

# Print links to all slides.
for resource_uri in response.slide_list:
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print(resource_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Move the third slide to the first position.
slidesApi.moveSlide("MyPresentation.pptx", 3, 1, null, "MyFolder", "MyStorage").then(response => {
    // Print links to all slides.
    response.body.slideList.forEach(resourceUri => {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

        // Move the third slide to the first position.
        Slides response = slidesApi.moveSlide("MyPresentation.pptx", 3, 1, null, "MyFolder", "MyStorage");

        // Print links to all slides.
        for (ResourceUri resourceUri : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

    // Move the third slide to the first position.
    auto response = slidesApi->moveSlide(L"MyPresentation.pptx", 3, 1, L"", L"MyFolder", L"MyStorage").get();

    // Print links to all slides.
    for (auto resourceUri : response->getSlideList()) {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

# Move the third slide to the first position.
my %parameters = (name => "MyPresentation.pptx", slide_index => 3, new_position => 1, folder => "MyFolder", storage => "MyStorage");
my $response = $slides_api->move_slide(%parameters);

# Print links to all slides.
for my $resource_uri (@{$response->{slide_list}}) {
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print $resource_uri->{href}, "\n";
}
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **ReorderSlides**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/reorder|POST|Changes the order of presentation slides.|[ReorderSlides](https://apireference.aspose.cloud/slides/#/Slides/ReorderSlides)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|oldPositions|string|query|false|A comma separated array of 1-based indices of slides to be reordered.|
|newPositions|string|query|false|A comma separated array of new slide positions.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

**MyFolder/MyPresentation.pptx** file saved to **MyStorage** contains three slides. Swap the **first** and **last** slides.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Reorder the Slides**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/reorder?oldPositions=1,3&newPositions=3,1&folder=MyFolder&storage=MyStorage" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

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

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System;
using System.Collections.Generic;

class Application
{
    static void Main()
    {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Swap the first and third slides.
        var slideIndices = new List<int> { 1, 3 };
        var newPositions = new List<int> { 3, 1 };
        var response = api.ReorderSlides("MyPresentation.pptx", slideIndices, newPositions);

        // Print links to all slides.
        foreach (var resourceUri in response.SlideList)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

        // Swap the first and third slides.
        ArrayList slideIndices = new ArrayList(Arrays.asList(1, 3));
        ArrayList newPositions = new ArrayList(Arrays.asList(3, 1));
        Slides response = api.reorderSlides("MyPresentation.pptx", slideIndices, newPositions, null, null, null);

        // Print links to all slides.
        for (ResourceUri resourceUri : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
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

// Swap the first and third slides.
$response = $slidesApi->reorderSlides("MyPresentation.pptx", [1, 3], [3, 1], null, "MyFolder", "MyStorage");

// Print links to all slides.
foreach ($response->getSlideList() as $resourceUri) {
    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

# Swap the first and third slides.
response = slides_api.reorder_slides("MyPresentation.pptx", [1, 3], [3, 1], nil, "MyFolder", "MyStorage")

# Print links to all slides.
for resource_uri in response.slide_list
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

# Swap the first and third slides.
response = slides_api.reorder_slides("MyPresentation.pptx", [1, 3], [3, 1], None, "MyFolder", "MyStorage")

# Print links to all slides.
for resource_uri in response.slide_list:
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print(resource_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret");

// Swap the first and third slides.
slidesApi.reorderSlides("MyPresentation.pptx", [1, 3], [3, 1], null, "MyFolder", "MyStorage").then(response => {
    // Print links to all slides.
    response.body.slideList.forEach(resourceUri => {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Swap the first and third slides.
        ArrayList slideIndices = new ArrayList(Arrays.asList(1, 3));
        ArrayList newPositions = new ArrayList(Arrays.asList(3, 1));
        Slides response = slidesApi.reorderSlides("MyPresentation.pptx", slideIndices, newPositions, null, "MyFolder", "MyStorage");

        // Print links to all slides.
        for (ResourceUri resourceUri : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

    // Swap the first and third slides.
    auto response = slidesApi->reorderSlides(L"MyPresentation.pptx", { 1, 3 }, { 3, 1 }, L"", L"MyFolder", L"MyStorage").get();

    // Print links to all slides.
    for (auto resourceUri : response->getSlideList()) {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
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

# Swap the first and third slides.
my %parameters = (name => "MyPresentation.pptx", old_positions => [1, 3], new_positions => [3, 1], folder => "MyFolder", storage => "MyStorage");
my $response = $slides_api->reorder_slides(%parameters);

# Print links to all slides.
for my $resource_uri (@{$response->{slide_list}}) {
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print $resource_uri->{href}, "\n";
}
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
