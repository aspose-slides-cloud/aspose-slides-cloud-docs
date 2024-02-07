---
title: "Working with a Slide Background"
type: docs
url: /working-with-a-slide-background/
weight: 70
---

## **Introduction**

Aspose.Slides Cloud API makes it easy to read, update, and delete the background of any slide in a PowerPoint presentation. The presentation must already be saved to a Cloud storage. You can set different background types, such as solid color, gradient, pattern, and image. Many effects can also be applied to the slide background (blur, glow, shadows, reflections, etc.).

## **GetBackground**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/background|GET|Reads information about the background applied to a presentation slide.|[GetBackground](https://apireference.aspose.cloud/slides/#/Slides/GetBackground)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide to read the background.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Get the **background type** of the **first** slide from **MyFolder/MyPresentation.pptx** file saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get the Slide Background**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/background?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "type": "Solid",
    "fillFormat": {
        "type": "Solid",
        "color": "#FFFFC000"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/background?folder=MyFolder",
        "relation": "self",
        "slideIndex": 1
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get the background of the first slide.
        var slideBackground = slidesApi.GetBackground("MyPresentation.pptx", 1, null, "MyFolder");

        Console.WriteLine(slideBackground.Type); // Solid, for example
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get the background of the first slide.
        SlideBackground slideBackground = slidesApi.getBackground("MyPresentation.pptx", 1, null, "MyFolder", null);

        System.out.println(slideBackground.getType()); // Solid, for example
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Get the background of the first slide.
$slideBackground = $slidesApi->getBackground("MyPresentation.pptx", 1, null, "MyFolder");

echo $slideBackground->getType(); // Solid, for example
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

# Get the background of the first slide.
slide_background = slides_api.get_background("MyPresentation.pptx", 1, nil, "MyFolder")

print slide_background.type # Solid, for example
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Get the background of the first slide.
slide_background = slides_api.get_background("MyPresentation.pptx", 1, None, "MyFolder")

print(slide_background.type) # Solid, for example
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Get the background of the first slide.
slidesApi.getBackground("MyPresentation.pptx", 1, null, "MyFolder").then((response) => {
    console.log(response.body.type) // Solid, for example
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Get the background of the first slide.
        slideBackground slideBackground = slidesApi.getBackground("MyPresentation.pptx", 1, null, "MyFolder", null);

        System.out.println(slideBackground.getType()); // Solid, for example
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Get the background of the first slide.
    auto slideBackground = slidesApi->getBackground(L"MyPresentation.pptx", 1, L"", L"MyFolder").get();

    std::wcout << slideBackground->getType(); // Solid, for example

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Get the background of the first slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 1, folder => "MyFolder");
my $slide_background = $slides_api->get_background(%parameters);

print $slide_background->{type}; # Solid, for example
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SetBackground**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/background|PUT|Sets a background for a presentation slide.|[SetBackground](https://apireference.aspose.cloud/slides/#/Slides/SetBackground)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide to set a background.|
|background|object|body|true|The background DTO. For more information, please see the [API Reference](https://apireference.aspose.cloud/slides/) and look for the `SlideBackground` object.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

**Background Properties**

|**Name**|**Type**|**Description**| 
| :- | :- | :- |
|Type|`TypeEnum`|The background fill type.|
|FillFormat| [FillFormat](/slides/fill-format-type/)|The background fill format.|
|EffectFormat| [EffectFormat](/slides/effect-format-type/)|The background effect format.|

**Background Types (`TypeEnum`)**

|**Name**|**Description**|
| :- | :- |
|Gradient|Specifies a gradient fill.|
|NoFill|No fill is applied.|
|NotDefined|No fill is specified. The background is applied from a slide layout.|
|Pattern|Specifies a pattern fill.|
|Picture|Specifies a picture fill.|
|Solid|Specifies the fill to a solid color.|

### **Examples**

Set **MyImage.png** as the background for the **second** slide in **MyFolder/MyPresentation.pptx** document saved to the default storage. Use the **Tile** fill mode.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the Slide Background**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/background?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @request_data.json
```

request_data.json content:

```json
{
    "FillFormat": {
        "Type": "Picture",
        "Base64Data": "iVBORw0KGgoAAAANSUhEUgAAADcAAAAbCAYAAADYtRcLAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAACxEAAAsRAX9kX5EAAAJmSURBVFhH7ZcxTNtAFIZ/mqBYZbDVDmxphtABlZY5HTqnVRFTN1ZnbJduHbuxhBGPdGOqUhVmWjUzhIoBMpBMMKSypSAcOdH17nxnzonjeGmFI3+SlXv3fC/3/P57lhewd0UwpzwQv3NJllxamThzZGtZjNJPJsu0kiWXVpIn13Ww8OUPdhxhp4CEyQ2xc+LCLOXwoeWKuftPsuScAfZtDZvP86hcDnAopu87iZJrdwdolgqo6kv4VHLx+XQoPAIu2WtxqdKlFf9G7VPF/1OpvHODl5HrKFNjMlzUAp8T87DZS1y5Jrkl5l6P1G1hdmyCRp9cCDPe75F6g8W1yQG32b1XpNLygrHZ4Q5/Xei++Jhy3UWrN7afO2ZXjlbNMgp4owu7WIBp97HdFTbHw5l8skUd5O0SysJkmK90VPlIw8f1RTRtWnlnhN/U3ixyhx8XI5wHFZoSUx4Rsa689pDuZ4Dvocr6zEjObySgyawoMrCox+pIeWnY3aKZH0n/NWqhxMOU9RyNN0LbGaJp5LEi5oE8Vg2Z0KyYLl6LebmfaBRJTsjS7pNKIBUFPq/IRiUkr7CEGFxGP24jYo9JUUWNOW1PEcRW7rDV9xuJsAN4Y/Gw32XyYk0h/v1nndygzUcuto89mE80GiOHZ9T+KivC5I8cnjL5x8XUC3hnKOv4vdFNJfaroEb/YHXjEd7L86bCutkRcEDlU+VjKdNF1IM1rFv2cGZosC59f2X9MX6t5fmYb6xBHyA31HWUqTEZrFtKOY777vjHnzwiuRfL2JWN4z+S7CWeUuY6uexLPK1kyaWVOU4O+As5FnkrBDOStwAAAABJRU5ErkJggg==",
        "PictureFillMode": "Tile"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "type": "Picture",
    "fillFormat": {
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
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/background?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

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

        // Prepare the background DTO.
        var imageData = File.ReadAllBytes("MyImage.png");
        var imageBase64String = Convert.ToBase64String(imageData);
        var newBackground = new SlideBackground 
        { 
            FillFormat = new PictureFill
            { 
                Base64Data = imageBase64String,
                PictureFillMode = PictureFill.PictureFillModeEnum.Tile
            }
        };

        // Set the new background for the second slide.
        var currentBackground = slidesApi.SetBackground("MyPresentation.pptx", 2, newBackground, null, "MyFolder");

        // Check the type of the current background.
        Debug.WriteLine(currentBackground.Type); // Picture
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

        byte[] imageData = Files.readAllBytes(Paths.get("MyImage.png"));
        String imageBase64String = new String(Base64.getEncoder().encode(imageData));

        // Prepare the background fill format.
        PictureFill pictureFill = new PictureFill();
        pictureFill.setBase64Data(imageBase64String);
        pictureFill.setPictureFillMode(PictureFill.PictureFillModeEnum.TILE);

        // Prepare the background DTO.
        SlideBackground newBackground = new SlideBackground();
        newBackground.setFillFormat(pictureFill);

        // Set the new background for the second slide.
        SlideBackground currentBackground = slidesApi.setBackground("MyPresentation.pptx", 2, newBackground, null, "MyFolder", null);

        // Check the type of the current background.
        System.out.println(currentBackground.getType()); // Picture
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\PictureFill;
use Aspose\Slides\Cloud\Sdk\Model\SlideBackground;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$imageData = file_get_contents("MyImage.png");
$imageBase64String = base64_encode($imageData);

// Prepare the background fill format.
$pictureFill = new PictureFill();
$pictureFill->setBase64Data($imageBase64String);
$pictureFill->setPictureFillMode("Tile");

// Prepare the background DTO.
$newBackground = new SlideBackground();
$newBackground->setFillFormat($pictureFill);

// Set the new background for the second slide.
$currentBackground = $slidesApi->setBackground("MyPresentation.pptx", 2, $newBackground, null, "MyFolder");

// Check the type of the current background.
echo $currentBackground->getType(); // Picture
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

image_data = File.binread("MyImage.png")
image_base64_string = Base64.encode64(image_data)

# Prepare the background fill format.
picture_fill = PictureFill.new
picture_fill.base64_data = image_base64_string
picture_fill.picture_fill_mode = "Tile"

# Prepare the background DTO.
new_background = SlideBackground.new
new_background.fill_format = picture_fill

# Set the new background for the second slide.
current_background = slides_api.set_background("MyPresentation.pptx", 2, new_background, nil, "MyFolder")

# Check the type of the current background.
print current_background.type # Picture
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud
import base64

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.picture_fill import PictureFill
from asposeslidescloud.models.slide_background import SlideBackground

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

with open("MyImage.png", "rb") as image_stream:
    image_base64_string = str(base64.b64encode(image_stream.read()), "utf-8")

# Prepare the background fill format.
picture_fill = PictureFill()
picture_fill.base64_data = image_base64_string
picture_fill.picture_fill_mode = "Tile"

# Prepare the background DTO.
new_background = SlideBackground()
new_background.fill_format = picture_fill

# Set the new background for the second slide.
current_background = slides_api.set_background("MyPresentation.pptx", 2, new_background, None, "MyFolder")

# Check the type of the current background.
print(current_background.type) # Picture
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

const imageBase64String = fs.readFileSync("MyImage.png", { encoding: "base64" })

// Prepare the background fill format.
const pictureFill = new cloud.PictureFill()
pictureFill.base64Data = imageBase64String
pictureFill.pictureFillMode = "Tile"

// Prepare the background DTO.
const newBackground = new cloud.SlideBackground()
newBackground.fillFormat = pictureFill

// Set the new background for the second slide.
slidesApi.setBackground("MyPresentation.pptx", 2, newBackground, null, "MyFolder").then((currentBackground) => {
    // Check the type of the current background.
    console.log(currentBackground.body.type) // Picture
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

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

        byte[] imageData = Files.readAllBytes(Paths.get("MyImage.png"));
        String imageBase64String = new String(Base64.getEncoder().encode(imageData));

        // Prepare the background fill format.
        PictureFill pictureFill = new PictureFill();
        pictureFill.setBase64Data(imageBase64String);
        pictureFill.setPictureFillMode(PictureFill.PictureFillModeEnum.TILE);

        // Prepare the background DTO.
        SlideBackground newBackground = new SlideBackground();
        newBackground.setFillFormat(pictureFill);

        // Set the new background for the second slide.
        SlideBackground currentBackground = slidesApi.setBackground("MyPresentation.pptx", 2, newBackground, null, "MyFolder", null);

        // Check the type of the current background.
        System.out.println(currentBackground.getType()); // Picture
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::PictureFill;
use AsposeSlidesCloud::Object::SlideBackground;

use File::Slurp;
use MIME::Base64;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $image_data = read_file("MyImage.png", { binmode => ":raw" });
my $image_base64_string = encode_base64($image_data);

# Prepare the background fill format.
my $picture_fill = AsposeSlidesCloud::Object::PictureFill->new();
$picture_fill->{base64_data} = $image_base64_string;
$picture_fill->{picture_fill_mode} = "Tile";

# Prepare the background DTO.
my $new_background = AsposeSlidesCloud::Object::SlideBackground->new();
$new_background->{fill_format} = $picture_fill;

# Set the new background for the second slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, background => $new_background, folder => "MyFolder");
my $current_background = $slides_api->set_background(%parameters);

# Check the type of the current background.s
print $current_background->{type}; # Picture
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **DeleteBackground**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/background|DELETE|Deletes the background applied to a presentation slide.|[DeleteBackground](https://apireference.aspose.cloud/slides/#/Slides/DeleteBackground)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide to delete a background.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Delete a background applied to the **second** slide in **MyFolder/MyPresentation.pptx** document saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Background**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/background?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "type": "NoFill",
    "fillFormat": {
        "type": "NoFill"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/background?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="33" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System.Diagnostics;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Delete a background from the second slide.
        var currentBackground = slidesApi.DeleteBackground("MyPresentation.pptx", 2, null, "MyFolder");

        // Check the type of the current background.
        Debug.WriteLine(currentBackground.Type); // NoFill
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Delete a background from the second slide.
        SlideBackground currentBackground = slidesApi.deleteBackground("MyPresentation.pptx", 2, null, "MyFolder", null);

        // Check the type of the current background.
        System.out.println(currentBackground.getType()); // NoFill
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Delete a background from the second slide.
$currentBackground = $slidesApi->deleteBackground("MyPresentation.pptx", 2, null, "MyFolder");

// Check the type of the current background.
echo $currentBackground->getType(); // NoFill
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

# Delete a background from the second slide.
current_background = slides_api.delete_background("MyPresentation.pptx", 2, nil, "MyFolder")

# Check the type of the current background.
print current_background.type # NoFill
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Delete a background from the second slide.
current_background = slides_api.delete_background("MyPresentation.pptx", 2, None, "MyFolder")

# Check the type of the current background.
print(f"{current_background.type}") # NoFill
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Delete a background from the second slide.
slidesApi.deleteBackground("MyPresentation.pptx", 2, null, "MyFolder").then((currentBackground) => {
    // Check the type of the current background.
    console.log(currentBackground.body.type)
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Delete a background from the second slide.
        SlideBackground currentBackground = slidesApi.deleteBackground("MyPresentation.pptx", 2, null, "MyFolder", null);

        // Check the type of the current background.
        System.out.println(currentBackground.getType()); // NoFill
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = new SlidesApi(L"MyClientId", L"MyClientSecret");

    // Delete a background from the second slide.
    auto currentBackground = slidesApi->deleteBackground(L"MyPresentation.pptx", 2, L"", L"MyFolder").get();

    // Check the type of the current background.
    std::wcout << currentBackground->getType(); // NoFill

    std::cin.get();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Delete a background from the second slide.
%parameters = (name => "MyPresentation.pptx", slide_index => 2, folder => "MyFolder");
my $current_background = $slides_api->delete_background(%parameters);

# Check the type of the current background.
print current_background->{type}; # NoFill
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< tab tabNum="11" >}}

{{< /tab >}}

{{< /tabs >}}

## **SetBackgroundColor**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/backgroundColor|PUT|Sets a background color for a presentation slide.|[SetBackgroundColor](https://reference.aspose.cloud/slides/#/Slides/SetBackgroundColor)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|color|string|query|true|The slide background color in #RRGGBB or #AARRGGBB format.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Set the background color to **#AABBDD** for the **first** slide in the document **MyPresentation.pptx** saved in the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="4" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the Background Color**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/backgroundColor?color=%23AABBDD" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Length: 0"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "type": "Solid",
  "fillFormat": {
    "type": "Solid",
    "color": "#FFAABBDD"
  },
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/background",
    "relation": "self",
    "slideIndex": 1
  }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="44" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using Aspose.Slides.Cloud.Sdk;
using System;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var documentName = "MyPresentation.pptx";
        var slideIndex = 1;
        var backgroundColor = "#AABBDD";

        var slideBackground = slidesApi.SetBackgroundColor(documentName, slideIndex, backgroundColor);

        Console.WriteLine("Background type: " + slideBackground.FillFormat.Type); // Solid
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SlideBackground;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String documentName = "MyPresentation.pptx";
        int slideIndex = 1;
        String backgroundColor = "#AABBDD";

        SlideBackground slideBackground = slidesApi.setBackgroundColor(documentName, slideIndex, backgroundColor, null, null, null);

        System.out.println("Background type: " + slideBackground.getFillFormat().getType()); // Solid
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$documentName = "MyPresentation.pptx";
$slideIndex = 1;
$backgroundColor = "#AABBDD";

$slideBackground = $slidesApi->setBackgroundColor($documentName, $slideIndex, $backgroundColor);

echo "Background type: ", $slideBackground->getFillFormat()->getType(); // Solid
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

document_name = "MyPresentation.pptx"
slide_index = 1
background_color = "#AABBDD"

slide_background = slides_api.set_background_color(document_name, slide_index, background_color)

print "Background type: ", slide_background.fill_format.type # Solid
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

document_name = "MyPresentation.pptx"
slide_index = 1
background_color = "#AABBDD"

slide_background = slides_api.set_background_color(document_name, slide_index, background_color)

print("Background type:", slide_background.fill_format.type)  # Solid
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const documentName = "MyPresentation.pptx";
const slideIndex = 1;
const backgroundColor = "#AABBDD";

slidesApi.setBackgroundColor(documentName, slideIndex, backgroundColor).then(slideBackground => {
    console.log("Background type:", slideBackground.body.fillFormat.type); // Solid
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto documentName = L"MyPresentation.pptx";
    auto slideIndex = 1;
    auto backgroundColor = L"#AABBDD";

    auto slideBackground = slidesApi->setBackgroundColor(documentName, slideIndex, backgroundColor).get(); 

    std::wcout << "Background type: " << slideBackground->getFillFormat()->getType(); // Solid
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %parameters = (name => "MyPresentation.pptx", slide_index => 1, color => "#AABBDD");

my $slide_background = $slides_api->set_background_color(%parameters);

print("Background type: " . $slide_background->{type}); # Solid
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
