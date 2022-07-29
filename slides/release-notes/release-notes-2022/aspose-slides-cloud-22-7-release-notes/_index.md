---
title: "Aspose.Slides Cloud 22.7 Release Notes"
type: docs
url: /aspose-slides-cloud-22-7-release-notes/
weight: 60
---

## **Important Changes and Enhancements**

- **SLIDESCLOUD-988** Add methods to modify chart visual elements - axes, legends & walls
- **SLIDESCLOUD-1477** Extracting slide notes with keeping content formatting
- **SLIDESCLOUD-1507** Removing unused master slides
- **SLIDESCLOUD-1509** Merging presentations via specified URL

## **Other Improvements and Changes**

- **SLIDESCLOUD-1510** ReorderSlides returns wrong result
- **SLIDESCLOUD-1520** API response is inconsistent on POST to /slides/{name}/Png
- **SLIDESCLOUD-1504** Layout slide name does not work when adding a new slide

## **Public API changes**

Added new **SetChartAxis**, **SetChartLegend**, **SetChartWall** to modify chart elements more conveniently. See [documentation](/slides/setting-chart-axis/) for more info.

Added new **DeleteUnusedMasterSlides** and **DeleteUnusedMasterSlidesOnline** methods. See [documentation](/slides/deleting-unused-masterslides/) for more info.

Added **Url** to the list of allowed values for **PresentationToMerge.SourceEnum** enum. You can now merge presentations from external URLs. See [documentation](/slides/merging-presentations-from-various-sources-into-a-local-file/) for more info.

Added **Html**, **Pdf**, **Xps**, **Pptx**, **Odp**, **Otp**, **Ppt**, **Pps**, **Ppsx**, **Pptm**, **Ppsm**, **Potx**, **Pot**, **Potm**, **Svg**, **Fodp**, **Xaml**, **Html5** to the list of allowed values for **SlideExportFormat** enum. You can now export slide notes to those formats.

Added **Html5** to the list of allowed values for **SlideExportFormat** enum. You can now export individual slides to HTML5.
