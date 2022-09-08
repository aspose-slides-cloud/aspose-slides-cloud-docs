---
title: "Working with Special Slide Shape Paragraphs in a PowerPoint Presentation"
type: docs
url: /working-with-special-slide-shape-paragraphs-in-a-powerpoint-presentation/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud API allows you to read, add, modify and delete special (notes, master, layout) slide shape paragraphs in a PowerPoint Presentation. A set of methods identical to those that work with ordinary slides can be used to do that.
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs|GET|Read slide shape paragraphs information|[GetSpecialSlideParagraph](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlideParagraphs)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|GET|Read slide shape paragraph information|[GetSpecialSlideParagraph](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlideParagraph)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs|POST|Add a new paragraph to the slide shape|[CreateSpecialSlideParagraph](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/CreateSpecialSlideParagraph)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|PUT|Update a paragraph in the slide shape|[UpdateSpecialSlideParagraph](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/UpdateSpecialSlideParagraph)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs|DELETE|Delete a portion from the slide shape|[DeleteSpecialSlideParagraph](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlideParagraph)|

The following examples demonstrate manipulating master slide shape paragraphs. You can access layout or notes slide shape paragraphs the same way, just change the value of **slideType** parameter accordingly.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

**Get Paragraph List**

```java

curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Add Paragraph**

```java

curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs" -d "@paragraph.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Update Paragraph**

```java

curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/6" -d "@paragraph.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Delete Paragraph**

```java

curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Simple paragraph.json example**

```javascript
{
    "alignment": "Center",
    "portions": {
        "text": "New paragraph"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "alignment": "Center",
    "depth": 2,
    "portionList": [
        {
            "text": "New paragraph",
            "fontHeight": 20.0,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions/1",
                "relation": "self"
            }
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
string fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Paragraphs paragraphs = api.GetSpecialSlideParagraphs(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeIndex);
int paragraphCount = paragraphs.ParagraphLinks.Count;

Paragraph dto = new Paragraph
{
    Alignment = Paragraph.AlignmentEnum.Right,
    PortionList = new List<Portion>
    {
        new Portion { Text = "New paragraph" }
    }
};
Paragraph paragraph = api.CreateSpecialSlideParagraph(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeIndex, dto);
Console.WriteLine(paragraph.Alignment); //Right

dto.Alignment = Paragraph.AlignmentEnum.Center;
paragraph = api.UpdateSpecialSlideParagraph(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeIndex, paragraphCount + 1, dto);
Console.WriteLine(paragraph.Alignment); //Center

api.DeleteSpecialSlideParagraph(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeIndex, paragraphCount + 1);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Paragraphs paragraphs = api.getSpecialSlideParagraphs(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeIndex, null, null, null);
int paragraphCount = paragraphs.getParagraphLinks().size();

Paragraph dto = new Paragraph();
dto.setAlignment(Paragraph.AlignmentEnum.RIGHT);
List<Portion> portions = new ArrayList<Portion>();
Portion portion = new Portion();
portion.setText("New paragraph");
portions.add(portion);
dto.setPortionList(portions);
Paragraph paragraph = api.createSpecialSlideParagraph(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeIndex, dto, null, null, null, null);
System.out.println(paragraph.getAlignment()); //Right

dto.setAlignment(Paragraph.AlignmentEnum.CENTER);
paragraph = api.updateSpecialSlideParagraph(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeIndex, paragraphCount + 1, dto, null, null, null);
System.out.println(paragraph.getAlignment()); //Center

api.deleteSpecialSlideParagraph(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeIndex, paragraphCount + 1, null, null, null);
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Paragraph;
use Aspose\Slides\Cloud\Sdk\Model\Portion;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$paragraphs = $api->GetSpecialSlideParagraphs($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeIndex);
$paragraphCount = count($paragraphs->getParagraphLinks());

$dto = new Paragraph();
$dto->setAlignment("Right");
$portion = new Portion();
$portion->setText("New paragraph");
$dto->setPortionList([ $portion ]);
$paragraph = $api->CreateSpecialSlideParagraph($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeIndex, $dto);
print($paragraph->getAlignment()); //Right

$dto->setAlignment("Center");
$paragraph = $api->UpdateSpecialSlideParagraph($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeIndex, $paragraphCount + 1, $dto);
print($paragraph->getAlignment()); //Center

$api->DeleteSpecialSlideParagraph($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeIndex, $paragraphCount + 1);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.paragraph import Paragraph
from asposeslidescloud.models.portion import Portion

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
paragraphs = api.get_special_slide_paragraphs(file_name, slide_index, 'masterSlide', shape_index)
paragraph_count = len(paragraphs.paragraph_links)

dto = Paragraph()
dto.alignment = "Right"
portion = Portion()
portion.text = "New paragraph"
dto.portion_list = [ portion ]
paragraph = api.create_special_slide_paragraph(file_name, slide_index, 'masterSlide', shape_index, None, dto)
print(paragraph.alignment) #Right

dto.alignment = "Center"
paragraph = api.update_special_slide_paragraph(file_name, slide_index, 'masterSlide', shape_index, paragraph_count + 1, dto)
print(paragraph.alignment) #Center

api.delete_special_slide_paragraph(file_name, slide_index, 'masterSlide', shape_index, paragraph_count + 1)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
const shapeIndex = 2;
api.getSpecialSlideParagraphs(fileName, slideIndex, CloudSdk.SpecialSlideType.MasterSlide, shapeIndex).then((result) => {
    const paragraphCount = result.body.paragraphLinks.length;
    var dto = new CloudSdk.Paragraph();
    dto.alignment = "Right";
    const portion = new CloudSdk.Portion();
    portion.text = "New paragraph";
    dto.portionList = [ portion ];
    api.createSpecialSlideParagraph(fileName, slideIndex, CloudSdk.SpecialSlideType.MasterSlide, shapeIndex, dto).then((postResult) => {
        console.log(postResult.body.alignment); //Right
        dto = new CloudSdk.Paragraph();
        dto.alignment = "Center";
        api.updateSpecialSlideParagraph(fileName, slideIndex, CloudSdk.SpecialSlideType.MasterSlide, shapeIndex, paragraphCount + 1, dto).then((putResult) => {
            console.log(putResult.body.alignment); //Center
            api.deleteSpecialSlideParagraph(fileName, slideIndex, CloudSdk.SpecialSlideType.MasterSlide, shapeIndex, paragraphCount + 1);
        });
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
var slideIndex int32 = 1
var shapeIndex int32 = 2

paragraphs, _, e := c.SlidesApi.GetSpecialSlideParagraphs(fileName, slideIndex, "masterSlide", shapeIndex, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
paragraphCount := len(portions.getParagraphLinks())

dto := NewParagraph()
dto.Alignment = "Right"
portion := NewPortion()
portion.Text = "New paragraph"
dto.PortionList = []IPotrion { portion }
paragraph, _, e := c.SlidesApi.CreateSpecialSlideParagraph(fileName, slideIndex, "masterSlide", shapeIndex, dto, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", portion.getAlignment()) //Right

dto = NewParagraph()
dto.Alignment = "Center"
paragraph, _, e = c.SlidesApi.UpdateSpecialSlideParagraph(fileName, slideIndex, "masterSlide", shapeIndex, paragraphCount + 1, dto, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", portion.getAlignment()) //Center

_, _, e = c.SlidesApi.DeleteSpecialSlideParagraph(fileName, slideIndex, "masterSlide", shapeIndex, paragraphCount + 1, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
