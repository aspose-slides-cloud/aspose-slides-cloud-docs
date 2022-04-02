---
title: "Aspose.Slides Cloud 22.3 Release Notes"
type: docs
url: /aspose-slides-cloud-22-3-release-notes/
weight: 100
---

## **Improvements and Changes**

- **SLIDESCLOUD-1326** Support modern comments
- **SLIDESCLOUD-812** Support Font Fallback Rules
- **SLIDESCLOUD-1411** Getting all charts from a slide
- **SLIDESCLOUD-1383** Enable creating portions with CreateParagraph / UpdateParagraph methods
- **SLIDESCLOUD-1365** Get and set a font for a text portion
- **SLIDESCLOUD-937** Support GetRect method for paragraphs and portions
- **SLIDESCLOUD-1359** Hide legend and gridlines of a chart
- **SLIDESCLOUD-1401** Broken PDF is converted without any exception
- **SLIDESCLOUD-1376** Slide count, shape count and paragraph count are wrong values in Perl SDK
- **SLIDESCLOUD-885** Update lineformat for shape fails occasionaly
- **SLIDESCLOUD-1405** pdf parameter is a required parameter for ImportFromPdf method
- **SLIDESCLOUD-1414** Support ffmpeg conversion in linux container

## **Public API changes**

Added **ModernSlideComment** class to support modern comments. Also added **SlideCommentBase** as base class for comments. Added optional **shapeIndex** to **CreateComment** and **CreateCommentOnline** methods. See [documentation](/slides/add-modern-comments/) for more info.

Added **GetParagraphRectangle**, **GetPortionRectangle** method and new **TextBounds** class to get paragraph or portion bounds. See [documentation](/slides/get-paragraph-rectangle/) for more info.

Added optional **shapeType** parameter for **GetShapes** method. You can now get list for shapes of a particular type (e.g. charts or tables). See [documentation](/slides/extract-shapes-from-a-slide/) for more info.

Added **FontFallbackRules** class and **FontFallbackRules** property to **ExportOptions** class. See [documentation](/slides/convert-using-fontfallbackrules/) for more info.

Added **LatinFont**, **EastAsianFont** and **ComplexScriptFont** properties to **Portion** class to enable getting and seting portion font name.

Added **ChartLinesFormat** class and **MajorGridLinesFormat** and **MinorGridLinesFormat** properties to **Axis** class.

Added **HideLegend** boolean property to **Legend** class.
