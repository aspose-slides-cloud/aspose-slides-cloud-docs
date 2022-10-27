---
title: "Aspose.Slides Cloud 22.10 Release Notes"
type: docs
url: /aspose-slides-cloud-22-10-release-notes/
weight: 30
---

## **Important Changes and Enhancements**

- **SLIDESCLOUD-1571** Support SlideShowSettings
- **SLIDESCLOUD-1583** Enable AWS S3 as storage for self-hosted cloud solution

## **Other Improvements and Changes**

- **SLIDESCLOUD-1562** Notes text is retrieved incorrectly when using GetNotesSlideOnline method
- **SLIDESCLOUD-1570** Support RepeatUntilEndSlide & RepeatUntilNextClick properties for Effect class in animation feature
- **SLIDESCLOUD-1576** Remove subshape methods

## **Public API changes**

Added new **GetSlideShowProperties** and  **SetSlideShowProperties** methods to get & set slideshow properties. See [documentation](/slides/working-with-slide-show-properties/) for more info.

Methods that work with shapes, paragraphs and portions now have an optional **subShape** parameter which can be used to access subshapes (SmartArt elements, grouped shapes). Separate methods for subshapes (**GetSubshapeParagraphs**, **CreateSubshape**, **AlignSubshapes** etc.) have been removed.

Added boolean **RepeatUntilEndSlide** and **RepeatUntilNextClick** properties to **Effect** class.
