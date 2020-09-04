---
title: "Aspose.Slides Cloud 20.5 Release Notes"
type: docs
url: /aspose-slides-cloud-20-5-release-notes/
weight: 30
---

{{% alert color="primary" %}} 

The page contains release notes for Aspose.Slides Cloud 20.5 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}} 
## **New features and enhancements**
- SLIDESCLOUD-928 - Read Notes from Slide from the request body
## **Other improvements and changes**
- SLIDESCLOUD-923 - Fix API reference for methods with binary body parameters
## **Public API changes**
- Added **slides/{slideIndex}/notesSlide** resource at the root level (not connected to a storage document). Its POST method allows us to get notes to slide information for a document provided in the request body.
- POST for new **slides/{slideIndex}/notesSlide/{format}** subresource allows to get notes slide in a specified image format.
