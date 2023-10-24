---
title: "Replace Text Not Using the Storage"
type: docs
url: /replace-text-not-using-the-storage/
weight: 90
---

## **Introduction**
You don't need to upload files to the Storage to perform text replacement. You can use online methods that read presentation from request body and return the updated presentation in response body. As with storage methods, Aspose.Slides Cloud provides you methods to replace text in a individual slide or a presentation as a whole. With online methods, the result of the operation is the updated presentation. The number of replacements is not returned. You need to use storage methods if replacement count is essential information for you.
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/replaceText|POST|Replace text within a presentation in request body|[ReplacePresentationTextOnline](https://apireference.aspose.cloud/slides/#/Text/ReplacePresentationTextOnline)|
|/slides/slides/{slideIndex}/replaceText|POST|Replace text within a individual slide in request body|[ReplaceSlideTextOnline](https://apireference.aspose.cloud/slides/#/Text/ReplaceSlideTextOnline)|
### **cURL Example**
{{% alert color="primary" %}} 

We are using the **/slides/replaceText** resource as an example below. You can use **/slides/slides/{slideIndex}/replaceText** with the same query parameters to replace all matching occurrences of the text items in a specific slide of a PowerPoint presentation.

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v "https://api.aspose.cloud/v3.0/slides/replaceText?oldValue=banana&newValue=orange&ignoreCase=true" -F "file1=@InputPresentation.pptx" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzA4ODMsImV4cCI6MTU2MDExNzI4MywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.bhURwSdcASMrRj4ukvG5rWTT_O2JpzVKH436ekU1CW6ZO7wOqGnE8wtkMdq6oivVzazs8xwbeuJmluFpHLNBco7A0vU56_UXZ5cIsfNCIpTOp6e_lmeHYgOD1rnW8f6y9jWLRoerup2vzqppjbF-8KXZ2HgCOXpos4lzy7GLqWmElW9TGd2uOd3cFEu1rXmkiJzuyjEi1dFdZtvRPvNyqon5R9ZS5rxQ09GhaiRA6DW4HwFTS-jTAPQo0QGfv87b4Gg_DvnUu_JjWlAhIeqWIM72-xmvFQ_20mk-s6H7foiyvJSC65w-XN5AqUyAyE8rAZduIwcS7BuYiQuOqqen4w" --ssl-no-revoke -o "UpdatedPresentation.pptx"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

The updated presentation.

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
using Stream file = File.OpenRead("InputPresentation.pptx");
using Stream result = api.ReplacePresentationTextOnline(file, "banana", "orange", true);
using Stream outFile = File.OpenWrite("UpdatedPresentation.pptx");
result.CopyTo(outFile);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
File response = api.replacePresentationTextOnline(file, "banana", "orange", true, null);
System.out.println("The updated file was saved to " + response.getPath());
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
$file = fopen("MyPresentation.pptx", 'r');
$result = $api->ReplacePresentationTextOnline($file, "banana", "orange", true);
print("The updated file was saved to " . $result->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

with open("MyPresentation.pptx", 'rb') as f:
    input_file = f.read()

result = api.replace_presentation_text_online(input_file, "banana", "orange", True)
print('The updated file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require('fs');
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
const file = fs.createReadStream("MyPresentation.pptx");
api.replacePresentationTextOnline(file, "banana", "orange", true).then((response) => {
    fs.writeFile("UpdatedPresentation.pptx", response.body, (err) => {
        if (err) throw err;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

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
result, _, e := c.SlidesApi.ReplacePresentationTextOnline(source, "banana", "orange", &ignoreCase, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The updated file was saved to %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
