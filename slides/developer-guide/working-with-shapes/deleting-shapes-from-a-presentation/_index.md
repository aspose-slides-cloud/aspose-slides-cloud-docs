---
title: "Deleting shapes from a Presentation"
type: docs
url: /deleting-shapes-from-a-presentation/
weight: 80
---


## **Introduction**

With Aspose.Slides Cloud, you can easily delete shapes from a PowerPoint presentation. The following methods allow you to delete shapes at specified indices or all shapes at once from a slide. The methods return information about the remaining shapes.

## **DeleteShape**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}|DELETE|Deletes a shape from a presentation slide.|[DeleteShape](https://apireference.aspose.cloud/slides/#/Shapes/DeleteShape)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide contaning the shapes.|
|shapeIndex|integer|path|true|The 1-based index of the shape to delete.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
|subShape|string|query|false|Sub-shape path (e.g. "3", "3/shapes/2")

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

**MyFolder/MyPresentation.pptx** document contains **three** shapes on the **first** slide. Delete the **second** shape.

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
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "shapesLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1?folder=MyFolder",
            "relation": "self",
            "slideIndex": 1
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2?folder=MyFolder",
            "relation": "self",
            "slideIndex": 1
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1
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

        // Delete the second shape from the first slide.
        var remainingShapes = slidesApi.DeleteShape("MyPresentation.pptx", 1, 2, null, "MyFolder");

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

        // Delete the second shape from the first slide.
        Shapes remainingShapes = slidesApi.deleteShape("MyPresentation.pptx", 1, 2, null, "MyFolder", null, null);

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

// Delete the second shape from the first slide.
$remainingShapes = $slidesApi->deleteShape("MyPresentation.pptx", 1, 2, null, "MyFolder");

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

# Delete the second shape from the first slide.
remaining_shapes = slides_api.delete_shape("MyPresentation.pptx", 1, 2, nil, "MyFolder")

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

# Delete the second shape from the first slide.
remaining_shapes = slides_api.delete_shape("MyPresentation.pptx", 1, 2, None, "MyFolder")

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

// Delete the second shape from the first slide.
slidesApi.deleteShape("MyPresentation.pptx", 1, 2, null, "MyFolder").then((remainingShapes) => {
    // Print resource references for the remaining shapes.
    remainingShapes.body.shapesLinks.forEach(shape =>
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
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Delete the second shape from the first slide.
    auto remainingShapes = slidesApi->deleteShape(L"MyPresentation.pptx", 1, 2, L"", L"MyFolder").get();

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

# Delete the second shape from the first slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, shape_index => 2, folder => "MyFolder");
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
|/slides/{name}/slides/{slideIndex}/shapes|DELETE|Deletes shapes from a presentation slide.|[DeleteShapes](https://apireference.aspose.cloud/slides/#/Shapes/DeleteShapes)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide contaning the shapes.|
|shapes|string|query|false|The 1-based indices of the shapes to delete. Delete all by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

**MyFolder/MyPresentation.pptx** document contains **three** shapes on the **first** slide. Delete the **first** and **third** shapes.

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
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?shapes=1,3&folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "shapesLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1?folder=MyFolder",
            "relation": "self",
            "slideIndex": 1
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1
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

        // Delete the first and third shapes from the first slide.
        var shapeIndices = new List<int> { 1, 3 };
        var remainingShapes = slidesApi.DeleteShapes("MyPresentation.pptx", 1, shapeIndices, null, "MyFolder");

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

        // Delete the first and third shapes from the first slide.
        ArrayList shapeIndices = new ArrayList(Arrays.asList( 1, 3 ));
        Shapes remainingShapes = slidesApi.deleteShapes("MyPresentation.pptx", 1, shapeIndices, null, "MyFolder", null);

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

// Delete the first and third shapes from the first slide.
$remainingShapes = $slidesApi->deleteShapes("MyPresentation.pptx", 1, [1, 3], null, "MyFolder");

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

# Delete the first and third shapes from the first slide.
remaining_shapes = slides_api.delete_shapes("MyPresentation.pptx", 1, [1, 3], nil, "MyFolder")

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

# Delete the first and third shapes from the first slide.
remaining_shapes = slides_api.delete_shapes("MyPresentation.pptx", 1, [1, 3], None, "MyFolder")

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

// Delete the first and third shapes from the first slide.
slidesApi.deleteShapes("MyPresentation.pptx", 1, [1, 3], null, "MyFolder").then((remainingShapes) => {
    // Print resource references for the remaining shapes.
    remainingShapes.body.shapesLinks.forEach(shape =>
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
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Delete the first and third shapes from the first slide.
    auto remainingShapes = slidesApi->deleteShapes(L"MyPresentation.pptx", 1, { 1, 3 }, L"", L"MyFolder").get();

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

# Delete the first and third shapes from the first slide.
my @shape_indices = (1, 3);
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, shapes => \@shape_indices, folder => "MyFolder");
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

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
