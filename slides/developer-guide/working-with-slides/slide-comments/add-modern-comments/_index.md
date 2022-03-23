---
title: "Add Modern Comments"
type: docs
url: /add-modern-comments/
weight: 30
---
## **Introduction**
The article shows how to add a modern comment using Aspose.Slides Cloud.
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
int textSellectionLength = 5;
            
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
    TextSelectionLength = textSellectionLength,
    ChildComments = new List<SlideCommentBase>(){childComment}
};
            
SlideComments response = api.CreateComment("MyPresentation.pptx", 3, dto, 1, null, null);
            
            
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}