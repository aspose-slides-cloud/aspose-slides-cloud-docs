---
title: "Aspose.Slides Cloud 21.2 Release Notes"
type: docs
url: /aspose-slides-cloud-21-2-release-notes/
weight: 60
---
## **Improvements and Changes**

- **SLIDESCLOUD-1064** Support Map charts
- **SLIDESCLOUD-1060** Support SketchFormat property of LineFormat
- **SLIDESCLOUD-1092** Aspose.Slides Cloud SDK for Python with Amazon Lambda
- **SLIDESCLOUD-995** Enable category management for Waterfall charts
- **SLIDESCLOUD-977** Sunburst & Treemap charts change number of categories after save
- **SLIDESCLOUD-984** Chart type changes after deleting a series
- **SLIDESCLOUD-1089** fromPDF method should return 400 error in case of invalid input data

## **Public API Changes**
### Map Charts
**Map** has been added to the list of valid **ChartType** properties to support Map charts.

### **LineFormat.SketchFormat** Property
A new **SketchFormat** property has been added to **LineFormat** class. The property values: **None**, **Curved**, **Freehand**, **Scribble** and **NotDefined**.

### **Deprecated Methods**
**PUT fromHtml** method is deprecated and will be deleted since 21.4 release. Use **POST fromHtml** method for both creating presentations and adding slides to it.

**slideSize** resource is deprecated and will be deleted since 21.4 release. Use **slideProperties** resource instead.
