---
title: "Aspose.Slides for Cloud 18.5 Release Notes"
type: docs
url: /aspose-slides-for-cloud-18-5-release-notes/
weight: 70
---

{{% alert color="primary" %}} 

The page contains release notes for Aspose.Slides for Cloud update 18.5 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}} 
## **New Features and Enhancements**
- SLIDESCLOUD-319 - Export shape to SVG
- SLIDESCLOUD-408 - Insert slide/paragraph/portion to specified position
- SLIDESCLOUD-416 - Support outPath parameter for slide/saveAs resource
## **Other Improvements and Changes**
- SLIDESCLOUD-360 - Wrong status code for invalid index
- SLIDESCLOUD-402 - Slides Background (Gradient) and Bullets are missing
## **Public API Changes**
- SVG is added to shape export formats. You can also specify export options in request body for POST method of saveAs resource for a shape
- **position** optional POST request parameter is added to shapes, paragraphs and portions resources. It allows to insert an item to a list at the specified position, not only to the end of the list
- **outPath** request parameter is now available for **saveAs** resource for shape and slide, not only for presentation
- **fontsFolder** request parameter is available for **saveAs** resource for shape, not only slide and presentation


