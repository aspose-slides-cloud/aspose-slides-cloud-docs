---
title: "Aspose.Slides Cloud 22.8 Release Notes"
type: docs
url: /aspose-slides-cloud-22-8-release-notes/
weight: 50
---

## **Important Changes and Enhancements**

- **SLIDESCLOUD-1534** Get presentation fonts
- **SLIDESCLOUD-1536** Embed/unembed presentation fonts
- **SLIDESCLOUD-1525** Adding individual shapes from SVG

## **Other Improvements and Changes**

- **SLIDESCLOUD-1548** Upgrade GuzzleHttp version to 7.2.4 for PHP SDK

## **Public API changes**

Added new **GetFonts** and **GetFontsOnline** methods you can get a list for fonts used in the presentation.

Added new **SetEmbeddedFont**, **SetEmbeddedFontOnline**, **DeleteEmbeddedFont** and **DeleteEmbeddedFontOnline** methods to embed/unembed presentation fonts. See [documentation](/slides/working-with-fonts/) for more info about new font handling methods.

Added new **ImportImagesFromSvg** method to import SVG images as individual geometry shapes. See [documentation](/slides/import-shapes-from-svg/) for more info.
