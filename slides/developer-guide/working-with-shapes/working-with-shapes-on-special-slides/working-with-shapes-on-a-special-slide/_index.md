---
title: "Working with Shapes"
type: docs
url: /working-with-shapes-on-a-special-slide/
weight: 10
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, modify, and delete shapes on special slides (Master, Layout, or Notes) in a PowerPoint presentation. To do this, you can use the following set of methods, identical to those that work with regular slides.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes|GET|Reads information about shapes on a special slide.|[GetSpecialSlideShapes](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlideShapes)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}|GET|Reads information about a shape on a special slide.|[GetSpecialSlideShape](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlideShape)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes|POST|Adds a new shape to a special slide.|[CreateSpecialSlideShape](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/CreateSpecialSlideShape)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}|PUT|Updates a shape on a special slide.|[UpdateSpecialSlideShape](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/UpdateSpecialSlideShape)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes|DELETE|Deletes a shape from a special slide.|[DeleteSpecialSlideShape](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlideShape)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes|DELETE|Deletes shapes from a special slide.|[DeleteSpecialSlideShapes](https://reference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlideShapes)|

{{< expand-list title="GetSpecialSlideShapes Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of the special slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="GetSpecialSlideShape Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of the special slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="CreateSpecialSlideShape Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of the special slide.|
|dto|object|body|true|The data transfer object with parameters for the new shape.|
|shapeToClone|integer|query|false|The 1-based index for a cloning shape instead of adding a new one.|
|position|integer|query|false|The 1-based index for the new shape in the list. By default, the shape is added to the end of the list.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="UpdateSpecialSlideShape Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of the special slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|dto|object|body|true|The data transfer object with parameters to be updated.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="DeleteSpecialSlideShape Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of the special slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="DeleteSpecialSlideShapes Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of the special slide.|
|shapes|string|query|false|The indices of the shapes to be deleted. Delete all by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

## **Examples**

The following examples demonstrate manipulating shapes on a Master slide. You can access shapes on a Layout slide or Notes slide the same way, just change the value of the **slideType** parameter accordingly.

**cURL Examples**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get a Shape List**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes" \
     -H "authorization: Bearer MyAccessToken"
```

**Add a Shape**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: text/json" \
     -d "@shape.json"
```

**Update a Shape**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/6" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: text/json" \
     -d "@shape.json"
```

**Delete a Shape**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes" \
     -H "authorization: Bearer MyAccessToken"
```

**shape.json example**

```json
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

```json
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

**SDK Examples**

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

string fileName = "MyPresentation.pptx";
SpecialSlideType slideType = SpecialSlideType.MasterSlide;
int slideIndex = 1;

Shapes shapes = api.GetSpecialSlideShapes(fileName, slideIndex, slideType);
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

Shape shape = (Shape)api.CreateSpecialSlideShape(fileName, slideIndex, slideType, dto);
Console.WriteLine(shape.Text); // New shape

dto.Text = "Updated shape";
shape = (Shape)api.UpdateSpecialSlideShape(fileName, slideIndex, slideType, shapeCount + 1, dto);
Console.WriteLine(shape.Text); // Updated shape

api.DeleteSpecialSlideShape(fileName, slideIndex, SpecialSlideType.MasterSlide, shapeCount + 1);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

String fileName = "MyPresentation.pptx";
SpecialSlideType slideType = SpecialSlideType.MASTERSLIDE;
int slideIndex = 1;

Shapes shapes = api.getSpecialSlideShapes(fileName, slideIndex, slideType, null, null, null, null);
int shapeCount = shapes.getShapesLinks().size();

Shape dto = new Shape();
dto.setX(100.0);
dto.setY(100.0);
dto.setWidth(500.0);
dto.setHeight(200.0);
dto.setShapeType(GeometryShape.ShapeTypeEnum.RECTANGLE);
dto.setText("New shape");

Shape shape = (Shape)api.createSpecialSlideShape(fileName, slideIndex, slideType, dto, null, null, null, null, null, null);
System.out.println(shape.getText()); // New shape

dto.setText("Updated shape");
shape = (Shape)api.updateSpecialSlideShape(fileName, slideIndex, slideType, shapeCount + 1, dto, null, null, null, null);
System.out.println(shape.getText()); // Updated shape

api.deleteSpecialSlideShape(fileName, slideIndex, slideType, shapeCount + 1, null, null, null, null);
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
$slideType = SpecialSlideType::MASTER_SLIDE;
$slideIndex = 1;

$shapes = $api->GetSpecialSlideShapes($fileName, $slideIndex, $slideType);
$shapeCount = count($shapes->getShapesLinks());

$dto = new Shape();
$dto->setX(100);
$dto->setY(100);
$dto->setWidth(500);
$dto->setHeight(200);
$dto->setShapeType("Rectangle");
$dto->setText("New shape");

$shape = $api->CreateSpecialSlideShape($fileName, $slideIndex, $slideType, $dto);
print($shape->getText()); // New shape

$dto->setText("Updated shape");
$shape = $api->UpdateSpecialSlideShape($fileName, $slideIndex, $slideType, $shapeCount + 1, $dto);
print($shape->getText()); // Updated shape

$api->DeleteSpecialSlideShape($fileName, $slideIndex, $slideType, $shapeCount + 1);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_type = "masterSlide"
slide_index = 1

shapes = slides_api.get_special_slide_shapes(file_name, slide_index, slide_type)
shape_count = shapes.shapes_links.length

dto = Shape.new
dto.shape_type = "Rectangle"
dto.x = 100
dto.y = 100
dto.width = 500
dto.height = 200
dto.text = "New shape"

shape = slides_api.create_special_slide_shape(file_name, slide_index, slide_type, dto)
puts shape.text # New shape

dto.text = "Updated shape"
shape = slides_api.update_special_slide_shape(file_name, slide_index, slide_type, shape_count + 1, dto)
puts shape.text # Updated shape

slides_api.delete_special_slide_shape(file_name, slide_index, slide_type, shape_count + 1)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.shape import Shape

configuration = Configuration()
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_type = "masterSlide"
slide_index = 1

shapes = api.get_special_slide_shapes(file_name, slide_index, slide_type)
shape_count = len(shapes.shapes_links)

dto = Shape()
dto.shape_type = "Rectangle"
dto.x = 100
dto.y = 100
dto.width = 500
dto.height = 200
dto.text = "New shape"

shape = api.create_special_slide_shape(file_name, slide_index, slide_type, dto)
print(shape.text) # New shape

dto.text = "Updated shape"
shape = api.update_special_slide_shape(file_name, slide_index, slide_type, shape_count + 1, dto)
print(shape.text) # Updated shape

api.delete_special_slide_shape(file_name, slide_index, slide_type, shape_count + 1)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideType = CloudSdk.SpecialSlideType.MasterSlide;
const slideIndex = 1;

api.getSpecialSlideShapes(fileName, slideIndex, slideType).then(result => {
    const shapeCount = result.body.shapesLinks.length;

    const dto = new CloudSdk.Shape();
    dto.shapeType = CloudSdk.Shape.ShapeTypeEnum.Rectangle;
    dto.x = 100;
    dto.y = 100;
    dto.width = 500;
    dto.height = 200;
    dto.text = "New shape";

    api.createSpecialSlideShape(fileName, slideIndex, slideType, dto).then(postResult => {
        console.log(postResult.body.text); // New shape
        dto.text = "Updated shape";
        api.updateSpecialSlideShape(fileName, slideIndex, slideType, shapeCount + 1, dto).then(putResult => {
            console.log(putResult.body.text); // Updated shape
            api.deleteSpecialSlideShape(fileName, slideIndex, slideType, shapeCount + 1);
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
slideType := "masterSlide"
var slideIndex int32 = 1

shapes, _, e := api.SlidesApi.GetSpecialSlideShapes(fileName, slideIndex, slideType, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
shapeCount := len(shapes.GetShapesLinks())

dto := asposeslidescloud.NewShape()
dto.ShapeType = "Rectangle"
dto.X = 100
dto.Y = 100
dto.Width = 500
dto.Height = 200
dto.Text = "New shape"

shape, _, e := api.SlidesApi.CreateSpecialSlideShape(fileName, slideIndex, slideType, dto, nil, nil, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", shape.(asposeslidescloud.IShape).GetText()) // New shape

dto.Text = "Updated shape"
shape, _, e = api.SlidesApi.UpdateSpecialSlideShape(fileName, slideIndex, slideType, int32(shapeCount + 1), dto, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", shape.(asposeslidescloud.IShape).GetText()) // Updated shape

_, _, e = api.SlidesApi.DeleteSpecialSlideShape(fileName, slideIndex, slideType, int32(shapeCount + 1), "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Shape;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_type = "masterSlide";
my $slide_index = 1;

my %shapes_parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type);
my $shapes = $slides_api->get_special_slide_shapes(%shapes_parameters);
my $shape_count = @{$shapes->{shapes_links}};

my $dto = AsposeSlidesCloud::Object::Shape->new();
$dto->{x} = 100;
$dto->{y} = 100;
$dto->{width} = 500;
$dto->{height} = 200;
$dto->{shape_type} = "Rectangle";
$dto->{text} = "New shape";

my %new_shape_parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, dto => $dto);
my $shape = $slides_api->create_special_slide_shape(%new_shape_parameters);
print($shape->{text}); # New shape

$dto->{text} = "Updated shape";
my %updated_shape_parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_count + 1, dto => $dto);
$shape = $slides_api->update_special_slide_shape(%updated_shape_parameters);
print("\n" . $shape->{text}); # Updated shape

my %deleted_shape_parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_count + 1);
$slides_api->delete_special_slide_shape(%deleted_shape_parameters);
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
