---
title: "Aspose.Slides Cloud 22.4 Release Notes"
type: docs
url: /aspose-slides-cloud-22-4-release-notes/
weight: 90
---

## **Improvements and Changes**

- **SLIDESCLOUD-1406** Add transition options to video converter
- **SLIDESCLOUD-1419** Getting default portion format from a paragraph
- **SLIDESCLOUD-999** Support adding Group shapes, GraphicObject, OleObjectFrame
- **SLIDESCLOUD-1389** Set picture image for AudioFrame
- **SLIDESCLOUD-1435** Specified slide indices are ignored when converting PPTX to HTML5
- **SLIDESCLOUD-1423** PdfExportOptions.AccessPermissions property is implemented incorrectly
- **SLIDESCLOUD-1428** VideoExportOptions.VideoResolutionType option does not work
- **SLIDESCLOUD-1427** VideoExportOptions.TransitionDuration option does not work
- **SLIDESCLOUD-1425** Getting the first row index and first column index of merged cell
- **SLIDESCLOUD-1422** Width and Height properties don't work separately when converting PPTX to images
- **SLIDESCLOUD-1421** Width and Height export properties don't work for PDF documents
- **SLIDESCLOUD-1249** Images are not exported correctly to HTML in ZIP mode

## **Public API changes**

Added **TransitionType** and **SlidesTransitionDuration** properties to **VideoExportOptions** class to enable creation videos with transitions. See [documentation](/slides/convert-presentation-to-video/) for more info.

Added **DefaultPortionFormat** property to **Paragraph** class. Added new **PortionFormat** class. You cn now get & set default portion format for a paragraph.

Added **EmbeddedFileBase64Data** and a number of other properties to **OleObjectFrame** class. You can now add OLE Object frames to presentations using Cloud API.

Added **AccessPermissions** class to support access permissions for PDF export.

Added **PictureFillformat** property to **AudioFrame** class.

Added **RowIndex** and **ColumnIndex** properties to **TableCell** class.

Moved **Width** and **Height** properties from **ExportOptions** base class to the new **ImageExportOptionsBase** class. This is a superclass for **ImageExportOptions**, **GifExportOptions** and **TiffExportOptions** classes.

Removed redundant **Shapes** property from **ShapeBase** class. It is only left for **GroupShape** class.
