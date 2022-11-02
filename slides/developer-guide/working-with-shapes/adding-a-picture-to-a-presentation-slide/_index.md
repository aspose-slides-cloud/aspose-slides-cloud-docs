---
title: "Adding a Picture to a Presentation Slide"
type: docs
url: /adding-a-picture-to-a-presentation-slide/
weight: 95
---

## **Introduction**

You can use Aspose.Slides Cloud API to add pictures to PowerPoint documents. To add a picture to a presentation slide, you can use a bitmap or vector image. You can crop the image, set some transformation effects (such as an Alpha Bi-Level effect, blur effect, duotone effect, luminance effect, etc.), use stretch or tile fill mode. The code examples in this article use [CreateShape](/slides/adding-shapes-to-a-powerpoint-presentation/) method.

## **Example**

Use **MyImage.png** file to add a **400x300** picture at coordinates **(20, 20)** to the **second** slide in **MyFolder/MyPresentation.pptx** document saved to the default storage. Use **tile** fill mode for the image.

MyImage.png:

![Image example](MyImage.png "Image example")

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the Picture**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes?folder=MyFolder" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/json" \
     -d @request_data.json
```


request_data.json content:

```json
{
    "Type": "PictureFrame",
    "X": 20,
    "Y": 20,
    "Width": 400,
    "Height": 300,
    "PictureFillFormat": {
        "PictureFillMode": "Tile",
        "Base64Data": "iVBORw0KGgoAAAA...QmCC"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "type": "PictureFrame",
    "pictureFillFormat": {
        "type": "Picture",
        "cropBottom": 0.0,
        "cropLeft": 0.0,
        "cropRight": 0.0,
        "cropTop": 0.0,
        "dpi": 0,
        "image": {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images/1?folder=MyFolder",
            "relation": "self"
        },
        "pictureFillMode": "Tile"
    },
    "shapeType": "Rectangle",
    "name": "New picture",
    "width": 400.0,
    "height": 300.0,
    "alternativeText": "",
    "alternativeTextTitle": "",
    "hidden": false,
    "x": 20.0,
    "y": 20.0,
    "zOrderPosition": 0,
    "fillFormat": {
        "type": "NoFill"
    },
    "threeDFormat": {
        "contourWidth": 0.0,
        "depth": 0.0,
        "extrusionHeight": 0.0
    },
    "lineFormat": {
        "alignment": "Center",
        "capStyle": "Flat",
        "dashStyle": "Solid",
        "joinStyle": "Round",
        "style": "Single",
        "beginArrowHead": {
            "length": "Medium",
            "style": "None",
            "width": "Medium"
        },
        "endArrowHead": {
            "length": "Medium",
            "style": "None",
            "width": "Medium"
        },
        "fillFormat": {
            "type": "NoFill"
        },
        "miterLimit": 10.0,
        "width": 0.75
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    }
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![Tiled picture](TiledPicture.png "Tiled picture")

{{% alert color="primary" %}} 

To create pictures from SVG images, use `SvgData` option instead of `Base64Data`.

{{% /alert %}} 

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

using System;
using System.Diagnostics;
using System.IO;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the image data.
        var imageData = File.ReadAllBytes("MyImage.png");
        var imageBase64String = Convert.ToBase64String(imageData);

        // Prepare the DTO for the new picture. 
        var pictureFrame = new PictureFrame
        {
            X = 20,
            Y = 20,
            Width = 400,
            Height = 300,
            PictureFillFormat = new PictureFill
            {
                Base64Data = imageBase64String,
                PictureFillMode = PictureFill.PictureFillModeEnum.Tile,
            }
        };

        // Add the picture to the second slide.
        var pictureInfo = slidesApi.CreateShape("MyPresentation.pptx", 2, pictureFrame, folder: "MyFolder");

        // Print a reference to the picture frame.
        Debug.WriteLine(pictureInfo.SelfUri.Href);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.Base64;

public class Application {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare the image data.
        byte[] imageData = Files.readAllBytes(Paths.get("MyImage.png"));
        String imageBase64String = Base64.getEncoder().encodeToString(imageData);

        // Prepare the DTO for the new picture.
        PictureFrame pictureFrame = new PictureFrame();
        pictureFrame.setX(20.0);
        pictureFrame.setY(20.0);
        pictureFrame.setWidth(400.0);
        pictureFrame.setHeight(300.0);
        pictureFrame.setPictureFillFormat(new PictureFill());
        pictureFrame.getPictureFillFormat().setBase64Data(imageBase64String);
        pictureFrame.getPictureFillFormat().setPictureFillMode(PictureFill.PictureFillModeEnum.TILE);

        // Add the picture to the second slide.
        ShapeBase pictureInfo = slidesApi.createShape("MyPresentation.pptx", 2, pictureFrame, null, null, null, "MyFolder", null, null);

        // Print a reference to the picture frame.
        System.out.println(pictureInfo.getSelfUri().getHref());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\PictureFrame;
use Aspose\Slides\Cloud\Sdk\Model\PictureFill;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare the image data.
$imageData = file_get_contents("MyImage.png");
$imageBase64String = base64_encode($imageData);

// Prepare the DTO for the new picture.
$pictureFrame = new PictureFrame();
$pictureFrame->setX(20);
$pictureFrame->setY(20);
$pictureFrame->setWidth(400);
$pictureFrame->setHeight(300);
$pictureFrame->setPictureFillFormat(new PictureFill());
$pictureFrame->getPictureFillFormat()->setBase64Data($imageBase64String);
$pictureFrame->getPictureFillFormat()->setPictureFillMode("Tile");

// Add the picture to the second slide.
$pictureInfo = $slidesApi->createShape("MyPresentation.pptx", 2, $pictureFrame, null, null, null, "MyFolder");

// Print a reference to the picture frame.
echo $pictureInfo->getSelfUri()->getHref();
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"
require "base64"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

# Prepare the image data.
image_data = File.binread("MyImage.png")
image_base64_string = Base64.encode64(image_data)

# Prepare the DTO for the new picture.
picture_frame = PictureFrame.new
picture_frame.x = 20
picture_frame.y = 20
picture_frame.width = 400
picture_frame.height = 300
picture_frame.picture_fill_format = PictureFill.new
picture_frame.picture_fill_format.base64_data = image_base64_string
picture_frame.picture_fill_format.picture_fill_mode = "Tile"

# Add the picture to the second slide.
picture_info = slides_api.create_shape("MyPresentation.pptx", 2, picture_frame, nil, nil, nil, "MyFolder")

# Print a reference to the picture frame.
print picture_info.self_uri.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud
import base64

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.picture_frame import PictureFrame
from asposeslidescloud.models.picture_fill import PictureFill

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare the image data.
with open("MyImage.png", "rb") as image_stream:
    image_base64_string = str(base64.b64encode(image_stream.read()), "utf-8")

# Prepare the DTO for the new picture.
picture_frame = PictureFrame()
picture_frame.x = 20
picture_frame.y = 20
picture_frame.width = 400
picture_frame.height = 300
picture_frame.picture_fill_format = PictureFill()
picture_frame.picture_fill_format.base64_data = image_base64_string
picture_frame.picture_fill_format.picture_fill_mode = "Tile"

# Add the picture to the second slide.
picture_info = slides_api.create_shape("MyPresentation.pptx", 2, picture_frame, None, None, None, "MyFolder")

# Print a reference to the picture frame.
print(picture_info.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Prepare the image data.
const imageBase64String = fs.readFileSync("MyImage.png", { encoding: "base64" })

// Prepare the DTO for the new picture.
const pictureFrame = new cloud.PictureFrame()
pictureFrame.x = 20
pictureFrame.y = 20
pictureFrame.width = 400
pictureFrame.height = 300
pictureFrame.pictureFillFormat = new cloud.PictureFill()
pictureFrame.pictureFillFormat.base64Data = imageBase64String
pictureFrame.pictureFillFormat.pictureFillMode = "Tile"

// Add the picture to the second slide.
slidesApi.createShape("MyPresentation.pptx", 2, pictureFrame, null, null, null, "MyFolder").then((pictureInfo) => {
    // Print a reference to the picture frame.
    console.log(pictureInfo.body.selfUri.href)
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::PictureFrame;
use AsposeSlidesCloud::Object::PictureFill;

use File::Slurp;
use MIME::Base64;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare the image data.
my $image_data = read_file("MyImage.png", { binmode => ":raw" });
my $image_base64_string = encode_base64($image_data);

# Prepare the DTO for the new picture.
my $picture_frame = AsposeSlidesCloud::Object::PictureFrame->new();
$picture_frame->{x} = 20;
$picture_frame->{y} = 20;
$picture_frame->{width} = 400;
$picture_frame->{height} = 300;
$picture_frame->{picture_fill_format} = AsposeSlidesCloud::Object::PictureFill->new();
$picture_frame->{picture_fill_format}->{base64_data} = $image_base64_string;
$picture_frame->{picture_fill_format}->{picture_fill_mode} = "Tile";

# Add the picture to the second slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, dto => $picture_frame, folder => "MyFolder");
my $picture_info = $slides_api->create_shape(%parameters);

# Print a reference to the picture frame.
print $picture_info->{selfUri}->{href};
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Using an SDK (API client) is the quickest way for a developer to speed up development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
