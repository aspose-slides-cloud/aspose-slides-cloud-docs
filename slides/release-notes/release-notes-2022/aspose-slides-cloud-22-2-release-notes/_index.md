---
title: "Aspose.Slides Cloud 22.2 Release Notes"
type: docs
url: /aspose-slides-cloud-22-2-release-notes/
weight: 110
---

## **Improvements and Changes**

- **SLIDESCLOUD-1348** Add presentation to video conversion
- **SLIDESCLOUD-635** Support text highlighting feature
- **SLIDESCLOUD-1063** Support WordArt
- **SLIDESCLOUD-1322** Support zoom frames
- **SLIDESCLOUD-1369** Removing unused layout slides
- **SLIDESCLOUD-1370** Use Google Cloud storage in Docker container
- **SLIDESCLOUD-1380** Split PDF files
- **SLIDESCLOUD-1097** Support hierarchic categories for all chart types
- **SLIDESCLOUD-1377** Add TimeUnitType.None enum option
- **SLIDESCLOUD-1381** Fix exception code and message for empty paragraph list

## **Public API changes**

Added **Mpeg4** to the list of allowed values for **ExportFormat** type. You can now convert presentations to video.

Added **HighlightShapeText** and **HighlightShapeRegex** methods. See [documentation](/slides/text-highlighting/) for more info.

Added **DeleteUnusedLayoutSlides** and **DeleteUnusedLayoutSlides** methods. See [documentation](/slides/deleting-unused-layoutslides/) for usage example.

Added **ZoomFrame** and **ZoomObject** classes with a number of subclasses. See [documentation](/slides/working-with-zoom-frames/) for more info.

Added **TextFrameFormat** property to **Shape** class to support WordArt. See [documentation](/slides/working-with-word-art/) for more info.

Added **XYSeries** class as a supercalss for **ScatterSeries** and **BubbleSeries** classes.

Added **None** to the list of allowed values for **TimeUnitType** enum type.
