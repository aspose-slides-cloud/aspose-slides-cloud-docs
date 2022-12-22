---
title: "Aspose.Slides Cloud 22.12 Release Notes"
type: docs
url: /aspose-slides-cloud-22-12-release-notes/
weight: 10
---

## **Improvements and Changes**

- **SLIDESCLOUD-1603** Add explicit "Type" property to the DataPoint class
- **SLIDESCLOUD-1614** Spreadsheet, row & column indexed must be 1-based
- **SLIDESCLOUD-1606** Chart creation issues

## **Public API changes**

Added **Type** property to **DataPoint** class. You should specify it for methods that work with individual chart data points (**CreateDataPoint** &amp; **UpdateDataPoint**). Nothing has changed if you use a Cloud SDK.
