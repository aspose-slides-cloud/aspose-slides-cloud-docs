---
title: "Add Modern Comments"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- slide
- comment
- author
- modern comment
- create a comment
- add a comment
type: docs
url: /add-modern-comments/
weight: 30
---
## **Introduction**
You can add comments using **CreateComment** method. The example below shows how to add a modern comment. You can also add a [regular comment](/slides/add-comments/) using the same method.
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/comments|POST|Adds comment on the slide| [CreateComment](https://apireference.aspose.cloud/slides/#/Comments/CreateComment)
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```
```java

curl -v -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/comments" -d @"comments.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```
comments.json
```java
{
    "type": "modern",
    "text": "comment text",
    "author":"Author Name",
    "status":"active",
    "childComments":[
        {
            "type": "modern",
            "text": "child comment text",
            "author": "Author Name",
            "status": "resolved"
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
int textSelectionStartIndex = 1;
int textSelectionLength = 5;
            
SlideModernComment childComment = new SlideModernComment()
{
    Author = "Author Name",
    Text = "Comment text",
    Status = SlideModernComment.StatusEnum.Resolved
};
SlideModernComment dto = new SlideModernComment
{
    Author = "Author Name",
    Text = "Comment text",
    Status  = SlideModernComment.StatusEnum.Active,
    TextSelectionStart = textSelectionStartIndex,
    TextSelectionLength = textSelectionLength,
    ChildComments = new List<SlideCommentBase>(){childComment}
};
            
SlideComments response = api.CreateComment("MyPresentation.pptx", 3, dto, 1, null, null);
Console.WriteLine($"The slide has {response.List.Count} comments");
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
int textSelectionStartIndex = 1;
int textSelectionLength = 5;

SlideModernComment dto = new SlideModernComment();
dto.setText("Comment text");
dto.setAuthor("Author Name");
dto.setStatus(SlideModernComment.StatusEnum.RESOLVED);

List<SlideCommentBase> childComments = new ArrayList<SlideCommentBase>();
SlideModernComment childComment = new SlideModernComment();
childComment.setText("Child comment text");
childComment.setAuthor("Author Name");
childComment.setStatus(SlideModernComment.StatusEnum.ACTIVE);
childComment.setTextSelectionStart(textSelectionStartIndex);
childComment.setTextSelectionLength(textSelectionLength);

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
use Aspose\Slides\Cloud\Sdk\Model\SlideModernComment;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);
$textSelectionStartIndex = 1;
$textSelectionLength = 5;

$dto = new SlideModernComment();
$dto->setText("Comment text");
$dto->setAuthor("Author Name");
$dto->setStatus("Resolved");

$childComment = new SlideModernComment();
$childComment->setText("Child comment text");
$childComment->setAuthor("Author Name");
$childComment->setStatus("Active");
$childComment->setTextSelectionStart($textSelectionStartIndex);
$childComment->setTextSelectionLength($textSelectionLength);
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
text_selection_start_index = 1
text_selection_length = 5

dto = AsposeSlidesCloud::SlideModernComment.new()
dto.text = "Comment text"
dto.author = "Author Name"
dto.status = "Resolved"

child_comment = AsposeSlidesCloud::SlideModernComment.new()
child_comment.text = "Child comment text"
child_comment.author = "Author Name"
child_comment.status = "Active"
child_comment.text_selection_start = text_selection_start_index
child_comment.text_selection_length = text_selection_length
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
from asposeslidescloud.models.slide_modern_comment import SlideModernComment

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)
text_selection_start_index = 1
text_selection_length = 5

dto = SlideModernComment()
dto.text = "Comment text"
dto.author = "Author Name"
dto.status = "Resolved"

child_comment = SlideModernComment()
child_comment.text = "Child comment text"
child_comment.author = "Author Name"
child_comment.status = "Active"
child_comment.text_selection_start = text_selection_start_index
child_comment.text_selection_length = text_selection_length
dto.child_comments = [ child_comment ]
response = api.create_comment("MyPresentation.pptx", 3, dto)
print("The slide has " + str(len(response.list)) + " comments")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");
const textSelectionStartIndex = 1;
const textSelectionLength = 5;

const dto = new CloudSdk.SlideModernComment();
dto.text = "Comment text";
dto.author = "Author Name";
dto.status = "Resolved";

const childComment = new CloudSdk.SlideModernComment();
childComment.text = "Child comment text";
childComment.author = "Author Name";
childComment.status = "Active";
childComment.textSelectionStart = textSelectionStartIndex;
childComment.textSelectionLength = textSelectionLength;
dto.childComments= [ childComment ];
api.createComment("MyPresentation.pptx", 3, dto).then(comments => {
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
var textSelectionStartIndex int32 = 1
var textSelectionLength int32 = 5

dto := asposeslidescloud.NewSlideModernComment()
dto.Text = "Comment text"
dto.Author = "Author Name"
dto.Status = "Resolved"

childComment := asposeslidescloud.NewSlideModernComment()
childComment.Text = "Child comment text"
childComment.Author = "Author Name"
childComment.Status = "Active"
childComment.TextSelectionStart = textSelectionStartIndex
childComment.TextSelectionLength = textSelectionLength
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
use AsposeSlidesCloud::Object::SlideModernComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);
my $text_selection_start_index = 1;
my $text_selection_length = 5;

my $dto = AsposeSlidesCloud::Object::SlideModernComment->new();
$dto->{text} = "Comment text";
$dto->{author} = "Author Name";
$dto->{status} = "Resolved";

my $childComment = AsposeSlidesCloud::Object::SlideModernComment->new();
$childComment->{text} = "Child comment text";
$childComment->{author} = "Author Name";
$childComment->{status} = "Active";
$childComment->{text_selection_start} = $text_selection_start_index;
$childComment->{text_selection_length} = $text_selection_length;
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
