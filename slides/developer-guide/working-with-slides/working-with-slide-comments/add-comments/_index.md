---
title: "Add Comments"
keywords: "PowerPoint, presentation, REST API, Cloud API, slide, comment, author, create a comment, add a comment"
type: docs
url: /add-comments/
weight: 20
---

## **Introduction**

Comments on slides in PowerPoint presentations are a tool that allows you to add notes, questions, explanations, or other information to specific presentation slides. This is a valuable means of collaboration and communication within a working group or when discussing the presentation with colleagues. You can use the following methods to add regular comments on a slide.

You can also add [modern comments](/slides/add-modern-comments/) using the same methods.

## **CreateComment**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/comments|POST|Adds a comment to a slide or shape in a presentation saved in a storage.|[CreateComment](https://apireference.aspose.cloud/slides/#/Comments/CreateComment)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|dto|`SlideCommentBase`|body|true|The data transfer object with comment parameters.|
|shapeIndex|integer|query|false|The 1-based index of a shape to comment.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

Add a regular comment from **John Smith** to the **first** slide in the document **MyPresentation.pptx**. Add a regular comment from **James Johnson** to the first comment in the same request.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the Comments**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/comments" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: text/json" \
     -d @"MyComments.json" 

```

MyComments.json content:
```json
{
    "type": "regular",
    "author": "John Smith",
    "text": "This is the first comment.",
    "childComments":[
        {
            "type": "regular",
            "author": "James Johnson",
            "text": "This is a child comment."
        }
    ]
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
  "list": [
    {
      "author": "John Smith",
      "text": "This is the first comment.",
      "createdTime": "2024-02-16T05:18:33.410725Z",
      "childComments": [
        {
          "author": "James Johnson",
          "text": "This is a child comment.",
          "createdTime": "2024-02-16T05:18:33.4107358Z",
          "type": "Regular"
        }
      ],
      "type": "Regular"
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

{{< tabs tabTotal="10" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using System.Collections.Generic;

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string fileName = "MyPresentation.pptx";
        int slideIndex = 1;

        SlideComment slideComment = new SlideComment
        {
            Author = "John Smith",
            Text = "This is the first comment.",
            ChildComments = new List<SlideCommentBase>
            {
                new SlideComment
                {
                    Author = "James Johnson",
                    Text = "This is a child comment."
                }
            }
        };

        SlideComments slideComments = slidesApi.CreateComment(fileName, slideIndex, slideComment);

        int commentCount = slideComments.List.Count;
        Console.WriteLine("Сomment count: " + commentCount);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SlideComment;
import com.aspose.slides.model.SlideComments;

import java.util.List;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;

        SlideComment firstComment = new SlideComment();
        firstComment.setAuthor("John Smith");
        firstComment.setText("This is the first comment.");

        SlideComment childComment = new SlideComment();
        childComment.setAuthor("James Johnson");
        childComment.setText("This is a child comment.");

        firstComment.setChildComments(List.of(childComment));

        SlideComments slideComments = slidesApi.createComment(fileName, slideIndex, firstComment, null, null, null, null);

        int commentCount = slideComments.getList().size();
        System.out.println("Comment count: " + commentCount);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideComment;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;

$firstComment = new SlideComment();
$firstComment->setAuthor("John Smith");
$firstComment->setText("This is the first comment.");

$childComment = new SlideComment();
$childComment->setAuthor("James Johnson");
$childComment->setText("This is a child comment.");

$firstComment->setChildComments([$childComment]);

$slideComments = $slidesApi->createComment($fileName, $slideIndex, $firstComment);

$commentCount = count($slideComments->getList());
echo "Comment count: ", $commentCount;
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

first_comment = SlideComment.new
first_comment.author = "John Smith"
first_comment.text = "This is the first comment."

child_comment = SlideComment.new
child_comment.author = "James Johnson"
child_comment.text = "This is a child comment."

first_comment.child_comments = [child_comment]

slide_comments = slides_api.create_comment(file_name, slide_index, first_comment)

comment_count = slide_comments.list.length()
puts "Comment count: #{comment_count}"
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_comment import SlideComment

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1

first_comment = SlideComment()
first_comment.author = "John Smith"
first_comment.text = "This is the first comment."

child_comment = SlideComment()
child_comment.author = "James Johnson"
child_comment.text = "This is a child comment."

first_comment.child_comments = [child_comment]

slide_comments = slides_api.create_comment(file_name, slide_index, first_comment)

comment_count = len(slide_comments.list)
print("Comment count:", comment_count)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;

firstComment = new cloudSdk.SlideComment();
firstComment.author = "John Smith";
firstComment.text = "This is the first comment.";

childComment = new cloudSdk.SlideComment();
childComment.author = "James Johnson";
childComment.text = "This is a child comment.";

firstComment.childComments = [childComment];

slidesApi.createComment(fileName, slideIndex, firstComment).then(slideComments => {
    commentCount = slideComments.body.list.length;
    console.log("Comment count:", commentCount);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"
#include "asposeslidescloud/model/SlideComment.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;

    std::shared_ptr<SlideComment> firstComment = std::make_shared<SlideComment>();
    firstComment->setAuthor(L"John Smith");
    firstComment->setText(L"This is the first comment.");

    std::shared_ptr<SlideComment> childComment = std::make_shared<SlideComment>();
    childComment->setAuthor(L"James Johnson");
    childComment->setText(L"This is a child comment.");

    firstComment->setChildComments({ childComment });

    std::shared_ptr<SlideComments> slideComments = slidesApi->createComment(fileName, slideIndex, firstComment).get();

    int commentCount = slideComments->getList().size();
    std::wcout << L"Comment count: " << commentCount;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;

my $first_comment = AsposeSlidesCloud::Object::SlideComment->new();
$first_comment->{author} = "John Smith";
$first_comment->{text} = "This is the first comment.";

my $child_comment = AsposeSlidesCloud::Object::SlideComment->new();
$child_comment->{author} = "James Johnson";
$child_comment->{text} = "This is a child comment.";

$first_comment->{child_comments} = [$child_comment];

my %parameters = (name => $file_name, slide_index => $slide_index, dto => $first_comment);
$slide_comments = $slides_api->create_comment(%parameters);

my $comment_count = @{$slide_comments->{list}};
print("Comment count: ", $comment_count);
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

firstComment := asposeslidescloud.NewSlideComment()
firstComment.Author = "John Smith"
firstComment.Text = "This is the first comment."

childComment := asposeslidescloud.NewSlideComment()
childComment.Author = "James Johnson"
childComment.Text = "This is a child comment."

childComments := []asposeslidescloud.ISlideCommentBase { childComment }
firstComment.ChildComments = childComments

comments, _, e := api.SlidesApi.CreateComment(fileName, slideIndex, firstComment, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Comment count: %v", len(comments.GetList()))
```

{{< /tab >}}

{{< /tabs >}}

## **CreateCommentOnline**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/slides/{slideIndex}/comments|POST|Adds a comment to a slide or shape in a presentation saved in a local file.|[CreateCommentOnline](https://reference.aspose.cloud/slides/#/Comments/CreateCommentOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|file|formData|true|The presentation file.|
|slideIndex|integer|path|true|The 1-based index of a presentation slide.|
|dto|`SlideCommentBase`|body|true|The data transfer object with comment parameters.|
|shapeIndex|integer|query|false|The 1-based index of a shape to comment.|
|password|string|header|false|The password to open the presentation.|

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
