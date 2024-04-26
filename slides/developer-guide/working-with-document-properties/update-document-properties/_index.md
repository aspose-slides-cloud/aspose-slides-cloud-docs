---
title: "Update Document Properties"
keywords: "PowerPoint, presentation, REST API, Cloud API, document properties, update a document property"
type: docs
url: /update-document-properties/
weight: 30
---

## **Introduction**

Aspose.Slides allows you to update a document property in a PowerPoint presentation.

{{% alert color="primary" %}}

Please note that you cannot set values against the **Application** and **Producer** fields, because Aspose Ltd. and Aspose.Slides for Cloud x.x.x will be displayed against these fields.

{{% /alert %}}

## **SetDocumentProperty**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties/{propertyName}|PUT|Updates a document property or creates a new one if it does not exist.|[SetDocumentProperty](https://apireference.aspose.cloud/slides/#/Properties/SetDocumentProperty)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|propertyName|string|path|true|The name of a document property.|
|property|object|body|true|The property data to be updated.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Set the value **H.G. Wells** to a document property named **Author** in **MyFolder/MyPresentation.pptx** document saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Update the Document Property**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentproperties/Author?folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -d @request_data.json
```

request_data.json content:

```json
{
  "Name": "Author",
  "Value": "H.G. Wells"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "name": "Author",
    "value": "H.G. Wells",
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

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System.Diagnostics;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Create the document property.
        var property = new DocumentProperty { Name = "Author", Value = "H.G. Wells" };

        // Update the property in the presentation.
        var currentProperty = slidesApi.SetDocumentProperty("MyPresentation.pptx", "Author", property, null, "MyFolder");

        // Print data of the document property.
        Debug.WriteLine($"{currentProperty.Name}: {currentProperty.Value}");
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

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Create the document property.
        DocumentProperty property = new DocumentProperty();
        property.setName("Author");
        property.setValue("H.G. Wells");

        // Update the property in the presentation.
        DocumentProperty currentProperty = slidesApi.setDocumentProperty("MyPresentation.pptx", "Author", property, null, "MyFolder", null);

        // Print data of the document property.
        System.out.printf("%s: %s%n", currentProperty.getName(), currentProperty.getValue());
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

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Create the document property.
$property = new DocumentProperty();
$property->setName("Author");
$property->setValue("H.G. Wells");

// Update the property in the presentation.
$currentProperty = $slidesApi->setDocumentProperty("MyPresentation.pptx", "Author", $property, null, "MyFolder");

// Print data of the document property.
echo sprintf("%s: %s\n", $currentProperty->getName(), $currentProperty->getValue());
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

# Create the document property.
property = DocumentProperty.new
property.name = "Author"
property.value = "H.G. Wells"

# Update the property in the presentation.
current_property = slides_api.set_document_property("MyPresentation.pptx", "Author", property, nil, "MyFolder")

# Print data of the document property.
print "#{current_property.name}: #{current_property.value}"
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.document_property import DocumentProperty

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Create the document property.
property = DocumentProperty()
property.name = "Author"
property.value = "H.G. Wells"

# Update the property in the presentation.
current_property = slides_api.set_document_property("MyPresentation.pptx", "Author", property, None, "MyFolder")

# Print data of the document property.
print(f"{current_property.name}: {current_property.value}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Create the document property.
var property = new cloud.DocumentProperty();
property.name = "Author";
property.value = "H.G. Wells";

// Update the property in the presentation.
slidesApi.setDocumentProperty("MyPresentation.pptx", "Author", property, null, "MyFolder").then(currentProperty => {
    // Print data of the document property.
    console.log(currentProperty.body.name + ": " + currentProperty.body.value);
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

    // Create the document property.
    auto property = std::make_shared<DocumentProperty>();
    property->setName(L"Author");
    property->setValue(L"H.G. Wells");

    // Update the property in the presentation.
    auto currentProperty = slidesApi->setDocumentProperty(L"MyPresentation.pptx", L"Author", property, L"", L"MyFolder").get();

    // Print data of the document property.
    std::wcout << currentProperty->getName() << L": " << currentProperty->getValue();

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

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Create the document property.
my $property = AsposeSlidesCloud::Object::DocumentProperty->new();
$property->{name} = "Author";
$property->{value} = "H.G. Wells";

# Update the property in the presentation.
my %parameters = (name => "MyPresentation.pptx", property_name => "Author", property => $property, folder => "MyFolder");
my $current_property = $slides_api->set_document_property(%parameters);

# Print data of the document property.
print("$current_property->{name}: $current_property->{value}\n");
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
