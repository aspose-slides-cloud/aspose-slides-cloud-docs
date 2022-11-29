---
title: "Aspose.Slides Cloud 22.11 Release Notes"
type: docs
url: /aspose-slides-cloud-22-11-release-notes/
weight: 20
---

## **Improvements and Changes**

- **SLIDESCLOUD-1511** Provide access to chart spreadsheet for cloud users
- **SLIDESCLOUD-942** Support getting & setting chart data spreadsheet formulas
- **SLIDESCLOUD-1587** Add option to SDKs to enable insecure requests
- **SLIDESCLOUD-1593** Add UseFrameSize and UseFrameRotation properties to SvgExportOptions
- **SLIDESCLOUD-1596** Enable InputBuffer as a valid input value for binary parameters in python SDK
- **SLIDESCLOUD-1563** SVG shape is imported with incorrect stroke width
- **SLIDESCLOUD-976** Pie chart series get mixed after saving
- **SLIDESCLOUD-1590** Subshape error handling issues

## **Public API changes**

You can now specify data sources for chart elements. This is done with new **DataSource** type which is used with propertries **Chart.DataSourceForCategories**, **Series.DataSourceForName**, **OneValueSeries.DataSourceForValues**, **XYSeries.DataSourceForXValues**, **XYSeries.DataSourceForYValues**, **BubbleSeries.DataSourceForBubbleSizeValues**. See [documentation](/slides/setting-chart-data-source/) for more info.

You can now specify formulas for data points using new properties **OneValueChartDataPoint.ValueFormula**, **ScatterChartDataPoint.XValueFormula**, **ScatterChartDataPoint.YValueFormula**, **BubbleChartDataPoint.BubbleSizeFormula**. See [documentation](/slides/working-with-formulas/) for more info.

Added boolean **UseFrameSize** and **UseFrameRotation** properties to **SvgExportOptions** class.
