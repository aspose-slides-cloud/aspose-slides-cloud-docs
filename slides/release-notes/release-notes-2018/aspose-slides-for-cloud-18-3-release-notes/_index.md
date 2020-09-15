---
title: "Aspose.Slides for Cloud 18.3 Release Notes"
type: docs
url: /aspose-slides-for-cloud-18-3-release-notes/
weight: 90
---

{{% alert color="primary" %}} 

The page contains release notes for Aspose.Slides for Cloud update 18.3 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}} 
## **New Features and Enhancements**
- SLIDESCLOUD-355 - Support adding and removing paragraphs and portions
- SLIDESCLOUD-356 - Return 404 for invalid property name
## **Public API Changes**
- POST method is added to paragraphs resource. It allows to create new paragraphs
- DELETE method is added to paragraphs resource. It allows to delete paragraphs by their indices in a list
- DELETE method is added to paragraph resource. It allows to delete a paragraph
- GET method is added to portions resource. It allows to get portion list for a specified paragraph
- POST method is added to portions resource. It allows to create new portions
- DELETE method is added to portions resource. It allows to delete portions by their indices in a list
- DELETE method is added to portion resource. It allows to delete a portion
- SwfExportOptions object is added that can be used with saveas resource to specify options for exporting a presentation to SWF format
- NotesPosition property is added to PdfExportOptions, TiffExportOptions and SwfExportOptions objects that allow to export slide notes
