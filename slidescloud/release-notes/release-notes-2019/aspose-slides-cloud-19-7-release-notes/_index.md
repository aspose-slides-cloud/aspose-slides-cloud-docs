---
title: "Aspose.Slides Cloud 19.7 release notes"
type: docs
url: /aspose-slides-cloud-19-7-release-notes/
weight: 50
---

## **Other improvements and changes**
\- Export to POT format
\- Support SvgResponsiveLayout property in HtmlOptions
\- Support AlternativeTextTitle shape property
\- Support ParentComment property for comments
\- Support IOleObjectFrame.SubstitutePictureTitle
\- PHP SDK; nothing seems to be returned from call
\- GetSlidesDocumentProperties method throws 503 error intermittently
\- Merge API throws exception-Input string was not in a correct format
## **Public API changes**
- **pot** export format is now available for presentations and slides.
- **SvgResponsiveLayout** boolean property is added to HTML export options.
- **AlternativeTextTitle** property is added to base Shape object.
- **ChildComments** property is added to Slide Comment object. If a slide contains nested comments, they are returned as items of ChildComments property of corresponding parent.
- **IsObjectIcon** and **SubstitutePictureTitle** properies are added to OleObjectFrame shape object.
