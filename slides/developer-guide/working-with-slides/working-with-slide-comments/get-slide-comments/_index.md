---
title: "Get Slide Comments"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- slide
- comment
- slide comments
- author
- get comments
type: docs
url: /get-slide-comments/
weight: 10
---

## **Introduction**

In Microsoft PowerPoint, comments on slides serve as a convenient way to exchange ideas, feedback, and remarks among presentation participants. You can use the following method to retrieve comments from a presentation slide. 

## **GetSlideComments**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/comments|GET|Retrieves slide comments from a presentation saved in a storage.|[GetSlideComments](https://apireference.aspose.cloud/slides/#/Comments/GetSlideComments)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

Get the number of comments on the **first** slide in the **MyPresentation.pptx** document saved in the **default** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get the Slide Comments**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/comments" \
     -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "list": [
    {
      "type": "Regular",
      "author": "John Smith",
      "text": "This is the first comment.",
      "createdTime": "2024-03-01T13:35:39.761Z"
    },
    {
      "type": "Regular",
      "author": "John Smith",
      "text": "This is the second comment.",
      "createdTime": "2024-03-01T13:36:01.438Z"
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/comments",
    "relation": "self",
    "slideIndex": 1
  }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string fileName = "MyPresentation.pptx";
        int slideIndex = 1;

        SlideComments slideComments = slidesApi.GetSlideComments(fileName, slideIndex);

        int commentCount = slideComments.List.Count;
        Console.WriteLine($"The slide has {commentCount} comments.");
    }
}

// The output example:
//
// The slide has 2 comments.
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SlideComments;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;

        SlideComments slideComments = slidesApi.getSlideComments(fileName, slideIndex, null, null, null);

        int commentCount = slideComments.getList().size();
        System.out.println("The slide has " + commentCount + " comments.");
    }
}

// The output example:
//
// The slide has 2 comments.
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

$fileName = "MyPresentation.pptx";
$slideIndex = 1;

$slideComments = $slidesApi->getSlideComments($fileName, $slideIndex);

$commentCount = count($slideComments->getList());
echo "The slide has ", $commentCount, " comments.";

// The output example:
//
// The slide has 2 comments.
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

file_name = "MyPresentation.pptx"
slide_index = 1

slide_comments = slides_api.get_slide_comments(file_name, slide_index)

comment_count = slide_comments.list.length()
print "The slide has ", comment_count, " comments."

# The output example:
#
# The slide has 2 comments.
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1

slide_comments = slides_api.get_slide_comments(file_name, slide_index)

comment_count = len(slide_comments.list)
print("The slide has", comment_count, "comments.")

# The output example:
#
# The slide has 2 comments.
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;

slidesApi.getSlideComments(fileName, slideIndex).then(slideComments => {
    commentCount = slideComments.body.list.length;
    console.log("The slide has", commentCount, "comments.");
});

// The output example:
//
// The slide has 2 comments.
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;

    std::shared_ptr<SlideComments> slideComments = slidesApi->getSlideComments(fileName, slideIndex).get();

    int commentCount = slideComments->getList().size();
    std::wcout << L"The slide has " << commentCount << L" comments.";
}

// The output example:
//
// The slide has 2 comments.
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;

my $slide_comments = $slides_api->get_slide_comments(name => $file_name, slide_index => $slide_index);

my $comment_count = @{$slide_comments->{list}};
print("The slide has ", $comment_count, " comments.");

# The output example:
#
# The slide has 2 comments.
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"

api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
slideIndex := 1

comments, _, e := api.SlidesApi.GetSlideComments(fileName, slideIndex, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

commentCount := len(comments.(asposeslidescloud.ISlideComments).GetList())
fmt.Printf("The slide has %v comments", commentCount)

// The output example:
//
// The slide has 2 comments.
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
