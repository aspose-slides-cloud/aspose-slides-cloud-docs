---
title: "Extract an Image in a Specified Format from a Presentation"
type: docs
url: /extract-an-image-in-a-specified-format-from-a-presentation/
weight: 40
---

## **Introduction**

The following API method allows you to easily retrieve an image in a specified format from a PowerPoint document. In order to get image information from a PowerPoint presentation please refer to [this](/slides/get-image-information-from-a-presentation/) article.

## **DownloadImage**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/images/{index}/{format}|GET|Retrieves an image in a specified format by index from a PowerPoint document.|[DownloadImage](https://apireference.aspose.cloud/slides/#/Images/DownloadImage)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|index|integer|path|true|The 1-based index of the image to be retrieved.|
|format|string|path|true|The format of the image to be retrieved.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Retrieve the **second** image in GIF format from **MyFolder/MyPresentation.pptx** document saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Retrieve the Image**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/2/Gif?folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

Image file

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System.IO;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");
        
        // Retrieve the second image in GIF format.
        using var imageStream = slidesApi.DownloadImage("MyPresentation.pptx", 2, ImageExportFormat.Gif, null, "MyFolder");

        // Save the image to a file.
        using var fileStream = File.OpenWrite("SecondImage.gif");
        imageStream.CopyTo(fileStream);
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

        // Retrieve the second image in GIF format.
        File imageFile = slidesApi.downloadImage("MyPresentation.pptx", 2, ImageExportFormat.GIF, null, "MyFolder", null);

        System.out.println("The second image was saved to " + imageFile.getPath());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ImageExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Retrieve the second image in GIF format.
$imageFile = $slidesApi->downloadImage("MyPresentation.pptx", 2, ImageExportFormat::GIF, null, "MyFolder");

echo "The second image was saved to ", $imageFile->getRealPath();
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

# Retrieve the second image in GIF format.
image_data = slides_api.download_image("MyPresentation.pptx", 2, ImageExportFormat::GIF, nil, "MyFolder")

# Save the image to a file.
File.binwrite("SecondImage.gif", image_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.image_export_format import ImageExportFormat

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Retrieve the second image in GIF format.
image_path = slides_api.download_image("MyPresentation.pptx", 2, ImageExportFormat.GIF, None, "MyFolder")

print("The second image was saved to " + image_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Retrieve the second image in GIF format.
slidesApi.downloadImage("MyPresentation.pptx", 2, "gif", null, "MyFolder").then((response) => {
    // Save the image to a file.
    fs.writeFile("SecondImage.gif", response.body, (error) => {
        if (error) throw error
    })
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

    // Retrieve the second image in GIF format.
    auto responseContent = slidesApi->downloadImage(L"MyPresentation.pptx", 2, L"gif", L"", L"MyFolder").get();

    // Save the image to a file.
    std::ofstream fileStream("SecondImage.gif", std::ofstream::binary);
    responseContent.writeTo(fileStream);

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

use File::Slurp;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Retrieve the second image in GIF format.
my %parameters = (name => "MyPresentation.pptx", index => 2, format => "gif", folder => "MyFolder");
my $image_data = $slides_api->download_image(%parameters);

# Save the image to a file.
write_file("SecondImage.gif", {binmode => ":raw"}, $image_data);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
