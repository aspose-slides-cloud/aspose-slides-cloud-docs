---
title: "Get Caption Tracks for a Video Frame"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- video frame
- caption tracks
type: docs
url: /get-video-caption-tracks/
weight: 10
---

## **Introduction**

The following API method allows you to get information about caption tracks of a video frame. You can choose whether to retrieve the caption contents or just their IDs and titles.

## **GetVideoCaptionTracks**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/captionTracks|GET|Returns caption tracks of a video frame.|[GetVideoCaptionTracks](https://apireference.aspose.cloud/slides/#/Shapes/GetVideoCaptionTracks)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape; must refer to a video frame.|
|includeData|boolean|query|false|True to include captions contents (DataAsString property) in the response.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage containing the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Get information about caption tracks for a video frame, which is the 1st shape on the 3rd slide in **MyFolder/MyPresentation.pptx** file saved to the default storage.
The response will not contain captions data because the `includeData` property is not set to true.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Read Caption Tracks Information**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/3/shapes/1/captionTracks?folder=MyFolder" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "items": [
        {
            "captionId": "ac2a3180-07f9-4323-955f-36d9f585c612",
            "label": "Caption1"
        }
    ]
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
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");
        CaptionTracks captions = slidesApi.GetVideoCaptionTracks("MyPresentation.pptx", 3, 1, null, "MyFolder");
        foreach (CaptionTrack caption in captions.Items)
        {
            Debug.WriteLine($"Label: {caption.Label}");
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
        CaptionTracks captions = slidesApi.getVideoCaptionTracks("MyPresentation.pptx", 3, 1, null, "MyFolder", null);
        for (CaptionTrack caption : captions.getItems()) {
            System.out.printf("Label: %s\n", caption.getLabel());
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
$captions = $slidesApi->getVideoCaptionTracks("MyPresentation.pptx", 3, 1, null, "MyFolder");
foreach ($captions->getItems() as $caption) {
    echo sprintf("Label: %s\n", $caption->getLabel());
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
captions = slides_api.get_video_caption_tracks("MyPresentation.pptx", 3, 1, nil, "MyFolder")
for caption in captions.items
    puts "Label: #{caption.label}"
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Read information about all images.
captions = slides_api.get_video_caption_tracks("MyPresentation.pptx", 3, 1, None, "MyFolder")

# Print information about the images.
for caption in captions.items:
    print(f"Label: {caption.label}")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

slidesApi.getVideoCaptionTracks("MyPresentation.pptx", 3, 1, null, "MyFolder").then(captions => {
    captions.body.list.forEach(caption => {
        console.log("Label: " + caption.label);
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

    auto captions = slidesApi->getVideoCaptionTracks(L"MyPresentation.pptx", 3, 1, boost::none, L"", L"MyFolder").get();
    for (auto caption : captions->getItems()) {
        std::wcout << "Label: " << caption->getLabel() << std::endl;
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

my %parameters = (name => "MyPresentation.pptx", slideIndex => 3, shapeIndex => 1, folder => "MyFolder");
my $captions = $slides_api->get_video_caption_tracks(%parameters);

for my $caption (@{$captions->{items}}) {
    print("Label: $caption->{label}\n");
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
