---
title: "Working with Special Slide Shape Paragraph Portions in a PowerPoint Presentation"
type: docs
url: /working-with-special-slide-shape-paragraph-portions-in-a-powerpoint-presentation/
weight: 30
---

## **Introduction**
Aspose.Slides Cloud API allows you to read, add, modify and delete special (notes, master, layout) slide shape paragraph portions in a PowerPoint Presentation. A set of methods identical to those that work with ordinary slides can be used to do that.
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|GET|Read slide shape paragraph portions information|[GetSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlidePortions)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|GET|Read slide shape paragraph portion information|[GetSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlidePortion)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|POST|Add a new portion to the slide shape paragraph|[CreateSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/CreateSpecialSlidePortion)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|PUT|Update a portion in the slide shape paragraph|[UpdateSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/UpdateSpecialSlidePortion)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|DELETE|Delete a portion from the slide shape paragraph|[DeleteSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlidePortion)|

The following examples demonstrate manipulating master slide shape paragraph portions. You can access layout or notes slide shape paragraph portions the same way, just change the value of **slideType** parameter accordingly.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

**Get Portion List**

```java

curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Add Portion**

```java

curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions" -d "@portion.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Update Portion**

```java

curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions/2" -d "@portion.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Delete Portion**

```java

curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions/2" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Simple portion.json example**

```javascript
{
    "fontBold": "True",
    "fontHeight": 22,
    "text": "New portion"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "text": "New portion",
    "fontBold": "True",
    "fontHeight":22.0,
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions/1",
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
int paragraphIndex = 3;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Portions portions = api.GetSpecialSlidePortions(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeIndex, paragraphIndex);
int portionCount = portions.Items.Count;

Portion dto = new Portion
{
    FontBold = Portion.FontBoldEnum.True,
    Text = "New portion"
};
Portion portion = api.CreateSpecialSlidePortion(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeIndex, paragraphIndex, dto);
Console.WriteLine(portion.FontBold); //True
Console.WriteLine(portion.Text); //New portion

dto = new Portion
{
    FontHeight = 22,
    Text = "Updated portion"
};
portion = api.UpdateSpecialSlidePortion(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeIndex, paragraphIndex, portionCount + 1, dto);
Console.WriteLine(portion.FontBold); //True
Console.WriteLine(portion.FontHeight); //22.0
Console.WriteLine(portion.Text); //Updated portion

api.DeleteSpecialSlidePortion(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeIndex, paragraphIndex, portionCount + 1);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
int paragraphIndex = 3;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Portions portion = api.getSpecialSlidePortions(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeIndex, paragraphIndex);
int portionCount = paragraphs.getItems().size();

Portion dto = new Portion();
dto.setFontBold(Portion.FontBoldEnum.TRUE);
dto.setText("New portion");
Portion portion = api.createSpecialSlidePortion(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeIndex, paragraphIndex, null, dto);
System.out.println(portion.getFontBold()); //True
System.out.println(portion.getText()); //New portion

dto.setFontHeight(22.0);
dto.setText("Updated portion");
portion = api.updateSpecialSlidePortion(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeIndex, paragraphIndex, portionCount + 1, dto);
System.out.println(portion.getFontBold()); //True
System.out.println(portion.getFontHeight()); //22.0
System.out.println(portion.getText()); //Updated portion

api.deleteSpecialSlidePortion(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeIndex, paragraphIndex, portionCount + 1);
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Portion;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$paragraphIndex = 3;
$portions = api->GetSpecialSlidePortion($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeIndex, $paragraphIndex);
$portionCount = count($portion->getItems());

$dto = new Portion();
$dto->setFontBold("True");
$dto->setText("New portion");
$portion = $api->CreateSpecialSlidePortion($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeIndex, $paragraphIndex, null, $dto);
print($portion->getFontBold()); //True
print($portion->getText()); //New portion

$dto = new Portion();
$dto->setFontHeight(22);
$dto->setText("Updated portion");
$portion = $api->UpdateSpecialSlidePortion($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeIndex, $paragraphIndex, $portionCount + 1, $dto);
print($portion->getFontBold()); //True
print($portion->getFontHeight()); //22.0
print($portion->getText()); //Updated portion

$api->DeleteSpecialSlidePortion($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeIndex, $paragraphIndex, $portionCount + 1);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.portion import Portion

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
paragraph_index = 3
portions = api.get_special_slide_portions(file_name, slide_index, 'masterSlide', shape_index, paragraph_index)
portion_count = len(portions.items)

dto = Portion()
dto.font_bold = "True"
dto.text = "New portion"
portion = api.create_special_slide_portion(file_name, slide_index, 'masterSlide', shape_index, paragraph_index, None, dto)
print(portion.font_bold) #True
print(portion.text) #New portion

dto = Portion()
dto.font_alignment = 22
dto.text = "Updated portion"
portion = api.update_special_slide_portion(file_name, slide_index, 'masterSlide', shape_index, paragraph_index, portion_count + 1, dto)
print(portion.font_bold) #True
print(portion.font_alignment) #22.0
print(portion.text) #Updated portion

api.delete_special_slide_portion(file_name, slide_index, 'masterSlide', shape_index, paragraph_index, portion_count + 1)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
const shapeIndex = 2;
const paragraphIndex = 3;
api.getSpecialSlidePortions(fileName, slideIndex, CloudSdk.SpecialSlideType.MasterSlide, shapeIndex, paragraphIndex).then((result) => {
    const portionCount = result.body.items.length;
    var dto = new CloudSdk.Portion();
    dto.fontBold(CloudSdk.Portion.FontBoldEnum.True);
    dto.text = "New portion";
    api.createSpecialSlidePortion(fileName, slideIndex, CloudSdk.SpecialSlideType.MasterSlide, shapeIndex, paragraphIndex, null, dto).then((postResult) => {
        console.log(postResult.body.fontBold); //True
        console.log(postResult.body.text); //New portion
        dto = new CloudSdk.Portion();
        dto.fontHeight(22);
        dto.text = "Updated portion";
        api.updateSpecialSlidePortion(fileName, slideIndex, CloudSdk.SpecialSlideType.MasterSlide, shapeIndex, paragraphIndex, portionCount + 1, dto).then((putResult) => {
            console.log(postResult.body.fontBold); //True
            console.log(postResult.body.fontHeight); //22.0
            console.log(postResult.body.text); //Updated portion
            api.deleteSpecialSlidePortion(fileName, slideIndex, CloudSdk.SpecialSlideType.MasterSlide, shapeIndex, paragraphIndex, portionCount + 1);
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
var paragraphIndex int32 = 3

portions, _, e := c.SlidesApi.GetSpecialSlidePortions(fileName, slideIndex, "masterSlide", shapeIndex, paragraphIndex, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
portionCount := len(portions.getItems())

dto := NewPortion()
dto.Text = "New portion"
dto.FontBold = "True"
portion, _, e := c.SlidesApi.CreateSpecialSlidePortion(fileName, slideIndex, "masterSlide", shapeIndex, paragraphIndex, dto, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", portion.getFontBold()) //True
fmt.Printf("Error: %v.", portion.getText()) //New portion

dto = NewPortion()
dto.Text = "Updated portion"
dto.FontHeight = 22
portion, _, e = c.SlidesApi.UpdateSpecialSlidePortion(fileName, slideIndex, "masterSlide", shapeIndex, paragraphIndex, portionCount + 1, dto, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", portion.getFontBold()) //True
fmt.Printf("Error: %v.", portion.getFontHeight()) //22.0
fmt.Printf("Error: %v.", portion.getText()) //Updated portion

_, _, e = c.SlidesApi.DeleteSpecialSlidePortion(fileName, slideIndex, "masterSlide", shapeIndex, paragraphIndex, portionCount + 1, "", "", "")
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
