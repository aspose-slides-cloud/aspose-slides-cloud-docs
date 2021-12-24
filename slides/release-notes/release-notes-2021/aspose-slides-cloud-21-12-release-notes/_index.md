---
title: "Aspose.Slides Cloud 21.12 Release Notes"
type: docs
url: /aspose-slides-cloud-21-12-release-notes/
weight: 120
---

## **Improvements and Changes**
- **SLIDESCLOUD-735** Support animation effects on paragraph level
- **SLIDESCLOUD-1061** Support Shape.ThreeDFormat properties
- **SLIDESCLOUD-1298** Make PDF one of input formats for Convert methods
- **SLIDESCLOUD-1305** Support export to HTML5
- **SLIDESCLOUD-1313** Ensure enum query parameters are validated in SDKs
- **SLIDESCLOUD-1325** C# API call fails with the OutOfMemory exception
- **SLIDESCLOUD-1354** Add width & height to ExportOptions

## **Public API changes**
A new **ThreeDFormat** property is added to **ShapeBase** object which allows to get and set 3D effects for shapes. See [documentation](/slides/three-d-format-type/) for more info.

Added **Html5** to the list of allowed values for **ExportFormat** type. You can now convert presentations to HTML5.

New **With** and **Height** properties are added to **ExportOptions** object. You can now specify custom size in conversion methods. See [documentation](/slides/convert-using-custom-size/) for an example.

A new **paragraphIndex** parameter is added to **GetSlideAnimation** and **GetSpecialSlideAnimation** methods. A new **paragraphIndex** property is added to **Effect** object. You can now get and set animation effect for a specific paragraph. See [documentation](/slides/working-with-animation-for-a-specific-paragraph/) for an example.
