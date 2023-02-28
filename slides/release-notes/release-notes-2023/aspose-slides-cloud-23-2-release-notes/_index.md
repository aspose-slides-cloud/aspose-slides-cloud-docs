---
title: "Aspose.Slides Cloud 23.2 Release Notes"
type: docs
url: /aspose-slides-cloud-23-2-release-notes/
weight: 110
---

## **Important Changes and Enhancements**

- **SLIDESCLOUD-1628** Convert shape from JSON input

## **Other Improvements and Changes**

- **SLIDESCLOUD-1065** Support shape.TextFrame.TextFrameFormat properties
- **SLIDESCLOUD-1622** Allow setting hyperlink sound
- **SLIDESCLOUD-1623** Support StopPreviousSound property for animation effects
- **SLIDESCLOUD-1621** Support new PDF Compliance levels
- **SLIDESCLOUD-1708** Hidden slides appear when PPTX is converted to image format
- **SLIDESCLOUD-861** Table is recreated in update shape method

## **Public API changes**

New **DownloadShapeFromDto** method allows to convert charts and other shapes from DTO to SVG and other formats without creating and storing presentation files. See [documentation](/slides/download-shape-from-a-data-transfer-object/) for more info.

Added **SoundBase64** property to **Hyperlink** class to support getting and setting hyperlink sounds.

Added **BulletFillFormat** property to **Paragraph** class.

Added **StopPreviousSound** property to animation **Effect** class.

Added a number of properties to **TextFrameFormat** that enable formatting shape text: **MarginLeft**, **MarginRight**, **MarginTop**, **MarginBottom**, **WrapText**, **AnchoringType**, **CenterText**, **TextVerticalType**, **AutofitType**, **ColumnCount**, **ColumnSpacing**, **KeepTextFlat**, **RotationAngle**, **DefaultParagraphFormat**.

Added **Pdf16**, **Pdf17**, **PdfA2b**, **PdfA2a**, **PdfA2u**, **PdfA3a**, **PdfA3b** to the list of allowed values for **PdfExportOptions.Compliance** property.
