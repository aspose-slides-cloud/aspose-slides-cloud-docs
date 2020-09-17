---
title: "Aspose.Slides Cloud 20.7 Release Notes"
type: docs
url: /aspose-slides-cloud-20-7-release-notes/
weight: 10
---

{{% alert color="primary" %}} 

The page contains release notes for Aspose.Slides Cloud 20.7 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}} 
## **New features and enhancements**


- SLIDESCLOUD-985 Add methods to modify chart series
- SLIDESCLOUD-981 Portion list should return portion contents, not just portion links
## **Other improvements and changes**


- SLIDESCLOUD-971 - Unresolved reference error using .NET Core SDK
- SLIDESCLOUD-969 - Portion with unspecified text causes null reference exception
- SLIDESCLOUD-922 - Make ShapeIndex nullable for animation GET method in SDKs
## **Public API changes**

### **Series resource**
The new resource is a subresource of **shape**. It works only for Chart shapes and allows to add, modify & delete chart series.
#### **Example 1 (Add series to a chart)**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/series?folder=myFolder
```

***Request body:***

```
{ "dataPointType": "OneValue", "dataPoints": [{ "value": 5.5 }, { "value": 76 }, { "value": 27 }] }
```

***SDK Code:***

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
OneValueSeries dto = new OneValueSeries();
dto.DataPoints = new List<OneValueChartDataPoint>();
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 5.5 });
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 76 });
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 27 });
PostChartSeriesRequest request = new PostChartSeriesRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 1,
    ShapeIndex = 1,
    Series = dto
};
Chart chart = api.PostChartSeries(request);
Console.WriteLine(chart.Series.Count);
```

#### **Example 2 (Update chart series)**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/series/2?folder=myFolder
```

***Request body:***

```
{ "dataPointType": "OneValue", "dataPoints": [{ "value": 5.5 }, { "value": 76 }, { "value": 27 }] }
```

***SDK Code:***

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
OneValueSeries dto = new OneValueSeries();
dto.DataPoints = new List<OneValueChartDataPoint>();
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 5.5 });
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 76 });
dto.DataPoints.Add(new OneValueChartDataPoint { Value = 27 });
PutChartSeriesRequest request = new PutChartSeriesRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 1,
    ShapeIndex = 1,
    SeriesIndex = 2,
    Series = dto
};
Chart chart = api.PutChartSeries(request);
Console.WriteLine(((OneValueSeries)chart.Series[1]).DataPoints.Count);
```
#### **Example 3 (Delete chart series)**
```
DELETE https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/series/2?folder=myFolder
```

***SDK Code:***

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
DeleteChartSeriesRequest request = new DeleteChartSeriesRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 1,
    ShapeIndex = 1,
    SeriesIndex = 2
};
Chart chart = api.DeleteChartSeries(request);
Console.WriteLine(chart.Series.Count);
```
### **PortionList property**
*Paragraph* class now has *PortionList* property which allows us to retrieve text and other properties for paragraph portions.
Similarly, *Portions* class now has *Items* property of the same kind.
