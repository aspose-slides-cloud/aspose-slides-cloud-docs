---
title: "Deleting Shapes from a Group Shape"
type: docs
url: /deleting-shapes-from-a-group-shape/
weight: 40
---


## **Introduction**

This article shows you how to delete shapes from a group shape using Aspose.Slides Cloud API in your applications. The following methods allow you to specify a path to a group shape or subgroup from which you want to delete one or more shapes. The sub-shape path is a string that contains shape index (e.g., "1") or a path in case of more than one level of grouping( e.g. "1/shapes/1").

## **DeleteShape**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}|DELETE|Deletes a shape.|[DeleteShape](https://apireference.aspose.cloud/slides/#/Shapes/DeleteShape)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide with the group shape.|
|shapeIndex|integer|path|true|The 1-based index of the shape to delete.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
|subShape|string|query|false|Sub-shape path (e.g. "3", "3/shapes/2)

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

The **second** slide in **MyFolder/MyPresentation.pptx** document contains a **single** shape. The shape is a group shape consisting of **four** shapes. Delete the **third** shape from the group.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Shape**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1?folder=MyFolder&subShape=3" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "shapesLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/shapes/1?folder=MyFolder",
            "relation": "self",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/shapes/2?folder=MyFolder",
            "relation": "self",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/shapes/3?folder=MyFolder",
            "relation": "self",
            "slideIndex": 2
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/shapes?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2,
        "shapeIndex": 1
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

        // Delete the shape from the group shape.
        var remainingShapes = slidesApi.DeleteShape("MyPresentation.pptx", 1, 4, null, "MyFolder", null, "1");

        // Print resource references for the remaining shapes.
        foreach (var shape in remainingShapes.ShapesLinks)
        {
            Console.WriteLine(shape.Href);
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

        // Delete the shape from the group shape.
        Shapes remainingShapes = slidesApi.deleteShape("MyPresentation.pptx", 1, 4, null, "MyFolder", null, "1");

        // Print resource references for the remaining shapes.
        for (ResourceUri shape : remainingShapes.getShapesLinks())
        {
            System.out.println(shape.getHref());
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

// Delete the shape from the group shape.
$remainingShapes = $slidesApi->deleteShape("MyPresentation.pptx", 1, 4, null, "MyFolder", null, "1");

// Print resource references for the remaining shapes.
foreach ($remainingShapes->getShapesLinks() as $shape)
{
    echo $shape->getHref(), "\n";
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

# Delete the shape from the group shape.
remaining_shapes = slides_api.delete_shape("MyPresentation.pptx", 1, 4, nil, "MyFolder", nil, "1")

# Print resource references for the remaining shapes.
for shape in remaining_shapes.shapes_links
    puts shape.href
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Delete the shape from the group shape.
remaining_shapes = slides_api.delete_shape("MyPresentation.pptx", 1, 4, None, "MyFolder", None, "1")

# Print resource references for the remaining shapes.
for shape in remaining_shapes.shapes_links:
    print(shape.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Delete the shape from the group shape.
slidesApi.deleteShape("MyPresentation.pptx", 1, 4, null, "MyFolder", null, "1").then((remainingShapes) => {
    remainingShapes.body.shapesLinks.forEach(shape =>
        // Print resource references for the remaining shapes.
        console.log(shape.href)
    )
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
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Delete the shape from the group shape.
    auto remainingShapes = slidesApi->deleteShape(L"MyPresentation.pptx", 1, 4, L"", L"MyFolder", L"", L"1").get();

    // Print resource references for the remaining shapes.
    for (auto shape : remainingShapes->getShapesLinks()) {
        std::wcout << shape->getHref() << std::endl;
    }

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

# Delete the shape from the group shape.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, shape_index => 4, folder => "MyFolder", sub_shape=> "1");
my $remaining_shapes = $slides_api->delete_shape(%parameters);

# Print resource references for the remaining shapes.
for $shape (@{$remaining_shapes->{shapes_links}}) {
    print $shape->{href}, "\n";
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **DeleteShapes**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes|DELETE|Deletes shapes.|[DeleteShapes](https://apireference.aspose.cloud/slides/#/Shapes/DeleteShapes)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide with the group shape.|
|shapes|string|query|false|The indices of the shapes to be deleted. Delete all by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
|subShape|string|query|false|Sub-shape path (e.g. "3", "3/shapes/2)

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

The **second** slide in **MyFolder/MyPresentation.pptx** document contains a **single** shape. The shape is a group shape consisting of **four** shapes. Delete the **first** and **third** shapes from the group.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Shapes**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes?subShape=1&shapes=1,3&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "shapesLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/shapes/1?folder=MyFolder",
            "relation": "self",
            "slideIndex": 2
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/shapes/2?folder=MyFolder",
            "relation": "self",
            "slideIndex": 2
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/shapes?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2,
        "shapeIndex": 1
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
using System;
using System.Collections.Generic;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Delete the shapes from the group shape.
        var shapeIndices = new List<int> { 1, 2 };
        var remainingShapes = slidesApi.DeleteShapes("MyPresentation.pptx", 1, shapeIndices, null, "MyFolder", null, "4");

        // Print resource references for the remaining shapes.
        foreach (var shape in remainingShapes.ShapesLinks)
        {
            Console.WriteLine(shape.Href);
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
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Delete the shapes from the group shape.
        ArrayList shapeIndices = new ArrayList(Arrays.asList(1, 2));
        Shapes remainingShapes = slidesApi.deleteShapes("MyPresentation.pptx", 1, shapeIndices, null, "MyFolder", null, "4");

        // Print resource references for the remaining shapes.
        for (ResourceUri shape : remainingShapes.getShapesLinks()) {
            System.out.println(shape.getHref());
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

// Delete the shapes from the group shape.
$remainingShapes = $slidesApi->deleteShapes("MyPresentation.pptx", 1, [1, 2], null, "MyFolder", null, "4");

// Print resource references for the remaining shapes.
foreach ($remainingShapes->getShapesLinks() as $shape) {
    echo $shape->getHref(), "\n";
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

# Delete the shapes from the group shape.
remaining_shapes = slides_api.delete_shapes("MyPresentation.pptx", 1, [1, 2], nil, "MyFolder", nil, "4")

# Print resource references for the remaining shapes.
for shape in remaining_shapes.shapes_links
    puts shape.href
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Delete the shapes from the group shape.
remaining_shapes = slides_api.delete_shapes("MyPresentation.pptx", 1, [1, 2], None, "MyFolder", None, "4")

# Print resource references for the remaining shapes.
for shape in remaining_shapes.shapes_links:
    print(shape.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Delete the shapes from the group shape.
slidesApi.deleteShapes("MyPresentation.pptx", 1, [1, 2], null, "MyFolder", null, "4").then((remainingShapes) => {
    remainingShapes.body.shapesLinks.forEach(shape =>
        // Print resource references for the remaining shapes.
        console.log(shape.href)
    )
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
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Delete the shapes from the group shape.
    auto remainingShapes = slidesApi->deleteShapes(L"MyPresentation.pptx", 1, {1, 2}, L"", L"MyFolder", L"", L"4").get();

    // Print resource references for the remaining shapes.
    for (auto shape : remainingShapes->getShapesLinks()) {
        std::wcout << shape->getHref() << std::endl;
    }

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

# Delete the shapes from the group shape.
my @shape_indices = (1, 3);
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, shapes => \@shape_indices, folder => "MyFolder", sub_shape=>"4");
my $remaining_shapes = $slides_api->delete_shapes(%parameters);

# Print resource references for the remaining shapes.
for $shape (@{$remaining_shapes->{shapes_links}}) {
    print $shape->{href}, "\n";
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
