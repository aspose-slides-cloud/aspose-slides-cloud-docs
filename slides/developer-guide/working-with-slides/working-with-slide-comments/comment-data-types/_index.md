---
title: "Comment Data Types"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- slide
- comment
- author
type: docs
url: /comment-data-types/
weight: 200
---

## **Introduction**

This article describes data types used in slide comments.

## **SlideCommentBase Properties**
|**Name**|**Type**|**Description**|
| :- | :- | :- |
|Author|string|The author of a comment.|
|ChildComments|[SlideCommentBase](/slides/comment-data-types/#slidecommentbase-properties) collection|The collection of child comments.|
|CreatedTime|string|The date and time of comment creation.|
|Text|string|The comment text.|
|Type|[TypeEnum](/slides/comment-data-types/#typeenum-values)|The comment type.|

## **SlideComment Properties**
|**Name**|**Type**|**Description**|
| :- | :- | :- |
|Author|string|The author of a comment.|
|ChildComments|[SlideCommentBase](/slides/comment-data-types/#slidecommentbase-properties) collection|The collection of child comments.|
|CreatedTime|string|The date and time of comment creation.|
|Text|string|The comment text.|
|Type|[TypeEnum](/slides/comment-data-types/#typeenum-values)|The comment type. The property is set to `Regular`.|

## **SlideModernComment Properties**
|**Name**|**Type**|**Description**|
| :- | :- | :- |
|Author|string|The author of a comment.|
|ChildComments|[SlideCommentBase](/slides/comment-data-types/#slidecommentbase-properties) collection|The collection of child comments.|
|CreatedTime|string|The date and time of comment creation.|
|Status|[StatusEnum](/slides/comment-data-types/#statusenum-values)|The comment status.|
|Text|string|The comment text.|
|TextSelectionLength|int|The text selection length in the text frame if the comment is associated with a shape.|
|TextSelectionStart|int|The starting position of text selection in the text frame if the comment is associated with a shape.|
|Type|[TypeEnum](/slides/comment-data-types/#typeenum-values)|The comment type. The property is set to `Modern`.|

## **SlideComments Properties**
|**Name**|**Type**|**Description**|
| :- | :- | :- |
|AlternateLinks|`ResourceUri` collection|The alternate links to resources. Inherited from `ResourceBase`.|
|List|[SlideCommentBase](/slides/comment-data-types/#slidecommentbase-properties) collection|The list of slide comments.|
|SelfUri|`ResourceUri`|The identifier for the resource. Inherited from `ResourceBase`.|

## **TypeEnum Values**
|**Name**|**Value**|**Description**|
| :- | :- | :- |
|Regular|0|Specifies a regular comment.|
|Modern|1|Specifies a modern comment.|

## **StatusEnum Values**
|**Name**|**Value**|**Description**|
| :- | :- | :- |
|NotDefined|0|The comment status is not defined.|
|Active|1|The comment status is "active".|
|Resolved|2|The comment status is "resolved".|
|Closed|3|The comment status is "closed".|
