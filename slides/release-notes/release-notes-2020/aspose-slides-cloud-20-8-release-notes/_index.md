---
title: "Aspose.Slides Cloud 20.8 Release Notes"
type: docs
url: /aspose-slides-cloud-20-8-release-notes/
weight: 9
---

{{% alert color="primary" %}} 

The page contains release notes for Aspose.Slides Cloud 20.8 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}} 
## **New features and enhancements**


- SLIDESCLOUD-987 Add methods to modify chart categories
- SLIDESCLOUD-986 Add methods to modify chart data points
## **Other improvements and changes**


- SLIDESCLOUD-975 Support type inheritance in Ruby SDK
- SLIDESCLOUD-936 Support ISaveOptions.DefaultRegularFont
- SLIDESCLOUD-519 Tabs in textboxes are ignored
## **Public API changes**

### **1. Categories of resource**
The new resource is a subresource of **shape**. It works only for Chart shapes and allows to add, modify & delete chart series.
#### **Example 1 (Add category to a chart)**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/categories?folder=myFolder
```

***Request body:***

```
{ "value": "NewCategory", "dataPoints": [{ "value": 5.5 }, { "value": 76 }, { "value": 27 }] }
```

***SDK Code:***

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
ChartCategory dto = new ChartCategory
{
    Value = "NewCategory",
    DataPoints = new List<OneValueChartDataPoint>
    {
        new OneValueChartDataPoint { Value = 5.5 },
        new OneValueChartDataPoint { Value = 76 },
        new OneValueChartDataPoint { Value = 27 }
    }
};
PostChartCategoryRequest request = new PostChartCategoryRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 1,
    ShapeIndex = 1,
    Category = dto
};
Chart chart = api.PostChartCategory(request);
Console.WriteLine(chart.Categories.Count);
```

#### **Example 2 (Update chart category)**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/categories/2?folder=myFolder
```

***Request body:***

```
{ "value": "UpdatedCategory", "dataPoints": [{ "value": 5.5 }, { "value": 76 }, { "value": 27 }] }
```

***SDK Code:***

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
ChartCategory dto = new ChartCategory
{
    Value = "UpdatedCategory",
    DataPoints = new List<OneValueChartDataPoint>
    {
        new OneValueChartDataPoint { Value = 5.5 },
        new OneValueChartDataPoint { Value = 76 },
        new OneValueChartDataPoint { Value = 27 }
    }
};
PutChartCategoryRequest request = new PutChartCategoryRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 1,
    ShapeIndex = 1,
    CategoryIndex = 2,
    Category = dto
};
Chart chart = api.PutChartCategory(request);
Console.WriteLine(chart.Categories.Count);
```
#### **Example 3 (Delete chart category)**
```
DELETE https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/categories/2?folder=myFolder
```

***SDK Code:***

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
DeleteChartCategoryRequest request = new DeleteChartCategoryRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 1,
    ShapeIndex = 1,
    CategoryIndex = 2
};
Chart chart = api.DeleteChartCategory(request);
Console.WriteLine(chart.Categories.Count);
```

### **2. dataPoints resource**
The new resource is a subresource of **series**. It works only for Chart shapes and allows us to add, modify & delete individual data points.

#### **Example 1 (Add a data point to a chart series)**
This works with scatter & bubble series. You cannot create a data point for a one-value series without creating a relevant category.
```
POST https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/series/2/dataPoints?folder=myFolder
```

***Request body:***
```
{ "XValue": 5.5, "YValue": 8 }
```

***SDK Code:***
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
ScatterChartDataPoint dto = new ScatterChartDataPoint
{
 XValue = 5.5,
 YValue = 8
};
PostChartDataPointRequest request = new PostChartDataPointRequest
{
 Name = "myPresentaion.pptx",
 Folder = "myFolder",
 SlideIndex = 1,
 ShapeIndex = 1,
 SeriesIndex = 2,
 DataPoint = dto
};
Chart chart = api.PostChartDataPoint(request);
Console.WriteLine(((ScatterSeries)chart.Series[1]).DataPoints.Count);
```

#### **Example 2 (Update chart data point)**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/series/2/dataPoints/2?folder=myFolder
```

***Request body:***
```
{ "XValue": 5.5, "YValue": 8 }
```

***SDK Code:***
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
ScatterChartDataPoint dto = new ScatterChartDataPoint
{
 XValue = 5.5,
 YValue = 8
};
PutChartDataPointRequest request = new PutChartDataPointRequest
{
 Name = "myPresentaion.pptx",
 Folder = "myFolder",
 SlideIndex = 1,
 ShapeIndex = 1,
 SeriesIndex = 2,
 PointIndex = 2,
 DataPoint = dto
};
Chart chart = api.PutChartDataPoint(request);
Console.WriteLine(((ScatterSeries)chart.Series[1]).DataPoints[1].XValue); //5.5
```

#### **Example 3 (Delete chart data point)**
```
DELETE https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/1/shapes/1/series/2/dataPoints/2?folder=myFolder
```

***SDK Code:***
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
DeleteChartDataPointRequest request = new DeleteChartDataPointRequest
{
 Name = "myPresentaion.pptx",
 Folder = "myFolder",
 SlideIndex = 1,
 ShapeIndex = 1,
 SeriesIndex = 2,
 PointIndex = 2
};
Chart chart = api.DeleteChartDataPoint(request);
Console.WriteLine(((ScatterSeries)chart.Series[1]).DataPoints.Count);
```

### **3. DefaultRegularFont property**
**ExportOptions** class now has **DefaultRegularFont** property which allows us to specify the default font to substitute a custom font in case it is not available.

#### **Example**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/pdf?folder=myFolder
```

***Request body:***
```
{ "DefaultRegularFont": "Calibri" }
```

***SDK Code:***
```csharp

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSlidesSaveAsRequest request = new PostSlidesSaveAsRequest
{
 Name = "myPresentaion.pptx",
 Folder = "myFolder",
 Format = ExportFormat.Pdf,
 Options = new PdfExportOptions { DefaultRegularFont = "Calibri" }
};
Stream response = api.PostSlidesSaveAs(request);
response.CopyTo(File.Create("myPresentation.pdf"));
```

