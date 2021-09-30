---
title: "Working with Special Slide Shapes in a PowerPoint Presentation"
type: docs
url: /working-with-special-slide-shapes-in-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud API allows you to read, add, modify and delete special (master, layout or notes) slide shapes in a PowerPoint Presentation. A set of methods identical to those that work with ordinary slides can be used to do that.
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes|GET|Read slide shapes information|[GetSpecialSlideShapes](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlideShapes)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}|GET|Read slide shape information|[GetSpecialSlideShape](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlideShape)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes|POST|Add a new shape to the slide|[CreateSpecialSlideShape](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/CreateSpecialSlideShape)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}|PUT|Update a shape in the slide|[UpdateSpecialSlideShape](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/UpdateSpecialSlideShape)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes|DELETE|Delete a shape from the slide|[DeleteSpecialSlideShape](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlideShape)|

The following examples demonstrate manipulating master slide shapes. You can access layout or notes slide shapes the same way, just change the value of **slideType** parameter accordingly.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

**Get Shape List**

```java

curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Add Shape**

```java

curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes" -d "@shape.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Update Shape**

```java

curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/6" -d "@shape.json" -H "Content-Type: text/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Delete Shape**

```java

curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw"

```

**Simple shape.json example**

```javascript
{
    "x": 100,
    "y": 100,
    "width": 500,
    "height": 200,
    "shapeType": "Rectangle",
    "text": "New shape"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "type": "Shape",
    "shapeType": "Rectangle",
    "name": "ShapeObject",
    "width": 500.0,
    "height": 200.0,
    "x": 100.0,
    "y":100.0,
    "lineFormat": {
        "alignment": "Center",
        "capStyle": "Flat",
        "dashStyle": "Solid",
        "joinStyle": "Round",
        "style": "Single",
        "miterLimit": 10.0,
        "width": 0.75
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/6",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
string fileName = "MyPresentation.pptx";
int slideIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Shapes shapes = api.GetSpecialSlideShapes(fileName, slideIndex, SpecialSlideType.MasterSlide);
int shapeCount = shapes.ShapesLinks.Count;

Shape dto = new Shape
{
    X = 100,
    Y = 100,
    Width = 500,
    Height = 200,
    ShapeType = GeometryShape.ShapeTypeEnum.Rectangle,
    Text = "New shape"
};
Shape shape = (Shape)api.CreateSpecialSlideShape(fileName, slideIndex, SpecialSlideType.MasterSlide, null, null, dto);
Console.WriteLine(shape.Text); //New shape

dto.Text = "Updated shape";
shape = (Shape)api.UpdateSpecialSlideShape(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeCount + 1, dto);
Console.WriteLine(shape.Text); //Updated shape

api.DeleteSpecialSlideShape(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeCount + 1);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Shapes shapes = api.getSpecialSlideShapes(fileName, slideIndex, SpecialSlideType.MASTERSLIDE);
int shapeCount = shapes.getShapesLinks().size();

Shape dto = new Shape();
dto.setX(100);
dto.setY(100);
dto.setWidth(500);
dto.setHeight(200);
dto.setShapeType(GeometryShape.ShapeTypeEnum.RECTANGLE);
dto.setText("New shape");
Shape shape = (Shape)api.createSpecialSlideShape(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, null, null, dto);
System.out.println(shape.getText()); //New shape

dto.setText("Updated shape");
shape = (Shape)api.updateSpecialSlideShape(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeCount + 1, dto);
System.out.println(shape.getText()); //Updated shape

api.deleteSpecialSlideShape(fileName, slideIndex, SpecialSlideType.MASTERSLIDE, shapeCount + 1);
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Shape;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapes = api->GetSpecialSlideShapes($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE);
$shapeCount = count($shapes->getShapesLinks());

$dto = new Shape();
$dto->setX(100);
$dto->setY(100);
$dto->setWidth(500);
$dto->setHeight(200);
$dto->setShapeType("Rectangle");
$dto->setText("New shape");
$shape = $api->CreateSpecialSlideShape($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, null, null, $dto);
print($shape->getText()); //New shape

$dto->setText("Updated shape");
$shape = $api->UpdateSpecialSlideShape($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeCount + 1, $dto);
print($shape->getText()); //Updated shape

$api->DeleteSpecialSlideShape($fileName, $slideIndex, SpecialSlideType::MASTER_SLIDE, $shapeCount + 1);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.shape import Shape

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shapes = api.get_special_slide_shapes(file_name, slide_index, 'masterSlide')
shape_count = len(shapes.shapes_links)

dto = Shape()
dto.shape_type = 'Rectangle'
dto.x = 100
dto.y = 100
dto.width = 500
dto.height = 200
dto.text = "New shape"
shape = api.create_special_slide_shape(file_name, slide_index, 'masterSlide', None, None, dto)
print(shape.text) #New shape

dto.text = "Updated shape"
shape = api.update_special_slide_shape(file_name, slide_index, 'masterSlide', shape_count + 1, dto)
print(shape.text) #Updated shape

api.delete_special_slide_shape(file_name, slide_index, 'masterSlide', shape_count + 1)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
api.getSpecialSlideShapes(fileName, slideIndex, CloudSdk.model.SpecialSlideType.MasterSlide).then((result) => {
    const shapeCount = (result.body as CloudSdk.model.Shapes).shapesLinks.length;
    const dto = new CloudSdk.model.Shape();
    dto.shapeType = CloudSdk.model.Shape.ShapeTypeEnum.Rectangle;
    dto.x = 100;
    dto.y = 100;
    dto.width = 500;
    dto.height = 200;
    dto.text = "New shape";
    api.createSpecialSlideShape(fileName, slideIndex, CloudSdk.model.SpecialSlideType.MasterSlide, null, null, dto).then((postResult) => {
        console.log((postResult.body as CloudSdk.model.Shape).text); //New shape
        dto.text = "Updated shape";
        api.updateSpecialSlideShape(fileName, slideIndex, CloudSdk.model.SpecialSlideType.MasterSlide, shapeCount + 1, dto).then((putResult) => {
            console.log((putResult.body as CloudSdk.model.Shape).text); //Updated shape
            api.deleteSpecialSlideShape(fileName, slideIndex, CloudSdk.model.SpecialSlideType.MasterSlide, shapeCount + 1);
        });
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< /tabs >}}

### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
