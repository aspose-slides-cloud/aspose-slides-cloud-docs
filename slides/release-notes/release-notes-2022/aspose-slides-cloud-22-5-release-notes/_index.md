---
title: "Aspose.Slides Cloud 22.5 Release Notes"
type: docs
url: /aspose-slides-cloud-22-5-release-notes/
weight: 80
---

## **Improvements and Changes**

- **SLIDESCLOUD-1452** Setting a poster image for Video frame
- **SLIDESCLOUD-1443** Setting transparency for images applied to fill autoshapes
- **SLIDESCLOUD-983** Cannot update portions inside smart art shape
- **SLIDESCLOUD-754** Include resource index in URL info
- **SLIDESCLOUD-1476** Slide notes are missing when converting PPTX to HTML
- **SLIDESCLOUD-1461** Cloning picture from presentation to another throws ApiException
- **SLIDESCLOUD-1462** Add missing Use Case tests for Python SDK
- **SLIDESCLOUD-1451** Add missing Use Case tests for Java SDK
- **SLIDESCLOUD-1440** Add use case tests for PHP SDK
- **SLIDESCLOUD-1420** ExportOptions class allows to change Format property

## **Public API changes**

Added **Paragraphs** property to **SmartArtNode** class to enable getting and setting text for SmartArt nodes. Excluded **shapes** from SmartArt node paths. See [documentation](/slides/working-with-smart-art-text/) for more info.

Added **ImageTransformList** property to **PictureFill** class to enable setting image transform effects. Added **ImageTransformEffect** class and subclasses for different kind of of effects.

Added **PictureFillFormat** property to **VideoFrame** class to enable setting poster image for video frames.

Added **SlideIndex** and **ShapeIndex** properties to **ResourceUri** class to simplify retrieveing slide & shape indexes for resources.

Removed redundant **BoxAndWhiskersSeries**, **WaterfallSeries** and **WaterfallChartDataPoint** classes. Their properties are moved to base **OneValueSeries** and **OneValueChartDataPoint** classes.
