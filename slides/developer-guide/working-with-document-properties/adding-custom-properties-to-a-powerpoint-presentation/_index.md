---
title: "Adding Custom Properties to a PowerPoint Presentation"
type: docs
url: /adding-custom-properties-to-a-powerpoint-presentation/
weight: 20
---

## **Introduction**

Aspose.Slides Cloud allows you to add document properties to a PowerPoint presentation. Document properties, also known as metadata, are details about a file that describe or identify it. They include details such as title, author name, subject, and keywords that identify the document's topic or contents. This article shows you how to add one or more custom document properties.

## **SetDocumentProperties**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties|POST|Adds a custom document property to a presentation.|[SetDocumentProperties](https://apireference.aspose.cloud/slides/#/Properties/SetDocumentProperties)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|properties|object|body|true|The list of new document properties to be added to the presentation.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Add the following custom properties to **MyFolder/MyPresentation.pptx** document saved to the default storage:
|**Name**|**Value**|
| :- | :- |
|ProcessedByOffice|Scotland Team|
|MyProperty|My Value|

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the Custom Properties**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentproperties?folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -d @request_data.json
```

request_data.json content:

```json
{
    "List": [
        {
            "Name": "ProcessedByOffice", 
            "Value": "Scotland Team"
        },
        {
            "Name": "MyProperty", 
            "Value": "My Value"
        }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "list": [
        {
            "name": "Author",
            "value": "Jhon Smith",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Author?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Company",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Company?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "CreatedTime",
            "value": "2022-07-13T14:01:41Z",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/CreatedTime?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "MyProperty",
            "value": "My Value",
            "builtIn": false,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/MyProperty?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "ProcessedByOffice",
            "value": "Scotland Team",
            "builtIn": false,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/ProcessedByOffice?folder=MyFolder",
                "relation": "self"
            }
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties?folder=MyFolder",
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
using Aspose.Slides.Cloud.Sdk.Model;
using System.Collections.Generic;
using System.Diagnostics;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Create the new document properties.
        var property1 = new DocumentProperty { Name = "ProcessedByOffice", Value = "Scotland Team" };
        var property2 = new DocumentProperty { Name = "MyProperty", Value = "My Value" };

        // Prepare a collection of the properties.
        var newProperties = new DocumentProperties();
        newProperties.List = new List<DocumentProperty>();
        newProperties.List.Add(property1);
        newProperties.List.Add(property2);

        // Add the new document properties to the presentation.
        var allProperties = slidesApi.SetDocumentProperties("MyPresentation.pptx", newProperties, null, "MyFolder");

        // Print all document properties.
        foreach (var property in allProperties.List)
        {
            Debug.WriteLine($"{property.Name}: {property.Value}");
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
import com.aspose.slides.model.*;

import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Create the new document properties.
        DocumentProperty property1 = new DocumentProperty();
        property1.setName("ProcessedByOffice");
        property1.setValue("Scotland Team");
        DocumentProperty property2 = new DocumentProperty();
        property2.setName("MyProperty");
        property2.setValue("My Value");

        // Prepare a collection of the properties.
        DocumentProperties newProperties = new DocumentProperties();
        newProperties.setList(Arrays.asList(property1, property2));

        // Add the new document properties to the presentation.
        DocumentProperties allProperties = slidesApi.setDocumentProperties("MyPresentation.pptx", newProperties, null, "MyFolder", null);

        // Print all document properties.
        for (DocumentProperty property : allProperties.getList()) {
            System.out.printf("%s: %s%n", property.getName(), property.getValue());
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
use Aspose\Slides\Cloud\Sdk\Model\DocumentProperty;
use Aspose\Slides\Cloud\Sdk\Model\DocumentProperties;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Create the new document properties.
$property1 = new DocumentProperty();
$property1->setName("ProcessedByOffice");
$property1->setValue("Scotland Team");
$property2 = new DocumentProperty();
$property2->setName("MyProperty");
$property2->setValue("My Value");

// Prepare a collection of the properties.
$newProperties = new DocumentProperties();
$newProperties->setList([$property1, $property2]);

// Add the new document properties to the presentation.
$allProperties = $slidesApi->setDocumentProperties("MyPresentation.pptx", $newProperties, null, "MyFolder");

// Print all document properties.
foreach ($allProperties->getList() as $property) {
    echo sprintf("%s: %s\n", $property->getName(), $property->getValue());
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

# Create the new document properties.
property1 = DocumentProperty.new
property1.name = "ProcessedByOffice"
property1.value = "Scotland Team"
property2 = DocumentProperty.new
property2.name = "MyProperty"
property2.value = "My Value"

# Prepare a collection of the properties.
new_properties = DocumentProperties.new
new_properties.list = [property1, property2]

# Add the new document properties to the presentation.
all_properties = slides_api.set_document_properties("MyPresentation.pptx", new_properties, nil, "MyFolder")

# Print all document properties.
for property in all_properties.list
    puts "#{property.name}: #{property.value}"
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models import *

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Create the new document properties.
property1 = DocumentProperty()
property1.name = "ProcessedByOffice"
property1.value = "Scotland Team"
property2 = DocumentProperty()
property2.name = "MyProperty"
property2.value = "My Value"

# Prepare a collection of the properties.
new_properties = DocumentProperties()
new_properties.list = [property1, property2]

# Add the new document properties to the presentation.
all_properties = slides_api.set_document_properties("MyPresentation.pptx", new_properties, None, "MyFolder")

# Print all document properties.
for property in all_properties.list:
    print(f"{property.name}: {property.value}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Create the new document properties.
const property1 = new cloud.DocumentProperty()
property1.name = "ProcessedByOffice"
property1.value = "Scotland Team"
const property2 = new cloud.DocumentProperty()
property2.name = "MyProperty"
property2.value = "My Value"

// Prepare a collection of the properties.
const newProperties = new cloud.DocumentProperties()
newProperties.list = [property1, property2]

// Add the new document properties to the presentation.
slidesApi.setDocumentProperties("MyPresentation.pptx", newProperties, null, "MyFolder").then((allProperties) => {
    // Print all document properties.
    allProperties.body.list.forEach(property =>
        console.log(property.name + ": " + property.value)
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

    // Create the new document properties.
    auto property1 = std::make_shared<DocumentProperty>();
    property1->setName(L"ProcessedByOffice");
    property1->setValue(L"Scotland Team");
    auto property2 = std::make_shared<DocumentProperty>();
    property2->setName(L"MyProperty");
    property2->setValue(L"My Value");

    // Prepare a collection of the properties.
    auto newProperties = std::make_shared<DocumentProperties>();
    newProperties->setList({ property1, property2 });

    // Add the new document properties to the presentation.
    auto allProperties = slidesApi->setDocumentProperties(L"MyPresentation.pptx", newProperties, L"", L"MyFolder").get();

    // Print all document properties.
    for (auto property : allProperties->getList()) {
        std::wcout << property->getName() << L": " << property->getValue() << std::endl;
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
use AsposeSlidesCloud::Object::DocumentProperty;
use AsposeSlidesCloud::Object::DocumentProperties;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Create the new document properties.
my $property1 = AsposeSlidesCloud::Object::DocumentProperty->new();
$property1->{name} = "ProcessedByOffice";
$property1->{value} = "Scotland Team";
my $property2 = AsposeSlidesCloud::Object::DocumentProperty->new();
$property2->{name} = "MyProperty";
$property2->{value} = "My Value";

# Prepare a collection of the properties.
my $new_properties = AsposeSlidesCloud::Object::DocumentProperties->new();
$new_properties->{list} = [$property1, $property2];

# Add the new document properties to the presentation.
my %parameters = (name => "MyPresentation.pptx", properties => $new_properties, folder => "MyFolder");
my $all_properties = $slides_api->set_document_properties(%parameters);

# Print all document properties.
for my $property (@{$all_properties->{list}}) {
    print("$property->{name}: $property->{value}\n");
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
