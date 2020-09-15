---
title: "Aspose.Slides for Cloud 18.4 Release Notes"
type: docs
url: /aspose-slides-for-cloud-18-4-release-notes/
weight: 80
---

{{% alert color="primary" %}} 

The page contains release notes for Aspose.Slides for Cloud update 18.4 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}} 
## **New Features and Enhancements**
- SLIDESCLOUD-378 - slides/saveAs API now support ExportOptions parameter
- SLIDESCLOUD-379 - Support all ExportOptions
- SLIDESCLOUD-413 - Add color query parameter to PUT method of background resource
## **Other Improvements and Changes**
- SLIDESCLOUD-398 - Folder attribute not added to URL
- SLIDESCLOUD-401 - fontsFolder parameter is not working with GET /slides/{name}/slides/{slideIndex}/saveAs/{format} API
## **Public API Changes**
- POST method is added to saveAs resource for slide. It allows to save a slide in a specified format using options provided as JSON in a request body
- XpsExportOptions, SvgExportOptions and ImageExportOptions objects are added that can be used with saveas resource to specify options for exporting a presentation to XPS, SVG and image formats (except TIFF that has its own option format)
- A number of properties (ShowHiddenSlides, CommentsPosition, CommentsAreaWidth et al.) are added to PdfExportOptions, HtmlExportOptions, TiffExportOptions and SwfExportOptions objects to fully support export options available in Slides.NET
- fontsFolder optional parameter is added to saveAs resource for slide. It allows to specify a storage folder for custom fonts when saving a single slide
- color optional PUT request parameter is added to background resource. It allows to set the background color for a slide
- Passing ARGB color as PUT request body parameter of background resource is deprecated and is going to be removed after 18.6. Use color query string parameter instead
- PdfNotes, SwfNotes and TiffNotes export formats are deprecated and are going to be removed after 18.6. Use Pdf, Swf and Tiff formats instead with NotesPosition export option


