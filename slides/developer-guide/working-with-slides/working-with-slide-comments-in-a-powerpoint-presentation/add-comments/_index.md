---
title: "Add Comments"
type: docs
url: /add-comments/
weight: 20
---
## **Introduction**
You can add comments using **CreateComment** method. The example below shows how to add a regular comment. You can also add a [modern comment](/slides/add-modern-comments/) using the same method.
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/comments|POST|Adds comment on the slide| [CreateComment](https://apireference.aspose.cloud/slides/#/Comments/CreateComment)|
### **cURL Example**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```
```sh

curl -v -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/comments" -d @"comments.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```
comments.json
```java
{
    "type": "regular",
    "text": "comment text",
    "author": "Author Name",
    "childComments":[
        {
            "type": "regular",
            "text": "child comment text",
            "author": "Author Name"
        }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns slide comments info.

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
SlideComment dto = new SlideComment()
{
    Text = "Comment text",
    Author = "Author Name",
    ChildComments = new List<SlideCommentBase>()
    {
        new SlideComment()
        {
            Text = "Child comment text",
            Author = "Author Name"
        }
    }
};

SlideComments response = api.CreateComment("MyPresentation.pptx", 3, dto);
Console.WriteLine($"The slide has {response.List.Count} comments");
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
SlideComment dto = new SlideComment();
dto.setText("Comment text");
dto.setAuthor("Author Name");
List<SlideCommentBase> childComments = new ArrayList<SlideCommentBase>();
SlideComment childComment = new SlideComment();
childComment.setText("Child comment text");
childComment.setAuthor("Author Name");
childComments.add(childComment);
dto.setChildComments(childComments);
SlideComments response = api.createComment("MyPresentation.pptx", 3, dto, null, null, null, null);
System.out.println("The slide has " + response.getList().size() + " comments");
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideComment;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new SlideComment();
$dto->setText("Comment text");
$dto->setAuthor("Author Name");
$childComment = new SlideComment();
$childComment->setText("Child comment text");
$childComment->setAuthor("Author Name");
$childComments = [ $childComment ];
$dto->setChildComments($childComments);
$response = $api->CreateComment("MyPresentation.pptx", 3, $dto);
print("The slide has " . count($response->getList()) . " comments");
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

dto = AsposeSlidesCloud::SlideComment.new()
dto.text = "Comment text"
dto.author = "Author Name"
child_comment = AsposeSlidesCloud::SlideComment.new()
child_comment.text = "Child comment text"
child_comment.author = "Author Name"
dto.child_comments = [ child_comment ]
response = api.create_comment("MyPresentation.pptx", 3, dto)
p("The slide has #{ response.list.length } comments")
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_comment import SlideComment

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = SlideComment()
dto.text = "Comment text"
dto.author = "Author Name"
child_comment = SlideComment()
child_comment.text = "Child comment text"
child_comment.author = "Author Name"
dto.child_comments = [ child_comment ]
response = api.create_comment("MyPresentation.pptx", 3, dto)
print("The slide has " + str(len(response.list)) + " comments")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
const dto = new CloudSdk.SlideComment();
dto.text = "Comment text";
dto.author = "Author Name";
const childComment = new CloudSdk.SlideComment();
childComment.text = "Child comment text";
childComment.author = "Author Name";
dto.childComments= [ childComment ];
api.createComment("MyPresentation.pptx", 3, dto).then((comments) => {
    console.log("The slide has " + comments.body.list.length + " comments");
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

dto := asposeslidescloud.NewSlideComment()
dto.Text = "Comment text"
dto.Author = "Author Name"
childComment := asposeslidescloud.NewSlideComment()
childComment.Text = "Child comment text"
childComment.Author = "Author Name"
childComments := []asposeslidescloud.ISlideCommentBase { childComment }
dto.ChildComments = childComments
comments, _, e := api.SlidesApi.CreateComment("MyPresentation.pptx", 3, dto, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The slide has %v comments", len(comments.GetList()))
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $dto = AsposeSlidesCloud::Object::SlideComment->new();
$dto->{text} = "Comment text";
$dto->{author} = "Author Name";
my $childComment = AsposeSlidesCloud::Object::SlideComment->new();
$childComment->{text} = "Child comment text";
$childComment->{author} = "Author Name";
my @childComments = ( $childComment );
$dto->{child_comments} = \@childComments;
my %params = ('name' => 'MyPresentation.pptx', 'slide_index' => 3, 'dto' => $dto);
my $comments = $api->create_comment(%params);
print "The slide has " . (scalar @{$comments->{list}}) . " comments";
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}