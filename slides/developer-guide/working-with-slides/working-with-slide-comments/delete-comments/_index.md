---
title: "Delete Comments"
type: docs
url: /delete-comments/
weight: 40
---

## **Introduction**

Comments in PowerPoint presentations are a tool that allows users to add explanations, notes, and discussions to each individual slide of a presentation. This functionality is valuable for collaborative work on a presentation, especially when multiple people are involved in the creation or editing process. The following API methods are for deleting comments from presentations.
 
You can delete all comments, or comments by a specific author. There is [a method]((/slides/get-comment-authors/) to retrieve the list of comment authors.

## **DeleteComments**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/comments|DELETE|Deletes comments from a presentation saved in a storage.|[DeleteComments](https://apireference.aspose.cloud/slides/#/Comments/DeleteComments)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of the presentation file saved in a storage.|
|author|string|query|false|The author of the comments. If the author is not specified, all comments will be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete comments from author **John Smith** in the document **MyPresentation.pptx**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Comments**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/comments?author=John%20Smith" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```text
Code: 200
Returns OK status.
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var documentName = "MyPresentation.pptx";
        var author = "John Smith";

        slidesApi.DeleteComments(documentName, author);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String documentName = "MyPresentation.pptx";
        String author = "John Smith";

        slidesApi.deleteComments(documentName, author, null, null, null);
    }
}
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

$documentName = "MyPresentation.pptx";
$author = "John Smith";

$slidesApi->deleteComments($documentName, $author);
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

document_name = "MyPresentation.pptx"
author = "John Smith"

slides_api.delete_comments(document_name, author)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

document_name = "MyPresentation.pptx"
author = "John Smith"

slides_api.delete_comments(document_name, author)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const documentName = "MyPresentation.pptx";
const author = "John Smith";

slidesApi.deleteComments(documentName, author).then(() => {
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto documentName = L"MyPresentation.pptx";
    auto author = L"John Smith";

    slidesApi->deleteComments(documentName, author).get();
}
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

my %parameters = (name => "MyPresentation.pptx", author => "John Smith");
$slides_api->delete_comments(%parameters);
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

_, e := api.SlidesApi.DeleteComments("MyPresentation.pptx", "John Smith", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
```

{{< /tab >}}

{{< /tabs >}}

## **DeleteCommentsOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/comments/delete|POST|Deletes comments from a presentation saved in a local file.|[DeleteCommentsOnline](https://reference.aspose.cloud/slides/#/Comments/DeleteCommentsOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|author|string|query|false|The author of the comments. If the author is not specified, all comments will be deleted.|
|password|string|header|false|The password to open the presentation.|

## **DeleteSlideComments**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/comments|DELETE|Deletes slide comments from a presentation saved in a storage.|[DeleteSlideComments](https://apireference.aspose.cloud/slides/#/Comments/DeleteSlideComments)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of the presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|author|string|query|false|The author of the comments. If the author is not specified, all comments will be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete comments from author **John Smith** on the **first** slide in the document **MyPresentation.pptx**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Comments**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/comments?author=John%20Smith" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```text
Code: 200
Returns OK status.
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="4" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var documentName = "MyPresentation.pptx";
        var slideIndex = 1;
        var author = "John Smith";

        slidesApi.DeleteSlideComments(documentName, slideIndex, author);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String documentName = "MyPresentation.pptx";
        int slideIndex = 1;
        String author = "John Smith";

        slidesApi.deleteSlideComments(documentName, slideIndex, author, null, null, null);
    }
}
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

$documentName = "MyPresentation.pptx";
$slideIndex = 1;
$author = "John Smith";

$slidesApi->deleteSlideComments($documentName, $slideIndex, $author);
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

document_name = "MyPresentation.pptx"
slide_index = 1
author = "John Smith"

slides_api.delete_slide_comments(document_name, slide_index, author)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

document_name = "MyPresentation.pptx"
slide_index = 1
author = "John Smith"

slides_api.delete_slide_comments(document_name, slide_index, author)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const documentName = "MyPresentation.pptx";
const slideIndex = 1;
const author = "John Smith";

slidesApi.deleteSlideComments(documentName, slideIndex, author).then(() => {
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto documentName = L"MyPresentation.pptx";
    auto slideIndex = 1;
    auto author = L"John Smith";

    slidesApi->deleteSlideComments(documentName, slideIndex, author).get();
}
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

my %parameters = (name => "MyPresentation.pptx", slide_index => 1, author => "John Smith");
$slides_api->delete_slide_comments(%parameters);
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

_, _, e := api.SlidesApi.DeleteSlideComments("MyPresentation.pptx", 1, "John Smith", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
```

{{< /tab >}}

{{< /tabs >}}

## **DeleteSlideCommentsOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/slides/{slideIndex}/comments/delete|POST|Deletes slide comments from a presentation saved in a local file.|[DeleteSlideCommentsOnline](https://reference.aspose.cloud/slides/#/Comments/DeleteSlideCommentsOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|author|string|query|false|The author of the comments. If the author is not specified, all comments will be deleted.|
|password|string|header|false|The password to open the presentation.|

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
