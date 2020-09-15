---
title: "Aspose.Slides for Cloud 17.10 Release Notes"
type: docs
url: /aspose-slides-for-cloud-17-10-release-notes/
weight: 20
---

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|SLIDESCLOUD-311|Enable saving slide in SVG format|Feature|
|SLIDESCLOUD-312|SmartArt shape management|Feature|
|SLIDESCLOUD-313|Support properties of Chart & ChartSeries|Feature|
|SLIDESCLOUD-314|Enable adding and deleting shapes to (from) a GroupShape|Feature|
|SLIDESCLOUD-315|Delete shapes|Feature|
|SLIDESCLOUD-316|Cell formatting|Feature|
|SLIDESCLOUD-297|[Use Aspose.Slides for .NET 17.10 features](https://docs.aspose.com/display/slidesnet/Aspose.Slides+for+.NET+17.10+Release+Notes)|Feature|
## **Public API Changes**
- **nodes** and **node** resources are added to support SmartArt shape management.
  - **nodes** is available as a subresource of **shape** (only for SmartArt shapes) and **node** resources. It represents a node list for a SmartArt shape or a SmartArt shape node. No methods are supported for this resource; it can only be used with **node** subresource.
  - **node** is available as a subresource of **nodes** resource. It represents a SmartArt shape node. No methods are supported for this resource; it can only be used with **nodes** or **shapes** subresource.
- POST method of **shapes** resource supports adding shapes to a group shape.
- DELETE method is added to **shape** resource to delete a shape from a list of shapes in a slide or a group shape.
- **svg** is added to valid values of **format** parameter for **slide** resources and for **Save** task of the **pipeline** resource. It allows to save or download a slide in Scalable Vector Graphics format.
- **SideWall**, **BackWall**, **Floor**, **Legend**, **Axes** and **PlotArea** properties are added to Chart type. They allow to get and set chart walls, legend, axes & plot area formatting & other properties.
- **Smooth**, **PlotOnSecondAxis**, **Order**, **NumberFormatOfYValues**, **NumberFormatOfXValues**, **NumberFormatOfValues**, **NumberFormatOfBubbleSizes**, **InvertIfNegative**, **Explosion**, **Marker**, **FillFormat**, **EffectFormat** and **LineFormat** properties are added to **Series** type. They allow to get and set chart series properties.
- **MarginTop**, **MarginRight**, **MarginLeft**, **MarginBottom**, **TextAnchorType**, **TextVerticalType**, **FillFormat**, **BorderTop**, **BorderRight**, **BorderLeft**, **BorderBottom**, **BorderDiagonalUp** and **BorderDiagonalDown** properies are added to **Cell** type. They allow to get and set table cell properties.
