---
title: "ThreeDFormat"
type: docs
url: /three-d-format-type/
weight: 30
---

## **ThreeDFormat Type**

This complex type represents 3D format.

| **Property Name** | **Type** | **Description** |
| :- | :- | :- | 
| Material | enum | Material. |
| BevelBottom | ShapeBevel | Bottom 3D bevel. |
| BevelTop | ShapeBevel | Top 3D bevel. |
| Camera | Camera | Material. |
| ContourColor | string | Contour color. |
| ContourWidth | double | Contour width. |
| Depth  | double | Depth. |
| ExtrusionColor | string | Extrusion color. |
| ExtrusionHeight | double | Extrusion height. |
| LightRig | LightRig | Light rig. |

*Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.*

{{< expand-list title="Material Values" >}}

- Clear
- DkEdge
- Flat
- LegacyMatte
- LegacyMetal
- LegacyPlastic
- LegacyWireframe
- Matte
- Metal
- Plastic
- Powder
- SoftEdge
- Softmetal
- TranslucentPowder
- WarmMatte
- NotDefined

{{< /expand-list >}}

#### **ShapeBevel** properties

| **Property Name** | **Type** | **Description** |
| :- | :- | :- | 
| BevelType | enum | Bevel type. |
| Width | double | Bevel width. |
| Height | double | Bevel height. |

{{< expand-list title="BevelType Values" >}}

- Angle
- ArtDeco
- Circle
- Convex
- CoolSlant
- Cross
- Divot
- HardEdge
- RelaxedInset
- Riblet
- Slope
- SoftRound
- NotDefined

{{< /expand-list >}}

#### **Camera** properties

| **Property Name** | **Type** | **Description** |
| :- | :- | :- | 
| CameraType | enum | Camera type. |
| FieldOfViewAngle | double | Field of view angle (FOV). |
| Zoom | double | Camera zoom. |
| XRotation | double | XRotation. |
| YRotation | double | YRotation. |
| ZRotation | double | ZRotation. |

{{< expand-list title="BevelType Values" >}}

- IsometricBottomDown
- IsometricBottomUp
- IsometricLeftDown
- IsometricLeftUp
- IsometricOffAxis1Left
- IsometricOffAxis1Right
- IsometricOffAxis1Top
- IsometricOffAxis2Left
- IsometricOffAxis2Right
- IsometricOffAxis2Top
- IsometricOffAxis3Bottom
- IsometricOffAxis3Left
- IsometricOffAxis3Right
- IsometricOffAxis4Bottom
- IsometricOffAxis4Left
- IsometricOffAxis4Right
- IsometricRightDown
- IsometricRightUp
- IsometricTopDown
- IsometricTopUp
- LegacyObliqueBottom
- LegacyObliqueBottomLeft
- LegacyObliqueBottomRight
- LegacyObliqueFront
- LegacyObliqueLeft
- LegacyObliqueRight
- LegacyObliqueTop
- LegacyObliqueTopLeft
- LegacyObliqueTopRight
- LegacyPerspectiveBottom
- LegacyPerspectiveBottomLeft
- LegacyPerspectiveBottomRight
- LegacyPerspectiveFront
- LegacyPerspectiveLeft
- LegacyPerspectiveRight
- LegacyPerspectiveTop
- LegacyPerspectiveTopLeft
- LegacyPerspectiveTopRight
- ObliqueBottom
- ObliqueBottomLeft
- ObliqueBottomRight
- ObliqueLeft
- ObliqueRight
- ObliqueTop
- ObliqueTopLeft
- ObliqueTopRight
- OrthographicFront
- PerspectiveAbove
- PerspectiveAboveLeftFacing
- PerspectiveAboveRightFacing
- PerspectiveBelow
- PerspectiveContrastingLeftFacing
- PerspectiveContrastingRightFacing
- PerspectiveFront
- PerspectiveHeroicExtremeLeftFacing
- PerspectiveHeroicExtremeRightFacing
- PerspectiveHeroicLeftFacing
- PerspectiveHeroicRightFacing
- PerspectiveLeft
- PerspectiveRelaxed
- PerspectiveRelaxedModerately
- PerspectiveRight
- NotDefined

{{< /expand-list >}}

#### **LightRig** properties

| **Property Name** | **Type** | **Description** |
| :- | :- | :- | 
| Direction | enum | Light direction. |
| LightType | double | Light type. |
| XRotation | double | XRotation. |
| YRotation | double | YRotation. |
| ZRotation | double | ZRotation. |

{{< expand-list title="Direction Values" >}}

- TopLeft
- Top
- TopRight
- Right
- BottomRight
- Bottom
- BottomLeft
- Left
- NotDefined

{{< /expand-list >}}

{{< expand-list title="LightType Values" >}}

- Balanced
- BrightRoom
- Chilly
- Contrasting
- Flat
- Flood
- Freezing
- Glow
- Harsh
- LegacyFlat1
- LegacyFlat2
- LegacyFlat3
- LegacyFlat4
- LegacyHarsh1
- LegacyHarsh2
- LegacyHarsh3
- LegacyHarsh4
- LegacyNormal1
- LegacyNormal2
- LegacyNormal3
- LegacyNormal4
- Morning
- Soft
- Sunrise
- Sunset
- ThreePt
- TwoPt
- NotDefined

{{< /expand-list >}}

JSON value example:

```
{
    "Depth": 4,
    "BevelTop": {
        "BevelType": "Circle",
        "Height": 6,
        "Width": 6
    },
    "Camera": {
        "CameraType": "OrthographicFront"
    },
    "LightRig": {
        "LightType": "ThreePt",
        "Direction": "Top"
    }
}
```

SDK Example:

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Shape dto = new Shape
{
    ThreeDFormat = new ThreeDFormat
    {
        Depth = 4,
        BevelTop = new ShapeBevel { BevelType = ShapeBevel.BevelTypeEnum.Circle, Height = 6, Width = 6 },
        Camera = new Camera { CameraType = Camera.CameraTypeEnum.OrthographicFront },
        LightRig = new LightRig { LightType = LightRig.LightTypeEnum.ThreePt, Direction = LightRig.DirectionEnum.Top }
    }
};
ShapeBase shape = api.UpdateShape("MyPresentation.pptx", 1, 1, dto);
Console.WriteLine(shape.ThreeDFormat.Depth);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Shape dto = new Shape();
ThreeDFormat threeDFormat = new ThreeDFormat();
threeDFormat.setDepth(4.0);

ShapeBevel bevelTop = new ShapeBevel();
bevelTop.setBevelType(ShapeBevel.BevelTypeEnum.CIRCLE);
bevelTop.setHeight(6.0);
bevelTop.setWidth(6.0);
threeDFormat.setBevelTop(bevelTop);

Camera camera = new Camera();
camera.setCameraType(Camera.CameraTypeEnum.ORTHOGRAPHICFRONT);
threeDFormat.setCamera(camera);

LightRig lightRig = new LightRig();
lightRig.setLightType(LightRig.LightTypeEnum.THREEPT);
lightRig.setDirection(LightRig.DirectionEnum.TOP);
threeDFormat.setLightRig(lightRig);
dto.setThreeDFormat(threeDFormat);
ShapeBase shape = api.updateShape("MyPresentation.pptx", 1, 1, dto, null, null, null, null);
System.out.println(shape.getThreeDFormat().getDepth());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Shape;
use Aspose\Slides\Cloud\Sdk\Model\ThreeDFormat;
use Aspose\Slides\Cloud\Sdk\Model\ShapeBevel;
use Aspose\Slides\Cloud\Sdk\Model\Camera;
use Aspose\Slides\Cloud\Sdk\Model\LightRig;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new Shape();
$threeDFormat = new ThreeDFormat();
$threeDFormat->setDepth(4);

$bevelTop = new ShapeBevel();
$bevelTop->setBevelType("Circle");
$bevelTop->setHeight(6);
$bevelTop->setWidth(6);
$threeDFormat->setBevelTop($bevelTop);

$camera = new Camera();
$camera->setCameraType("OrthographicFront");
$threeDFormat->setCamera($camera);

$lightRig = new LightRig();
$lightRig->setLightType("ThreePt");
$lightRig->setDirection("Top");
$threeDFormat->setLightRig($lightRig);
$dto->setThreeDFormat($threeDFormat);
$result = $api->updateShape("MyPresentation.pptx", 1, 1, $dto);
print($result->getThreeDFormat()->getDepth());
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
from asposeslidescloud.models.three_d_format import ThreeDFormat
from asposeslidescloud.models.shape_bevel import ShapeBevel
from asposeslidescloud.models.camera import Camera
from asposeslidescloud.models.light_rig import LightRig

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = Shape()
three_d_format = ThreeDFormat()
three_d_format.depth = 4

bevel_top = ShapeBevel()
bevel_top.bevel_type = "Circle"
bevel_top.height = 6
bevel_top.width = 6
three_d_format.bevel_top = bevel_top

camera = Camera()
camera.camera_type = "OrthographicFront"
three_d_format.camera = camera

light_rig = LightRig()
light_rig.light_type = "ThreePt"
light_rig.direction = "Top"
three_d_format.light_rig = light_rig
dto.three_d_format = three_d_format
shape = api.update_shape("MyPresentation.pptx", 1, 1, dto)
print(shape.three_d_format.depth)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new CloudSdk.Shape();
const effectFormat = new CloudSdk.EffectFormat();
const innerShadow = new CloudSdk.InnerShadowEffect();
innerShadow.direction = 35;
innerShadow.blurRadius = 30;
innerShadow.distance = 40;
innerShadow.shadowColor = "#FFFFFF00";
effectFormat.innerShadow = innerShadow;
dto.effectFormat = effectFormat;
api.updateShape("MyPresentation.pptx", 1, 1, dto).then((result) => {
    console.log(result.body.effectFormat.innerShadow.direction);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

dto := NewShape()
threeDFormat := NewThreeDFormat()
threeDFormat.Depth = 4

bevelTop := NewShapeBevel()
bevelTop.BevelType = "Circle"
bevelTop.Height = 6
bevelTop.Width = 6
threeDFormat.BevelTop = bevelTop

camera := NewCamera()
camera.CameraType = "OrthographicFront"
threeDFormat.Camera = camera

lightRig := NewLightRig()
lightRig.LightType = "ThreePt"
lightRig.Direction = "Top"
threeDFormat.LightRig = lightRig
dto.ThreeDFormat = threeDFormat
result, _, e := api.UpdateShape(fileName, slideIndex, shapeIndex, dto, "password", folderName, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    fmt.Printf("Depth value: %v.", dto.getThreeDFormat().getDepth())
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
