---
title: "Aspose.Slides Cloud 20.9 Release Notes"
type: docs
url: /aspose-slides-cloud-20-9-release-notes/
weight: 10
---

{{% alert color="primary" %}}

The page contains release notes for Aspose.Slides Cloud 20.9 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}}
## **New features and enhancements**


- SLIDESCLOUD-934 Support presentation sections
- SLIDESCLOUD-464 Support header and footer management

## **Other improvements and changes**

-     SLIDESCLOUD-994 Enable category management for Sunburst & treemap charts
## **Public API changes**

### **1. sections resource**
The new resource is a subresource of presentation. It allows to get and modify presentation sections.
#### **Example 1 (Get presentation sections)**
```
GET https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/sections?folder=myFolder
```

***SDK Code:***

```
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
GetSectionsRequest request = new GetSectionsRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder"
};
Sections sections = api.GetSections(tequest);
Console.WriteLine(sections.SectionList.Count);
```

#### **Example 2 (Set presentation sections)**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/sections?folder=myFolder
```

***Request body:***

```
{ "sectionList": [{ "name": "Section1", "firstSlideIndex": 1 }, { "name": "Section2", "firstSlideIndex": 4 }]}
```

***SDK Code:***

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
Sections dto = new Sections
{
    SectionList = new List<Section>
    {
        new Section { Name = "Section1", FirstSlideIndex = 1 },
        new Section { Name = "Section2", FirstSlideIndex = 4 }
    }
};
PutSectionsRequest request = new PutSectionsRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    Sections = dto
};
Sections sections = api.PutSections(request);
Console.WriteLine(sections.SectionList.Count); //2
Console.WriteLine(sections.SectionList[0].SlideList.Count); //3
```
#### **Example 3 (Create a new section)**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/sections?folder=myFolder&sectionName=NewSection&slideIndex=4
```

***SDK Code:***

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSectionRequest request = new PostSectionRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SectionName = "NewSection",
    SlideIndex = 4
};
Sections sections = api.PostSection(request);
Console.WriteLine(sections.SectionList.Count);
```

#### **Example 4 (Change section name)**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/sections/2?folder=myFolder&sectionName=UpdatedSection
```

***SDK Code:***
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PutSectionRequest request = new PutSectionRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SectionName = "UpdatedSection",
    SectionIndex = 2
};
Sections sections = api.PutSection(request);
Console.WriteLine(sections.SectionList[1].Name); //UpdatedSection
```

#### **Example 5 (Move section and its slides to another position)**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/sections/1/move?folder=myFolder&newPosition=2
```

***SDK Code:***
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSectionMoveRequest request = new PostSectionMoveRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SectionIndex = 1,
    NewPosition = 2
};
Sections sections = api.PostSectionMove(request);
Console.WriteLine(sections.SectionList.Count);
```

#### **Example 6 (Delete a section)**
```
DELETE https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/sections/2?folder=myFolder
```

***SDK Code:***
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
DeleteSectionRequest request = new DeleteSectionRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SectionIndex = 2
};
Sections sections = api.DeleteSection(request);
Console.WriteLine(sections.SectionList.Count);
```

### **2. HeaderFooter Resource**
The new resource is a subresource of presentation, slide and notesSlide resources. It allows to get & set header & footer info about slides and notes slides.
#### **Example 1 (Set footer for all slides)**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/headerFooter?folder=myFolder
```

***Request body:***
```
{ "isFooterVisible": true, "footerText": "footer", "isDateTimeVisible": false }
```

***SDK Code:***
```csharp

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PutSlidesHeaderFooterRequest request = new PutSlidesHeaderFooterRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    Dto = new HeaderFooter
    {
        IsFooterVisible = true,
        FooterText = "footer",
        IsDateTimeVisible = false
    }
};
api.PutSlidesHeaderFooter(request);
```

#### **Example 2 (Set footer for a slide)**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/2/headerFooter?folder=myFolder
```

***Request body:***
```
{ "isFooterVisible": true, "footerText": "footer", "isDateTimeVisible": false }
```

***SDK Code:***
```csharp

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PutSlideHeaderFooterRequest request = new PutSlideHeaderFooterRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 2,
    Dto = new HeaderFooter
    {
        IsFooterVisible = true,
        FooterText = "footer",
        IsDateTimeVisible = false
    }
};
HeaderFooter headerFooter = api.PutSlidesHeaderFooter(request);
Console.WriteLine(headerFooter.IsFooterVisible);
Console.WriteLine(headerFooter.IsDateTimeVisible);
```

#### **Example 3 (Set footer for a notes slide)**
```
PUT https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/2/notesSlide/headerFooter?folder=myFolder
```

***Request body:***
```
{ "isHeaderVisible": true, "headerText": "header", "isDateTimeVisible": false }
```

***SDK Code:***
```csharp

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PutNotesSlideHeaderFooterRequest request = new PutNotesSlideHeaderFooterRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 2,
    Dto = new NotesSlideHeaderFooter
    {
        IsHeaderVisible = true,
        HeaderText = "header",
        IsDateTimeVisible = false
    }
};
HeaderFooter headerFooter = api.PutNotesSlideHeaderFooter(request);
Console.WriteLine(headerFooter.IsHeaderVisible);
Console.WriteLine(headerFooter.IsDateTimeVisible);
```
### **3. Level and ParentCategories property of ChartCategory class**
These new properties are used to build with hierarchic (Sunburst & Treemap) diagrams.
Categories property of ChartCategory class is no longer available.
#### **Example**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentaion.pptx/slides/2/shapes?folder=myFolder
```

***Request body:***
```
{
    "chartType": "Sunburst",
    "width": 400,
    "height": 300,
    "categories": [
        { "value": "Leaf1", "level": 3, "parentCategories": [ "Branch1", "Stem1" ] },
        { "value": "Leaf2", "level": 3, "parentCategories": [ "Branch1", "Stem1" ] },
        { "value": "Branch2", "level": 2, "parentCategories": [ "Stem1" ] },
        { "value": "Stem2", "level": 1 }],
    "series": [
        {
            "name": "Series1",
            "dataPoints": [ { "value": 40 }, { "value": 50 }, { "value": 70 }, { "value": 80 } ]
        }]
    }
```

***SDK Code:***
```csharp

SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostAddNewShapeRequest request = new PostAddNewShapeRequest
{
    Name = "myPresentaion.pptx",
    Folder = "myFolder",
    SlideIndex = 2,
    Dto = new Chart
    {
        ChartType = Chart.ChartTypeEnum.Sunburst,
        Width = 400,
        Height = 300,
        Categories = new List<ChartCategory>
        {
            new ChartCategory { Value = "Leaf1", Level = 3, ParentCategories = new List<string> { "Branch1", "Stem1" } },
            new ChartCategory { Value = "Leaf2", Level = 3, ParentCategories = new List<string> { "Branch1", "Stem1" } },
            new ChartCategory { Value = "Branch2", Level = 2, ParentCategories = new List<string> { "Stem1" } },
            new ChartCategory { Value = "Stem2", Level = 1 }
        },
        Series = new List<Series>
        {
            new OneValueSeries
            {
                Name = "Series1",
                DataPoints = new List<OneValueChartDataPoint>
                {
                    new OneValueChartDataPoint { Value = 40 },
                    new OneValueChartDataPoint { Value = 50 },
                    new OneValueChartDataPoint { Value = 70 },
                    new OneValueChartDataPoint { Value = 80 }
                }
            }
        }
    }
};
Chart chart = TestUtils.SlidesApi.PostAddNewShape(request) as Chart;
Console.WriteLine(chart.Categories.Count); //4
```
