---
title: "Get API Information"
type: docs
url: /get-api-information/
weight: 5
---

## **Introduction**

The following method allows you to get information about the Aspose.Slides Cloud API.

## **GetApiInfo**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/info|GET|Returns information about the API.|[GetApiInfo](https://reference.aspose.cloud/slides/#/General/GetApiInfo)|

**Request Parameters**

No parameters.

### **Examples**

Get the **name** and **version** of the API.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get the Information**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/info" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "name": "Aspose.Slides for Cloud",
  "version": "23.12.0"
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var apiInfo = slidesApi.GetApiInfo();
        Console.WriteLine(apiInfo.Name + " " + apiInfo.Version);
    }
}

// Example output:
// Aspose.Slides for Cloud 23.12.0
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ApiInfo;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        ApiInfo apiInfo = slidesApi.getApiInfo();
        System.out.println(apiInfo.getName() + " " + apiInfo.getVersion());
    }
}

// Example output:
// Aspose.Slides for Cloud 23.12.0
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$apiInfo = $slidesApi->getApiInfo();
echo $apiInfo->getName(),  " ", $apiInfo->getVersion();

// Example output:
// Aspose.Slides for Cloud 23.12.0
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

api_info = slides_api.get_api_info()
print api_info.name, " ", api_info.version

# Example output:
# Aspose.Slides for Cloud 23.12.0
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

api_info = slides_api.get_api_info()
print(api_info.name, api_info.version)

# Example output:
# Aspose.Slides for Cloud 23.12.0
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

slidesApi.getApiInfo().then(apiInfo => {
    console.log(apiInfo.body.name, apiInfo.body.version);
});

// Example output:
// Aspose.Slides for Cloud 23.12.0
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto apiInfo = slidesApi->getApiInfo().get();
    std::wcout << apiInfo->getName() << " " << apiInfo->getVersion();
}

// Example output:
// Aspose.Slides for Cloud 23.12.0
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $api_info = $slides_api->get_api_info();
print($api_info->{name} . " " . $api_info->{version});

# Example output:
# Aspose.Slides for Cloud 23.12.0
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
