---
title: "Deleting Properties from a PowerPoint Presentation"
type: docs
url: /deleting-properties-from-a-powerpoint-presentation/
weight: 40
---

## **Introduction**

This article shows you how to delete document properties from a PowerPoint presentation. The request methods described below can be used for deleting one or all properties at once.

{{% alert color="primary" %}}

Please note that you cannot delete standard properties, such as Author, Title, Company, etc. Attempting to delete these properties only deletes their values. Some automatically updated properties and their values cannot also to be deleted either, such as CreatedTime, LastSavedTime, etc. Custom properties are deleted completely.

{{% /alert %}}

## **DeleteDocumentProperties**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties|DELETE|Deletes all document properties from a presentation.|[DeleteDocumentProperties](https://apireference.aspose.cloud/slides/#/Properties/DeleteDocumentProperties)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete all document properties from **MyFolder/MyPresentation.pptx** document saved to the default storage. Use **MyPassword** string to open the presentation.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete Document Properties**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentproperties?folder=MyFolder" \
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
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Author?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Category",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Category?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Comments",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Comments?folder=MyFolder",
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
            "name": "Keywords",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Keywords?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "LastSavedBy",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/LastSavedBy?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Manager",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Manager?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "NameOfApplication",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/NameOfApplication?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "RevisionNumber",
            "value": "1",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/RevisionNumber?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Subject",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Subject?folder=MyFolder",
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
        },
        {
            "name": "Title",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Title?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "TotalEditingTime",
            "value": "PT0S",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/TotalEditingTime?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "CreatedTime",
            "value": "2022-07-15T13:57:12.1753779Z",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/CreatedTime?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "LastPrinted",
            "value": "2022-07-15T13:57:12.1753791Z",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/LastPrinted?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "LastSavedTime",
            "value": "2022-07-15T13:57:12.1753791Z",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/LastSavedTime?folder=MyFolder",
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

        // Delete all document properties.
        var currentProperties = slidesApi.DeleteDocumentProperties("MyPresentation.pptx", "MyPassword", "MyFolder");

        // Print the current document properties.
        foreach (var property in currentProperties.List)
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

        // Delete all document properties.
        DocumentProperties currentProperties = slidesApi.deleteDocumentProperties("MyPresentation.pptx", "MyPassword", "MyFolder", null);

        // Print the current document properties.
        for (DocumentProperty property : currentProperties.getList()) {
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

// Delete all document properties.
$currentProperties = $slidesApi->deleteDocumentProperties("MyPresentation.pptx", "MyPassword", "MyFolder");

// Print the current document properties.
foreach ($currentProperties->getList() as $property) {
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

# Delete all document properties.
current_properties = slides_api.delete_document_properties("MyPresentation.pptx", "MyPassword", "MyFolder")

# Print the current document properties.
for property in current_properties.list
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

# Delete all document properties.
current_properties = slides_api.delete_document_properties("MyPresentation.pptx", "MyPassword", "MyFolder")

# Print the current document properties.
for property in current_properties.list:
    print(f"{property.name}: {property.value}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Delete all document properties.
slidesApi.deleteDocumentProperties("MyPresentation.pptx", "MyPassword", "MyFolder").then((currentProperties) => {
    // Print the current document properties.
    currentProperties.body.list.forEach(property =>
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

    // Delete all document properties.
    auto currentProperties = slidesApi->deleteDocumentProperties(L"MyPresentation.pptx", L"MyPassword", L"MyFolder").get();

    // Print the current document properties.
    for (auto property : currentProperties->getList()) {
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

# Delete all document properties.
my %parameters = (name => "MyPresentation.pptx", password => "MyPassword", folder => "MyFolder");
my $current_properties = $slides_api->delete_document_properties(%parameters);

# Print the current document properties.
for my $property (@{$current_properties->{list}}) {
    print("$property->{name}: $property->{value}\n");
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **DeleteDocumentProperty**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties/{propertyName}|DELETE|Deletes a document property from a presentation.|[DeleteDocumentProperty](https://apireference.aspose.cloud/slides/#/Properties/DeleteDocumentProperty)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|propertyName|string|path|true|The name of a document property to be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete the custom document property named **MyProperty** from **MyFolder/MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Property**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentproperties/MyProperty?folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
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
            "name": "Category",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Category?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Comments",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Comments?folder=MyFolder",
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
            "name": "Keywords",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Keywords?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "LastSavedBy",
            "value": "Jhon Smith",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/LastSavedBy?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Manager",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Manager?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "NameOfApplication",
            "value": "Microsoft Office PowerPoint",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/NameOfApplication?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "RevisionNumber",
            "value": "2",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/RevisionNumber?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "Subject",
            "value": "",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Subject?folder=MyFolder",
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
        },
        {
            "name": "Title",
            "value": "My Title",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/Title?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "TotalEditingTime",
            "value": "PT3M",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/TotalEditingTime?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "CreatedTime",
            "value": "2022-07-15T13:29:06Z",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/CreatedTime?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "LastPrinted",
            "value": "0001-01-01T00:00:00Z",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/LastPrinted?folder=MyFolder",
                "relation": "self"
            }
        },
        {
            "name": "LastSavedTime",
            "value": "2022-07-15T16:46:30Z",
            "builtIn": true,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties/LastSavedTime?folder=MyFolder",
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

        // Delete the document property.
        var currentProperties = slidesApi.DeleteDocumentProperty("MyPresentation.pptx", "MyProperty", null, "MyFolder");

        // Print the current document properties.
        foreach (var property in currentProperties.List)
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

        // Delete the document property.
        DocumentProperties currentProperties = slidesApi.deleteDocumentProperty("MyPresentation.pptx", "MyProperty", null, "MyFolder", null);

        // Print the current document properties.
        for (DocumentProperty property : currentProperties.getList()) {
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

// Delete the document property.
$currentProperties = $slidesApi->deleteDocumentProperty("MyPresentation.pptx", "MyProperty", null, "MyFolder");

// Print the current document properties.
foreach ($currentProperties->getList() as $property) {
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

# Delete the document property.
current_properties = slides_api.delete_document_property("MyPresentation.pptx", "MyProperty", nil, "MyFolder")

# Print the current document properties.
for property in current_properties.list
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

# Delete the document property.
current_properties = slides_api.delete_document_property("MyPresentation.pptx", "MyProperty", None, "MyFolder")

# Print the current document properties.
for property in current_properties.list:
    print(f"{property.name}: {property.value}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Delete the document property.
slidesApi.deleteDocumentProperty("MyPresentation.pptx", "MyProperty", null, "MyFolder").then((currentProperties) => {
    // Print the current document properties.
    currentProperties.body.list.forEach(property =>
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

    // Delete the document property.
    auto currentProperties = slidesApi->deleteDocumentProperty(L"MyPresentation.pptx", L"MyProperty", L"", L"MyFolder").get();

    // Print the current document properties.
    for (auto property : currentProperties->getList()) {
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

# Delete the document property.
my %parameters = (name => "MyPresentation.pptx", property_name => "MyProperty", folder => "MyFolder");
my $current_properties = $slides_api->delete_document_property(%parameters);

# Print the current document properties.
for my $property (@{$current_properties->{list}}) {
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
