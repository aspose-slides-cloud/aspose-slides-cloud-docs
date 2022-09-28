---
title: "Aspose.Slides Cloud 22.9 Release Notes"
type: docs
url: /aspose-slides-cloud-22-9-release-notes/
weight: 40
---

## **Important Changes and Enhancements**

- **SLIDESCLOUD-1535** Replace presentation fonts
- **SLIDESCLOUD-1552** Enhancements to font methods
- **SLIDESCLOUD-1554** Adding a shape to a SmartArt graphic

## **Other Improvements and Changes**

- **SLIDESCLOUD-1537** Font substitution
- **SLIDESCLOUD-1556** DeleteSubshape does not work for a SmartArt graphic
- **SLIDESCLOUD-1551** Add option to group shapes generated from SVG
- **SLIDESCLOUD-892** Support formatting individual datapoints in charts
- **SLIDESCLOUD-1565** Width and Height parameters don't work when loading Notes slide
- **SLIDESCLOUD-1546** DTO classes are instantiated without shape type initialization in C++

## **Public API changes**

Added new **ReplaceFont** and **ReplaceFontOnline** methods that allow replacing presentation fonts. See [documentation](/slides/replace-font/) for more info.

Added new **SetEmbeddedFontFromRequest** and **SetEmbeddedFontFromRequestOnline** that allow to embed fonts without uploading them to the storage. See [documentation](/slides/setting-embedded-font-from-request/) for more info.

Added new **CreateSmartArtNode** and  **DeleteSmartArtNode** methods to manage individual nodes in SmartArt shapes. See [documentation](/slides/adding-smartart-node/) for more info.

Added an optional **fontsFolder** parameter to **SetEmbeddedFont** and **SetEmbeddedFontOnline** methods to enable using custom fonts with those methods.

Added **FontSubstRules** property to **ExportOptions** class to allow specifying font substitution rules in conversion methods.

Added an optional **group** parameter to **ImportImagesFromSvg** method to allow importing SVG images as a GroupShape.

Added **FillFomat**, **LineFormat**, **EffectFormat** and  **ThreeDFormat** properties to **DataPoint** class that allow formatting individual chart data points.
