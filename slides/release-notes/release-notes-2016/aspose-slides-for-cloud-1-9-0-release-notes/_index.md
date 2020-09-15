---
title: "Aspose.Slides for Cloud 1.9.0 Release Notes"
type: docs
url: /aspose-slides-for-cloud-1-9-0-release-notes/
weight: 20
---

New Features

|**Key** |**Summary** |**Category** |
| :- | :- | :- |
|SLIDESCLOUD-98|[Convert a PPT to SWF](/slidescloud/working-with-document/)|New Feature|
|SLIDESCLOUD-205|[Ability to clone shapes](/slidescloud/working-with-shapes/)|New Feature|
|SLIDESCLOUD-207|[Add support for AudioFrame](/slidescloud/working-with-shapes/)|New Feature|
|SLIDESCLOUD-208|[Add support for VideoFrame](/slidescloud/working-with-shapes/)|New Feature|
|SLIDESCLOUD-241|[Support for accessing slide notes using REST Api](/slidescloud/working-with-notesslides/)|New Feature|
## **Public API Changes**
- 'Swf' and 'SwfNotes' values have been added to the list of available Presentation export formats. It allows to export slides or notes to swf format.
- 'TiffNotes' value has been added to the list of available Presentation export formats. It allows to export notes to tiff format.
- POST method of Shapes resource can receive AudioFrame and VideoFrame DTO (Data Transfer Object) to add new video or audio frames into slide.
- PUT method of Shape resource allows to update AudioFrame and VideoFrame objects.
- Optional parameter 'shapeToClone' has been added to the Shapes POST resource. It allows to clone existing shape.
- Property 'NotesSlide' has been added to the Slide DTO (Data Transfer Object).
- Added new resource NotesSlide. It allows to read, create, update and delete notes associated with slide. It also allows to export notes slide as an image and it provides access to shapes of notes slide.
