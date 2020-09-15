---
title: "Aspose.Slides Cloud 18.7 Release Notes"
type: docs
url: /aspose-slides-cloud-18-7-release-notes/
weight: 50
---

{{% alert color="primary" %}} 

The page contains release notes for Aspose.Slides Cloud 18.7 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}} 
## **New Features and Enhancements**
- SLIDESCLOUD-466 - Remove obsolete xxxNotes export formats
- SLIDESCLOUD-467 - Remove obsolete feature of passing color in PUT method body for background resource
- SLIDESCLOUD-468 - Support optional password parameter for all methods
## **Other Improvements and Changes**
- SLIDESCLOUD-420 - Black rectangle instead of drawing in exported SVG
## **Public API Changes**
- optional password parameters are added to many methods to make them available for password-protected documents. They include:
  - **password** optional parameter for the following resources: **slides**, **slide**, **notesSlide**; **saveAs** for **slide** and **shape**; **shapes** and subresources - **shape**, **paragraphs**, **paragraphportions**, **portion**; **masterSlides**, **masterSlide**; **layoutSlides**, **layoutSlide**; **images**, **image**; **placeholders**, **placeholder**; **properties**, **property**; **background**; **comments**; **theme** and subresources - **colorScheme**, **formatScheme**, **fontScheme**; **textItems**, **replaceText**; **merge**; **split** - to be used with the document in case it is password-protected;
  - **cloneFromPassword** optional parameter for POST method of **masterSlides** and **layoutSlides** resources to be used with clone source document in case it is specified and is password-protected;
  - **templatePassword** optional parameter for PUT and POST methods of **presentation** resource to be used with template document in case it is specified and is password-protected;
  - **Password** property for **PresentationToMerge** object to allow for supplying password for the merged document;
  - **PresentationPasswords** property for **PresentationsMergeRequest** object to allow for supplying passwords for the merged documents;
- Passing ARGB color as PUT request body parameter of **background** resource is removed as obsolete. Use **color** query string parameter instead.
- **PdfNotes**, **SwfNotes** and **TiffNotes** export formats are removed as obsolete. Use **Pdf**, **Swf** and **Tiff** formats instead with NotesPosition export option.
