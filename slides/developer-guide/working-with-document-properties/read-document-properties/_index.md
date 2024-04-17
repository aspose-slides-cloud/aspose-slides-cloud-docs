---
title: "Read Document Properties"
type: docs
url: /read-document-properties/
weight: 10
---

## **Introduction**

This article shows you how to read document properties from a PowerPoint presentation. The methods below allow you to read standard and custom properties. A document property is a name and value pair.

## **GetDocumentProperties**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties|GET|Reads all document properties from a presentation.|[GetDocumentProperties](https://apireference.aspose.cloud/slides/#/Properties/GetDocumentProperties)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read all document properties from **MyFolder/MyPresentation.pptx** document saved to the default storage. Use **MyPassword** string to open the protected presentation.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read Document Properties**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentproperties?folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "password: MyPassword"
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
            "value": "Aspose",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Company?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Template",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Template?folder=MyFolder",
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
using System.Diagnostics;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all document properties from the presentation.
        var properties = slidesApi.GetDocumentProperties("MyPresentation.pptx", "MyPassword", "MyFolder");

        // Print the document properties.
        foreach (var property in properties.List)
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get all document properties from the presentation.
        DocumentProperties properties = slidesApi.getDocumentProperties("MyPresentation.pptx", "MyPassword", "MyFolder", null);

        // Print the document properties.
        for (DocumentProperty property : properties.getList()) {
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

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Get all document properties from the presentation.
$properties = $slidesApi->getDocumentProperties("MyPresentation.pptx", "MyPassword", "MyFolder");

// Print the document properties.
foreach ($properties->getList() as $property) {
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

# Get all document properties from the presentation.
properties = slides_api.get_document_properties("MyPresentation.pptx", "MyPassword", "MyFolder")

# Print the document properties.
for property in properties.list
    puts "#{property.name}: #{property.value}"
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get all document properties from the presentation.
properties = slides_api.get_document_properties("MyPresentation.pptx", "MyPassword", "MyFolder")

# Print the document properties.
for property in properties.list:
    print(f"{property.name}: {property.value}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Get all document properties from the presentation.
slidesApi.getDocumentProperties("MyPresentation.pptx", "MyPassword", "MyFolder").then(properties => {
    // Print the document properties.
    properties.body.list.forEach(property => {
        console.log(property.name + ": " + property.value);
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

    // Get all document properties from the presentation.
    auto properties = slidesApi->getDocumentProperties(L"MyPresentation.pptx", L"MyPassword", L"MyFolder").get();

    // Print the document properties.
    for (auto property : properties->getList()) {
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

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Get all document properties from the presentation.
my %parameters = (name => "MyPresentation.pptx", password => "MyPassword", folder => "MyFolder");
my $properties = $slides_api->get_document_properties(%parameters);

# Print the document properties.
for my $property (@{$properties->{list}}) {
    print("$property->{name}: $property->{value}\n");
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **GetDocumentProperty**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties/{propertyName}|GET|Reads a document property from a presentation.|[GetDocumentProperty](https://apireference.aspose.cloud/slides/#/Properties/GetDocumentProperty)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|propertyName|string|path|true|The name of a document property.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Read the document property named **Author** from **MyFolder/MyPresentation.pptx** document saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read the Document Property**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentproperties/Author?folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "name": "Author",
    "value": "Jhon Smith",
    "builtIn": true,
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Author?folder=MyFolder",
        "relation": "self"
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

        // Read the document property.
        var property = slidesApi.GetDocumentProperty("MyPresentation.pptx", "Author", null, "MyFolder");

        // Print the property value.
        Debug.WriteLine(property.Value); // Jhon Smith, for example.
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

        // Read the document property.
        DocumentProperty property = slidesApi.getDocumentProperty("MyPresentation.pptx", "Author", null, "MyFolder", null);

        // Print the property value.
        System.out.println(property.getValue()); // Jhon Smith, for example.
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

// Read the document property.
$property = $slidesApi->getDocumentProperty("MyPresentation.pptx", "Author", null, "MyFolder");

// Print the property value.
print($property->getValue()); // Jhon Smith, for example.
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

# Read the document property.
property = slides_api.get_document_property("MyPresentation.pptx", "Author", nil, "MyFolder")

# Print the property value.
print property.value # Jhon Smith, for example.
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Read the document property.
property = slides_api.get_document_property("MyPresentation.pptx", "Author", None, "MyFolder")

# Print the property value.
print(property.value) # Jhon Smith, for example.
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Read the document property.
slidesApi.getDocumentProperty("MyPresentation.pptx", "Author", null, "MyFolder").then(property => {
    // Print the property value.
    console.log(property.body.value);
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

    // Read the document property.
    auto property = slidesApi->getDocumentProperty(L"MyPresentation.pptx", L"Author", L"", L"MyFolder").get();

    // Print the property value.
    std::wcout << property->getValue(); // Jhon Smith, for example.

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

# Read the document property.
%parameters = (name => "MyPresentation.pptx", property_name => "Author", folder => "MyFolder");
$property = $slides_api->get_document_property(%parameters);

# Print the property value.
print($property->{value}); # Jhon Smith, for example.
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
