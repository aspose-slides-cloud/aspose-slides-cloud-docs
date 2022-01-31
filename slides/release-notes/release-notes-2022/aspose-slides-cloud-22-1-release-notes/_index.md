---
title: "Aspose.Slides Cloud 22.1 Release Notes"
type: docs
url: /aspose-slides-cloud-22-1-release-notes/
weight: 10
---

## **Improvements and Changes**

- **SLIDESCLOUD-1324** Support export to GIF
- **SLIDESCLOUD-1323** Support convert to XAML
- **SLIDESCLOUD-940** Support math formulas
- **SLIDESCLOUD-991** Support export of formulas to MathML
- **SLIDESCLOUD-636** Support alternating hyperlinks
- **SLIDESCLOUD-1319** Support editing shape points
- **SLIDESCLOUD-1321** Support align shapes in group shape
- **SLIDESCLOUD-1347** Allow PDF as input format for merge operations
- **SLIDESCLOUD-1320** Support new AudioShape & VideoShape Properties
- **SLIDESCLOUD-1269** Background Missing of the table after split and merged it on single file
- **SLIDESCLOUD-1355** FillFormat is not properly deserialized in Go SDK

## **Public API changes**
Added **Gif** and **Xaml** to the list of allowed values for **ExportFormat** type. You can now convert presentations to Gif and Xaml.

A new **MathParagraph** property is added to **Portion** object. It allows to read & modify equations (math formulas) using cloud API. See [documentation](/slides/working-with-math-formulas/) for more info.

You can now export math formulas to MathML format using **mathml** subresource of **portion** resource. See [documentation](/slides/export-to-mathml/) for more info.

New **HyperlinkClick** and **HyperlinkMouseOver** properties of **ShapeBase** and **Portion** formats allow to manipulate hyperlinks on your presentation. It allows to export math formulas to MathML format. See [documentation](/slides/working-with-hyperlinks/) for more info.

New **geometryPath** subresource of **shape** resource allows to use custom lines for your geometry shapes. See [documentation](/slides/working-with-geometry-paths/) for more info.

**align** resource is now available for subshapes.

New **PlayAcrossSlides** and **RewindAudio** properties are added to **AudioFrame** object.

Added **InClickSequence** to the list of allowable values for **AudioPlayModePreset** and **AudioPlayModePreset** enum types.
