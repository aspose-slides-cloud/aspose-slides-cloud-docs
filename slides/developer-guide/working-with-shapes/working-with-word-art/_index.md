---
title: "Working With WordArt"
type: docs
url: /working-with-word-art/
weight: 160
---

## **Introduction**
The example below shows how to create add WordArt text to a slide.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Add Portion**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes" -d "@wordArt.json" -H "Content-Type: text/json" -H "Authorization: Bearer AuthToken"
```

**wordArt.json example**

```javascript
{
    "type": "Shape",
    "shapeType": "Rectangle",
    "x": 100,
    "y": 100,
    "height": 100,
    "width": 200,
    "text": "Sample text",
    "textFrameFormat": {
        "transform": "ArchUpPour",
        "threeDFormat": {
            "bevelBottom": {
                "bevelType": "Circle",
                "height": 3.5,
                "width": 3.5
            },
            "bevelTop": {
                "bevelType": "Circle",
                "height": 4,
                "width": 4
            },
            "extrusionColor": "#FF008000",
            "extrusionHeight": 6,
            "contourColor": "#FF25353D",
            "contourWidth": 1.5,
            "depth": 3,
            "material": "Plastic",
            "lightRig": {
                "lightType": "Balanced",
                "direction": "Top",
                "xRotation": 0,
                "yRotation": 0,
                "zRotation": 40
            },
            "camera": {
                "cameraType": "PerspectiveContrastingRightFacing"
            }
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "type": "Shape",
    "text": "Sample text",
    "paragraphs": { "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/5/paragraphs", "relation": "self" },
    "textFrameFormat": {
        "threeDFormat": {
            "bevelBottom": {
                "bevelType": "Circle",
                "width": 3.5,
                "height": 3.5
            },
            "bevelTop":{
                "bevelType": "Circle",
                "width": 4.0,
                "height": 4.0
            },
            "camera": { "cameraType": "PerspectiveContrastingRightFacing" },
            "contourColor": "#FF25353D",
            "contourWidth": 0.0,
            "depth": 3.0,
            "extrusionColor": "#FF008000",
            "extrusionHeight": 6.0,
            "lightRig": { "direction": "Top", "lightType": "Balanced", "xRotation": 0.0, "yRotation": 0.0, "zRotation": 40.0},
            "material": "Plastic"
        },
        "transform": "ArchUpPour"
    },
    "shapeType": "Rectangle",
    "name": "New shape",
    "width": 200.0,
    "height": 100.0,
    "alternativeText":"",
    "alternativeTextTitle": "",
    "hidden": false,
    "x": 100.0,
    "y": 100.0,
    "zOrderPosition": 4,
    "fillFormat": { "type":"Solid", "color":"#FF5B9BD5" },
    "threeDFormat": { "contourWidth":0.0, "depth":0.0, "extrusionHeight": 0.0},
    "lineFormat": {
        "alignment": "Center",
        "capStyle": "Flat",
        "dashStyle": "Solid",
        "joinStyle": "Miter",
        "style": "Single",
        "beginArrowHead": { "length": "Medium", "style": "None", "width": "Medium" },
        "endArrowHead": { "length": "Medium", "style": "None", "width": "Medium" },
        "fillFormat":{ "type": "Solid", "color": "#FF41719C" },
        "miterLimit": 8.0,
        "width": 1.0
    },
    "selfUri": { "href" : "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/5" , "relation": "self" }
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
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Shape dto = new Shape
{
    ShapeType = GeometryShape.ShapeTypeEnum.Rectangle,
    X = 100,
    Y = 100,
    Height = 100,
    Width = 200,
    Text = "Sample text",
    TextFrameFormat = new TextFrameFormat
    {
        Transform = TextFrameFormat.TransformEnum.ArchUpPour,
        ThreeDFormat = new ThreeDFormat
        {
            BevelBottom = new ShapeBevel
            {
                BevelType = ShapeBevel.BevelTypeEnum.Circle,
                Height = 3.5,
                Width = 3.5
            },
            BevelTop = new ShapeBevel
            {
                BevelType = ShapeBevel.BevelTypeEnum.Circle,
                Height = 4,
                Width = 4
            },
            ExtrusionColor = "#FF008000",
            ExtrusionHeight = 6,
            ContourColor = "#FF25353D",
            ContourWidth = 1.5,
            Depth = 3,
            Material = ThreeDFormat.MaterialEnum.Plastic,
            LightRig = new LightRig
            {
                LightType = LightRig.LightTypeEnum.Balanced,
                Direction = LightRig.DirectionEnum.Top,
                XRotation = 0,
                YRotation = 0,
                ZRotation = 40
            },
            Camera = new Camera
            {
               CameraType = Camera.CameraTypeEnum.PerspectiveContrastingRightFacing
            }
        }
    }
};
ShapeBase shape = api.CreateShape(fileName, slideIndex, dto);
Console.WriteLine(((Shape)shape).Text);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Shape dto = new Shape();
dto.setShapeType(GeometryShape.ShapeTypeEnum.RECTANGLE);
dto.setX(100.0);
dto.setY(100.0);
dto.setHeight(100.0);
dto.setWidth(200.0);
dto.setText("Sample text");

TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTransform(TextFrameFormat.TransformEnum.ARCHUPPOUR);

ThreeDFormat threeDFormat = new ThreeDFormat();
ShapeBevel bevelBottom = new ShapeBevel();
bevelBottom.setBevelType(ShapeBevel.BevelTypeEnum.CIRCLE);
bevelBottom.setHeight(3.5);
bevelBottom.setWidth(3.5);
threeDFormat.setBevelBottom(bevelBottom);

ShapeBevel bevelTop = new ShapeBevel();
bevelTop.setBevelType(ShapeBevel.BevelTypeEnum.CIRCLE);
bevelTop.setHeight(4.0);
bevelTop.setWidth(4.0);
threeDFormat.setBevelTop(bevelTop);

threeDFormat.setExtrusionColor("#FF008000");
threeDFormat.setExtrusionHeight(6.0);
threeDFormat.setContourColor("#FF25353D");
threeDFormat.setContourWidth(1.5);
threeDFormat.setDepth(3.0);
threeDFormat.setMaterial(ThreeDFormat.MaterialEnum.PLASTIC);

LightRig lightRig = new LightRig();
lightRig.setLightType(LightRig.LightTypeEnum.BALANCED);
lightRig.setDirection(LightRig.DirectionEnum.TOP);
lightRig.setXrotation(0.0);
lightRig.setYrotation(0.0);
lightRig.setZrotation(40.0);
threeDFormat.setLightRig(lightRig);

Camera camera = new Camera();
camera.setCameraType(Camera.CameraTypeEnum.PERSPECTIVECONTRASTINGRIGHTFACING);
threeDFormat.setCamera(camera);
textFrameFormat.setThreeDFormat(threeDFormat);
dto.setTextFrameFormat(textFrameFormat);

ShapeBase shape = api.createShape(fileName, slideIndex, dto, null, null, null, null, null, null);
System.out.println(((Shape)shape).getText());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Shape;
use Aspose\Slides\Cloud\Sdk\Model\TextFrameFormat;
use Aspose\Slides\Cloud\Sdk\Model\ThreeDFormat;
use Aspose\Slides\Cloud\Sdk\Model\ShapeBevel;
use Aspose\Slides\Cloud\Sdk\Model\LightRig;
use Aspose\Slides\Cloud\Sdk\Model\Camera;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;

$dto = new Shape();
$dto->setShapeType("Rectangle");
$dto->setX(100);
$dto->setY(100);
$dto->setHeight(100);
$dto->setWidth(200);
$dto->setText("Sample text");

$textFrameFormat = new TextFrameFormat();
$textFrameFormat->setTransform("ArchUpPour");

$threeDFormat = new ThreeDFormat();
$bevelBottom = new ShapeBevel();
$bevelBottom->setBevelType("Circle");
$bevelBottom->setHeight(3.5);
$bevelBottom->setWidth(3.5);
$threeDFormat->setBevelBottom($bevelBottom);

$bevelTop = new ShapeBevel();
$bevelTop->setBevelType("Circle");
$bevelTop->setHeight(4);
$bevelTop->setWidth(4);
$threeDFormat->setBevelTop($bevelTop);

$threeDFormat->setExtrusionColor("#FF008000");
$threeDFormat->setExtrusionHeight(6);
$threeDFormat->setContourColor("#FF25353D");
$threeDFormat->setContourWidth(1.5);
$threeDFormat->setDepth(3);
$threeDFormat->setMaterial("Plastic");

$lightRig = new LightRig();
$lightRig->setLightType("Balanced");
$lightRig->setDirection("Top");
$lightRig->setXRotation(0);
$lightRig->setYRotation(0);
$lightRig->setZRotation(40);
$threeDFormat->setLightRig($lightRig);

$camera = new Camera();
$camera->setCameraType("PerspectiveContrastingRightFacing");
$threeDFormat->setCamera($camera);
$textFrameFormat->setThreeDFormat($threeDFormat);
$dto->setTextFrameFormat($textFrameFormat);

$shape = $api->createShape($fileName, $slideIndex, $dto);
print($shape->getText());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1

dto = AsposeSlidesCloud::Shape().new
dto.shape_type = "Rectangle"
dto.x = 100
dto.y = 100
dto.height = 100
dto.width = 200
dto.text = "Sample text"

text_frame_format = AsposeSlidesCloud::TextFrameFormat().new
text_frame_format.transform = "ArchUpPour"

three_d_format = AsposeSlidesCloud::ThreeDFormat().new
bevel_bottom = AsposeSlidesCloud::ShapeBevel().new
bevel_bottom.bevel_type = "Circle"
bevel_bottom.height = 3.5
bevel_bottom.width = 3.5
three_d_format.bevel_bottom = bevel_bottom

bevel_top = AsposeSlidesCloud::ShapeBevel().new
bevel_top.bevel_type = "Circle"
bevel_top.height = 4
bevel_top.width = 4
three_d_format.bevel_top = bevel_top

three_d_format.extrusion_color = "#FF008000"
three_d_format.extrusion_height = 6
three_d_format.contour_color = "#FF25353D"
three_d_format.contour_width = 1.5
three_d_format.depth = 3
three_d_format.material = "Plastic"

light_rig = AsposeSlidesCloud::LightRig().new
light_rig.light_type = "Balanced"
light_rig.direction = "Top"
light_rig.x_rotation = 0
light_rig.y_rotation = 0
light_rig.z_rotation = 40
three_d_format.light_rig = light_rig

camera = AsposeSlidesCloud::Camera().new
camera.camera_type = "PerspectiveContrastingRightFacing"
three_d_format.camera = camera
text_frame_format.three_d_format = three_d_format
dto.text_frame_format = text_frame_format

shape = api.create_shape(file_name, slide_index, dto)
print(shape.text)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.shape import Shape
from asposeslidescloud.models.text_frame_format import TextFrameFormat
from asposeslidescloud.models.three_d_format import ThreeDFormat
from asposeslidescloud.models.shape_bevel import ShapeBevel
from asposeslidescloud.models.light_rig import LightRig
from asposeslidescloud.models.camera import Camera

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1

dto = Shape()
dto.shape_type = "Rectangle"
dto.x = 100
dto.y = 100
dto.height = 100
dto.width = 200
dto.text = "Sample text"

text_frame_format = TextFrameFormat()
text_frame_format.transform = "ArchUpPour"

three_d_format = ThreeDFormat()
bevel_bottom = ShapeBevel()
bevel_bottom.bevel_type = "Circle"
bevel_bottom.height = 3.5
bevel_bottom.width = 3.5
three_d_format.bevel_bottom = bevel_bottom

bevel_top = ShapeBevel()
bevel_top.bevel_type = "Circle"
bevel_top.height = 4
bevel_top.width = 4
three_d_format.bevel_top = bevel_top

three_d_format.extrusion_color = "#FF008000"
three_d_format.extrusion_height = 6
three_d_format.contour_color = "#FF25353D"
three_d_format.contour_width = 1.5
three_d_format.depth = 3
three_d_format.material = "Plastic"

light_rig = LightRig()
light_rig.light_type = "Balanced"
light_rig.direction = "Top"
light_rig.x_rotation = 0
light_rig.y_rotation = 0
light_rig.z_rotation = 40
three_d_format.light_rig = light_rig

camera = Camera()
camera.camera_type = "PerspectiveContrastingRightFacing"
three_d_format.camera = camera
text_frame_format.three_d_format = three_d_format
dto.text_frame_format = text_frame_format

shape = api.create_shape(file_name, slide_index, dto)
print(shape.text)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;

const dto = new CloudSdk.Shape();
dto.shapeType = "Rectangle";
dto.x = 100;
dto.y = 100;
dto.height = 100;
dto.width = 200;
dto.text = "Sample text";

const textFrameFormat = new CloudSdk.TextFrameFormat();
textFrameFormat.transform = "ArchUpPour";

const threeDFormat = new CloudSdk.ThreeDFormat();
const bevelBottom = new CloudSdk.ShapeBevel();
bevelBottom.bevelType = "Circle";
bevelBottom.height = 3.5;
bevelBottom.width = 3.5;
threeDFormat.bevel_bottom = bevelBottom;

const bevelTop = new CloudSdk.ShapeBevel();
bevelTop.bevelType = "Circle";
bevelTop.height = 4;
bevelTop.width = 4;
threeDFormat.bevelTop = bevelTop;

threeDFormat.extrusionColor = "#FF008000";
threeDFormat.extrusionHeight = 6;
threeDFormat.contourColor = "#FF25353D";
threeDFormat.contourWidth = 1.5;
threeDFormat.depth = 3;
threeDFormat.material = "Plastic";

const lightRig = new CloudSdk.LightRig();
lightRig.lightType = "Balanced";
lightRig.direction = "Top";
lightRig.xRotation = 0;
lightRig.yRotation = 0;
lightRig.zRotation = 40;
threeDFormat.lightRig = lightRig;

const camera = new CloudSdk.Camera();
camera.cameraType = CloudSdk.Camera.CameraTypeEnum.PerspectiveContrastingRightFacing;
threeDFormat.camera = camera;
textFrameFormat.threeDFormat = threeDFormat;
dto.textFrameFormat = textFrameFormat;

return api.createShape(fileName, slideIndex, dto).then((result) => {
    console.log(result.body.text);
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

dto := asposeslidescloud.NewShape()
dto.ShapeType = "Rectangle"
dto.X = 100
dto.Y = 100
dto.Height = 100
dto.Width = 200
dto.Text = "Sample text"

textFrameFormat := asposeslidescloud.NewTextFrameFormat()
textFrameFormat.Transform = "ArchUpPour"

threeDFormat := asposeslidescloud.NewThreeDFormat()
bevelBottom := asposeslidescloud.NewShapeBevel()
bevelBottom.BevelType = "Circle"
bevelBottom.Height = 3.5
bevelBottom.Width = 3.5
threeDFormat.BevelBottom = bevelBottom

bevelTop := asposeslidescloud.NewShapeBevel()
bevelTop.BevelType = "Circle"
bevelTop.Height = 4
bevelTop.Width = 4
threeDFormat.BevelTop = bevelTop

threeDFormat.ExtrusionColor = "#FF008000"
threeDFormat.ExtrusionHeight = 6
threeDFormat.ContourColor = "#FF25353D"
threeDFormat.ContourWidth = 1.5
threeDFormat.Depth = 3
threeDFormat.Material = "Plastic"

lightRig := asposeslidescloud.NewLightRig()
lightRig.LightType = "Balanced"
lightRig.Direction = "Top"
lightRig.XRotation = 0
lightRig.YRotation = 0
lightRig.ZRotation = 40
threeDFormat.LightRig = lightRig

camera := asposeslidescloud.NewCamera()
camera.CameraType = "PerspectiveContrastingRightFacing"
threeDFormat.Camera = camera
textFrameFormat.ThreeDFormat = threeDFormat
dto.TextFrameFormat = textFrameFormat

shape, _, e := api.SlidesApi.CreateShape(fileName, slideIndex, dto, nil, nil, "", "", "", "")
if e != nil {
	fmt.Printf("Error: %v.", e)
}
if shape == nil {
	fmt.Printf("Error: shape should not be nil.")
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
