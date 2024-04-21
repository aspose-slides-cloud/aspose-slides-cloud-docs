---
title: "Get Comment Authors"
keywords: "PowerPoint, presentation, REST API, Cloud API, slide, comment, author, get authors"
type: docs
url: /get-comment-authors/
weight: 50
---
## **Introduction**
The article shows how to retrieve authors of comments from a presentation.
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/comments/authors|GET|Read presentation slide comments|[GetCommentAuthors](https://apireference.aspose.cloud/slides/#/Comments/GetCommentAuthors)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```
```sh

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/comments/authors" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```
{{< /tab >}}

{{< tab tabNum="2" >}}

```json

{
    list: [
        { 'name': 'John Doe', 'initials': 'J.D.' },
        { 'name': 'Andrew Brooks' }
    ]
}

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
CommentAuthors authors = api.GetCommentAuthors("MyPresentation.pptx");
Console.WriteLine($"The presentation has {authors.List.Count} comment authors");
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
CommentAuthors authors = api.getCommentAuthors("MyPresentation.pptx", null, null, null);
System.out.println("The presentation has " + authors.getList().size() + " comment authors");
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

$authors = $api->GetCommentAuthors("MyPresentation.pptx");
print("The presentation has " . count($authors->getList()) . " comment authors");
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

authors = api.get_comment_authors("MyPresentation.pptx")
p("The presentation has #{ authors.list.length } comment authors")
```

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

authors = api.get_comment_authors("MyPresentation.pptx")
print("The presentation has " + str(len(authors.list)) + " comment authors")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
api.getCommentAuthors("MyPresentation.pptx").then(authors => {
    console.log("The presentation has " + authors.body.list.length + " authors");
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

authors, _, e := api.SlidesApi.GetCommentAuthors("MyPresentation.pptx", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The presentation has %v comment authors", len(authors.(asposeslidescloud.ICommentAuthors).GetList()))
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %params = ('name' => 'MyPresentation.pptx');
my $authors = $api->get_comment_authors(%params);
print "The presentation has " . (scalar @{$authors->{list}}) . " comment authors";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}