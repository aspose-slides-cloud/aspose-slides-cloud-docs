---
title: "Delete Slides from a PowerPoint Presentation"
type: docs
url: /delete-slides-from-a-powerpoint-presentation/
weight: 20
---

## **Introduction**

Aspose.Slides Cloud allows you to delete slides from a PowerPoint presentation. Using the request methods below, you can delete a single slide, multiple slides with specified indexes, or all slides at once.

## **DeleteSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}|DELETE|Deletes a slide from a presentation at the specified index.|[DeleteSlide](https://apireference.aspose.cloud/slides/#/Slides/DeleteSlide)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of a presentation.|
|slideIndex|integer|path|true|The 1-based index of the slide to be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete the **first** slide from **MyFolder/MyPresentation.pptx** document that contains three slides and was saved to **MyStorage**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Slide**

```java
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder&storage=MyStorage" \
     -H "authorization: Bearer <access_token>"
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

        // Delete the first slide from the presentation.
        var response = api.DeleteSlide("MyPresentation.pptx", 1, null);

        // Print the links of the remaining slides.
        foreach (var slide in response.SlideList)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
            Console.WriteLine(slide.Href);
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

        // Delete the first slide from the presentation.
        Slides response = slidesApi.deleteSlide("MyPresentation.pptx", 1, null, "MyFolder", "MyStorage");

        // Print the links of the remaining slides.
        for (ResourceUri slide : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
            System.out.println(slide.getHref());
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

// Delete the first slide from the presentation.
$response = $slidesApi->deleteSlide("MyPresentation.pptx", 1, null, "MyFolder", "MyStorage");

// Print the links of the remaining slides.
foreach ($response->getSlideList() as $slide)
{
    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    echo $slide->getHref(), "\n";
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

# Delete the first slide from the presentation.
response = slides_api.delete_slide("MyPresentation.pptx", 1, nil, "MyFolder", "MyStorage")

# Print the links of the remaining slides.
for slide in response.slide_list
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    puts slide.href
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Delete the first slide from the presentation.
response = slides_api.delete_slide("MyPresentation.pptx", 1, None, "MyFolder", "MyStorage")

# Print the links of the remaining slides.
for slide in response.slide_list:
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print(slide.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret")

// Delete the first slide from the presentation.
slidesApi.deleteSlide("MyPresentation.pptx", 1, null, "MyFolder", "MyStorage").then((response) => {
    // Print the links of the remaining slides.
    response.body.slideList.forEach(slide =>
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
        console.log(slide.href)
    )
})
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

        // Delete the first slide from the presentation.
        Slides response = slidesApi.deleteSlide("MyPresentation.pptx", 1, null, "MyFolder", "MyStorage");

        // Print the links of the remaining slides.
        for (ResourceUri slide : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
            System.out.println(slide.getHref());
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

    // Delete the first slide from the presentation.
    auto response = slidesApi->deleteSlide(L"MyPresentation.pptx", 1, L"", L"MyFolder", L"MyStorage").get();

    // Print the links of the remaining slides.
    for (auto slide : response->getSlideList()) {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
        std::wcout << slide->getHref() << std::endl;
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

# Delete the first slide from the presentation.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, folder => "MyFolder", storage => "MyStorage");
my $response = $slides_api->delete_slide(%parameters);

# Print the links of the remaining slides.
for $slide (@{$response->{slide_list}}) {
     # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1?folder=MyFolder etc.
    print $slide->{href}, "\n";
}
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **DeleteSlides**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides|DELETE|Deletes slides from a presentation at the specified indices.|[DeleteSlides](https://apireference.aspose.cloud/slides/#/Slides/DeleteSlides)|

#### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The file name of a presentation.|
|slides|string|query|false|The 1-based indices of the slides to be deleted. If the indices are not specified, all slides are deleted and one blank slide is added.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete the slides with indices **1, 3, 5** from **MyPresentation.pptx** document that contains five slides and was saved in the default storage root folder. Use **my_password** string to open the presentation.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=my_client_id&client_secret=my_client_secret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Slides**

```java
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?slides=1,3,5" \
     -H "authorization: Bearer <access_token>" \
     -H "password: my_password"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "slideList": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1",
            "relation": "self",
            "slideIndex": 1
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2",
            "relation": "self",
            "slideIndex": 2
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides",
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
        SlidesApi api = new SlidesApi("my_client_id", "my_client_secret");

        // Delete the slides from the presentation.
        var slideIndices = new List<int> { 1, 3, 5 };
        var response = api.DeleteSlides("MyPresentation.pptx", slideIndices);

        // Print the links of the remaining slides.
        foreach (var slide in response.SlideList)
        {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
            Console.WriteLine(slide.Href);
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
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_secret");

        // Delete the slides from the presentation.
        ArrayList slideIndices = new ArrayList(Arrays.asList(1, 3, 5));
        Slides response = slidesApi.deleteSlides("MyPresentation.pptx", slideIndices, "my_password", null, null);

        // Print the links of the remaining slides.
        for (ResourceUri slide : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
            System.out.println(slide.getHref());
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

// Delete the slides from the presentation.
$response = $slidesApi->deleteSlides("MyPresentation.pptx", [1, 3, 5], "my_password");

// Print the links of the remaining slides.
foreach ($response->getSlideList() as $slide)
{
    // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
    echo $slide->getHref(), "\n";
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

# Delete the slides from the presentation.
response = slides_api.delete_slides("MyPresentation.pptx", [1, 3, 5], "my_password")

# Print the links of the remaining slides.
for slide in response.slide_list
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
    puts slide.href
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "my_client_id", "my_client_secret")

# Delete the slides from the presentation.
response = slides_api.delete_slides("MyPresentation.pptx", [1, 3, 5], "my_password")

# Print the links of the remaining slides.
for slide in response.slide_list:
    # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
    print(slide.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("my_client_id", "my_client_secret")

// Delete the slides from the presentation.
slidesApi.deleteSlides("MyPresentation.pptx", [1, 3, 5], "my_password").then((response) => {
    // Print the links of the remaining slides.
    response.body.slideList.forEach(slide =>
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
        console.log(slide.href)
    )
})
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

        // Delete the slides from the presentation.
        ArrayList slideIndices = new ArrayList(Arrays.asList(1, 3, 5));
        Slides response = slidesApi.deleteSlides("MyPresentation.pptx", slideIndices, "my_password", null, null);

        // Print the links of the remaining slides.
        for (ResourceUri slide : response.getSlideList()) {
            // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
            System.out.println(slide.getHref());
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

    // Delete the slides from the presentation.
    auto response = slidesApi->deleteSlides(L"MyPresentation.pptx", {1, 3, 5}, L"my_password").get();

    // Print the links of the remaining slides.
    for (auto slide : response->getSlideList()) {
        // Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
        std::wcout << slide->getHref() << std::endl;
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

# Delete the slides from the presentation.
my @slide_indices = (1, 3, 5);
my %parameters = (name => "MyPresentation.pptx", slides => \@slide_indices, password => "my_password");
my $response = $slides_api->delete_slides(%parameters);

# Print the links of the remaining slides.
for $slide (@{$response->{slide_list}}) {
     # Output: https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1 etc.
    print $slide->{href}, "\n";
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
