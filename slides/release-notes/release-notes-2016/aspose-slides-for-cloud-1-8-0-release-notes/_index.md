---
title: "Aspose.Slides for Cloud 1.8.0 Release Notes"
type: docs
url: /aspose-slides-for-cloud-1-8-0-release-notes/
weight: 30
---

New Features

|**Key** |**Summary** |**Category** |
| :- | :- | :- |
|SLIDESCLOUD-189|Support for setting slide background image and changing theme|Feature |
|SLIDESCLOUD-206|Themes processing|Feature|
|SLIDESCLOUD-146|Cell borders missing in the generated PDF file|Bug |
|SLIDESCLOUD-225|Incorrect text alignment in generated pdf|Bug|
## **Public API Changes**
- Properties MasterSlides and LayoutSlides have been to Presentation DTO (Data Transfer Object).
- Added property LayoutSlide to Slide DTO (Data Transfer Object).
- Added new resource MasterSlides. It allows to GET list of all master slides in presentation. It also allows to clone master slide from another presentation via POST request and optionally apply cloned master to all existing slides.
- Added new resource MasterSlide. It allows to GET list of child layout slides and list of depending slides.
- Added new resource LayoutSlides. It allows to GET list of all layout slides in presentation. It also allows to clone layout slide from another presentation via POST request.
- Added new resource LayoutSlide. It allows to GET list of depending slides and parent master slide. Master slide could be change in PUT request
- Changing layout slide for particular slide allowed in PUT request for Slide resource.
- Optional parameter 'layoutAlias' allowed in POST request of Slides resource. It could be an integer layout slide index or string layout type.
- Added new pipeline task AddLayoutSlide
- Added new pipeline task AddMasterSlide
