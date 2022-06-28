---
title: "Aspose.Slides Cloud 22.6 Release Notes"
type: docs
url: /aspose-slides-cloud-22-6-release-notes/
weight: 70
---

## **Important Changes and Enhancements**

- **SLIDESCLOUD-1493** Add Effective boolean paramerter to GetPortion and GetParagraph methods
- **SLIDESCLOUD-1494** Chart series groups supporting
- **SLIDESCLOUD-1487** Checking whether a presentation is password protected

## **Other Improvements and Changes**

- **SLIDESCLOUD-1492** Setting an image background for a slide
- **SLIDESCLOUD-1497** PDF options do not work when converting slide to PDF document
- **SLIDESCLOUD-1496** Slide extraction methods do not zip output HTML document
- **SLIDESCLOUD-1488** Slide is distorted when converting it with notes and comments to PNG
- **SLIDESCLOUD-1484** Width and Height parameters don't work when converting slide to TIFF
- **SLIDESCLOUD-1482** Width and Height properties don't work separately for DownloadSlide method
- **SLIDESCLOUD-1458** BadHttpRequestException: Request body too large
- **SLIDESCLOUD-1450** Azure Function does not run when Aspose.Slides-Cloud is added
- **SLIDESCLOUD-1444** MergeOnline method does not work with file collection created by Arrays.asList
- **SLIDESCLOUD-1271** Enums with undescores are not generated correctly in .NET SDK
- **SLIDESCLOUD-490** Support Chart & Series properties added in Slides.NET 18.7

## **Public API changes**

Added new **effective** subresources for **portion** and **paragraph** resources to retrieve actual format values for paragraphs and portions, whether they are inherited from parent entities or not. See [documentation](/slides/get-paragraph-effective-values/) for more info.

Added new **ChartSeriesGroup** class and **SeriesGroups** property to **Chart** class to enable managing chart series groups. Added new **UpdateChartSeriesGroup** method. See [documentation](/slides/update-chart-series-groups/) for more info.

Password parameter is now optional for **GetProtectionProperties** method. So, you don't need to specify the password to check whether a presentation has a password. See [documentation](/slides/get-protection-properties/) for more info.

Added **HasRoundedCorners** property to **Chart** class.

Added **InvertIfNegative** property to **OneValueChartDataPoint** class.

Changed **FormatScheme** class to return actual format values instead of resource links.
