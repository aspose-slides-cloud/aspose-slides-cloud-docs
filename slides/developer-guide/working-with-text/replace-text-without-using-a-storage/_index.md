---
title: "Replace Text without Using a Storage"
keywords: "PowerPoint, presentation, REST API, Cloud API, text, replace text, change text, storage"
type: docs
url: /replace-text-without-using-a-storage/
weight: 90
---

## **Introduction**

You don't need to upload files to storage to perform text replacement. You can use online methods to read a presentation from a request body and return an updated one in a response body. As with storage methods, Aspose.Slides Cloud provides methods to replace text on a specified slide or in the presentation as a whole. With online methods, the result of the operation is the updated presentation. The number of replacements is not returned. You need to use storage methods if replacement count is essential information for you.

## **ReplacePresentationTextOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/replaceText|POST|Replaces text within a presentation.|[ReplacePresentationTextOnline](https://apireference.aspose.cloud/slides/#/Text/ReplacePresentationTextOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|oldValue|string|query|true|The text to be replaced.|
|newValue|string|query|true|The text to replace with.|
|ignoreCase|boolean|query|false|If `true`, the character case must be ignored. The default is `false`.|
|password|string|header|false|The password to open the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Replace the word **banana** with the word **orange** in the document **MyPresentation.pptx**. **Ignore the case** of text characters.

**cURL Solution**

{{% alert color="primary" %}} 

We are using the **/slides/replaceText** resource for the example. You can use the **/slides/slides/{slideIndex}/replaceText** with the same query parameters to replace all matching occurrences of the text items on a specific slide in a PowerPoint presentation.

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/replaceText?oldValue=banana&newValue=orange&ignoreCase=true" \
     -H "authorization: Bearer MyAccessToken" \
     -F "file=@MyPresentation.pptx" \
     -o UpdatedPresentation.pptx
```

{{< /tab >}}

{{< tab tabNum="2" >}}

The updated presentation file.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

using Stream documentStream = File.OpenRead("MyPresentation.pptx");
using Stream resultStream = api.ReplacePresentationTextOnline(documentStream, "banana", "orange", true);

using Stream outputStream = File.OpenWrite("UpdatedPresentation.pptx");
resultStream.CopyTo(outputStream);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

byte[] documentData = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
File resultFile = api.replacePresentationTextOnline(documentData, "banana", "orange", true, null);

System.out.println("The updated file was saved to " + resultFile.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$api = new SlidesApi(null, $config);

$documentStream = fopen("MyPresentation.pptx", "r");
$resultFile = $api->ReplacePresentationTextOnline($documentStream, "banana", "orange", true);

print("The updated file was saved to " . $resultFile->getPathname());
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

document_data = File.binread("MyPresentation.pptx")
result_data = slides_api.replace_presentation_text_online(document_data, "banana", "orange", true)

File.binwrite("UpdatedPresentation.pptx", result_data)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi(configuration)

with open("MyPresentation.pptx", "rb") as f:
    document_data = f.read()

result_file_path = api.replace_presentation_text_online(document_data, "banana", "orange", True)
print("The updated file was saved to " + result_file_path)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");
const fs = require("fs");

const api = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const documentStream = fs.createReadStream("MyPresentation.pptx");
api.replacePresentationTextOnline(documentStream, "banana", "orange", true).then(response => {
    fs.writeFile("UpdatedPresentation.pptx", response.body, (error) => {
        if (error) throw error;
    });
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

    auto documentStream = std::make_shared<std::ifstream>("MyPresentation.pptx", std::ios::binary);
    auto documentContent = std::make_shared<HttpContent>();
    documentContent->setData(documentStream);

    auto resultContent = slidesApi->replacePresentationTextOnline(documentContent, L"banana", L"orange", true).get();

    std::ofstream outputStream("UpdatedPresentation.pptx", std::ofstream::binary);
    resultContent.writeTo(outputStream);
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $document_data = read_file("MyPresentation.pptx", { binmode => ":raw" });

my %parameters = (document => $document_data, old_value => "banana", new_value => "orange", ignore_case => 1);
my $result_data = $slides_api->replace_presentation_text_online(%parameters);

write_file("UpdatedPresentation.pptx", {binmode => ":raw"}, $result_data);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"

api := asposeslidescloud.NewAPIClient(cfg)

source, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

var ignoreCase bool = true
result, _, e := api.SlidesApi.ReplacePresentationTextOnline(source, "banana", "orange", &ignoreCase, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("The updated file was saved to %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **ReplaceSlideTextOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/slides/{slideIndex}/replaceText|POST|Replaces text within a specified presentation slide.|[ReplaceSlideTextOnline](https://apireference.aspose.cloud/slides/#/Text/ReplaceSlideTextOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|oldValue|string|query|true|The text to be replaced.|
|newValue|string|query|true|The text to replace with.|
|ignoreCase|boolean|query|false|If `true`, the character case must be ignored. The default is `false`.|
|password|string|header|false|The password to open the presentation.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
