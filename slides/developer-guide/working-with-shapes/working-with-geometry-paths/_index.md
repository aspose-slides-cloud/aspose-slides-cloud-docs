---
title: "Working With Geometry Paths"
type: docs
url: /working-with-geometry-paths/
weight: 140
---

## **Introduction**
You can create shapes with custom geometry using **geometryPath** resource. You can create any type of geometry shape using lines, arcs and Bezier curves.

### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/geometryPath|GET|Gets shape geometry path.|[Get shape geomety path](https://apireference.aspose.cloud/slides/#/Shapes/GetShapeGeometryPath)|
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/geometryPath|POST|Sets shape geometry path.|[Set shape geomety path](https://apireference.aspose.cloud/slides/#/Shapes/SetShapeGeometryPath)|

{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|folder|POST/PUT|string (query)|Optional|Presentation folder.|
|storage|POST/PUT|string (query)|Optional|Presentation storage.|
|password|POST/PUT|string (header)|Optional|Presentation password.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< /expand-list >}}

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Add Portion**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/geometryPath" -d "@geometry.json" -H "Content-Type: text/json" -H "Authorization: Bearer AuthToken"
```

**geometry.json example**

```javascript
{
    "paths": [
        {
            "pathData": [
                { "type": "MoveTo", "x": 0, "y": 0 },
                { "type": "LineTo", "x": 0, "y": 200 },
                { "type": "LineTo", "x": 200, "y": 300 },
                { "type": "LineTo", "x": 400, "y": 200 },
                { "type": "LineTo", "x": 400, "y": 0 },
                { "type": "Close" }
            ]
        }
    ]
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
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2",
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

GeometryPaths dto = new GeometryPaths
{
    Paths = new List<GeometryPath>
    {
        new GeometryPath
        {
            PathData = new List<PathSegment>
            {
                new MoveToPathSegment { X = 0, Y = 0 },
                new LineToPathSegment { X = 0, Y = 200 },
                new LineToPathSegment { X = 200, Y = 300 },
                new LineToPathSegment { X = 400, Y = 200 },
                new LineToPathSegment { X = 400, Y = 0 },
                new ClosePathSegment()
            }
        }
    }
};
ShapeBase shape = api.SetShapeGeometryPath(fileName, slideIndex, shapeIndex, dto);
Console.WriteLine(shape.Width);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

GeometryPaths dto = new GeometryPaths();
List<GeometryPath> paths = new ArrayList<GeometryPath>();
GeometryPath path = new GeometryPath();
List<PathSegment> pathData = new ArrayList<PathSegment>();
MoveToPathSegment startSegment = new MoveToPathSegment();
startSegment.setX(0.0);
startSegment.setY(0.0);
pathData.add(startSegment);

LineToPathSegment line1Segment = new LineToPathSegment();
line1Segment.setX(0.0);
line1Segment.setY(200.0);
pathData.add(line1Segment);

LineToPathSegment line2Segment = new LineToPathSegment();
line2Segment.setX(200.0);
line2Segment.setY(300.0);
pathData.add(line2Segment);

LineToPathSegment line3Segment = new LineToPathSegment();
line3Segment.setX(400.0);
line3Segment.setY(200.0);
pathData.add(line3Segment);

LineToPathSegment line4Segment = new LineToPathSegment();
line4Segment.setX(400.0);
line4Segment.setY(0.0);
pathData.add(line4Segment);

ClosePathSegment endSegment = new ClosePathSegment();
pathData.add(endSegment);
path.setPathData(pathData);
paths.add(path);
dto.setPaths(paths);
ShapeBase shape = api.setShapeGeometryPath(fileName, slideIndex, shapeIndex, dto, null, null, null);
System.out.println(shape.getWidth());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\GeometryPaths;
use Aspose\Slides\Cloud\Sdk\Model\GeometryPath;
use Aspose\Slides\Cloud\Sdk\Model\MoveToPathSegment;
use Aspose\Slides\Cloud\Sdk\Model\LineToPathSegment;
use Aspose\Slides\Cloud\Sdk\Model\ClosePathSegment;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;

$dto = new GeometryPaths();
$path = new GeometryPath();
$start = new MoveToPathSegment();
$start->setX(0);
$start->setY(0);
$line1 = new LineToPathSegment();
$line1->setX(0);
$line1->setY(200);
$line2 = new LineToPathSegment();
$line2->setX(200);
$line2->setY(300);
$line3 = new LineToPathSegment();
$line3->setX(400);
$line3->setY(200);
$line4 = new LineToPathSegment();
$line4->setX(400);
$line4->setY(0);
$end = new ClosePathSegment();
$path->setPathData([ $start, $line1, $line1, $line3, $line4, $end ]);
$dto->setPaths([ $path ]);
$shape = $this->getApi()->setShapeGeometryPath($fileName, $slideIndex, $shapeIndex, $dto);
print($shape->getWith());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.geometry_paths import GeometryPaths
from asposeslidescloud.models.geometry_path import GeometryPath
from asposeslidescloud.models.move_to_path_segment import MoveToPathSegment
from asposeslidescloud.models.line_to_path_segment import LineToPathSegment
from asposeslidescloud.models.close_path_segment import ClosePathSegment

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2

dto = GeometryPaths()
path = GeometryPath()
start = MoveToPathSegment()
start.x = 0
start.y = 0
line1 = LineToPathSegment()
line1.x = 0
line1.y = 200
line2 = LineToPathSegment()
line2.x = 200
line2.y = 300
line3 = LineToPathSegment()
line3.x = 400
line3.y = 200
line4 = LineToPathSegment()
line4.x = 400
line4.y = 0
end = ClosePathSegment()
path.path_data = [ start, line1, line2, line3, line4, end ]
dto.paths = [ path ]
shape = BaseTest.slides_api.set_shape_geometry_path(file_name, slide_index, shape_index, dto)
print(shape.width)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
const shapeIndex = 2;

const dto = new CloudSdk.GeometryPaths();
const path = new CloudSdk.GeometryPath();
const start = new CloudSdk.MoveToPathSegment();
start.x = 0;
start.y = 0;
const line1 = new CloudSdk.MoveToPathSegment();
line1.x = 0;
line1.y = 200;
const line2 = new CloudSdk.MoveToPathSegment();
line2.x = 200;
line2.y = 300;
const line3 = new CloudSdk.MoveToPathSegment();
line3.x = 400;
line3.y = 200;
const line4 = new CloudSdk.MoveToPathSegment();
line4.x = 400;
line4.y = 0;
const end = new CloudSdk.ClosePathSegment();
path.pathData = [ start, line1, line2, line3, line4, end ];
dto.paths = [ path ];
return api.setShapeGeometryPath(fileName, slideIndex, shapeIndex, dto).then((result) => {
    console.log(result.body.width);
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

dto := NewGeometryPaths()
path := NewGeometryPath()
startSegment := NewMoveToPathSegment()
startSegment.X = 0
startSegment.Y = 0
line1 := NewLineToPathSegment()
line1.X = 0
line1.Y = 200
line2 := NewLineToPathSegment()
line2.X = 200
line2.Y = 300
line3 := NewLineToPathSegment()
line3.X = 400
line3.Y = 200
line4 := NewLineToPathSegment()
line4.X = 400
line4.Y = 0
endSegment := NewClosePathSegment()
path.PathData = []IPathSegment { startSegment, line1, line2, line3, line4, endSegment }
dto.Paths = []IGeometryPath { path }
shape, _, e := c.SlidesApi.SetShapeGeometryPath(fileName, slideIndex, shapeIndex, dto, "", "", "")
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
