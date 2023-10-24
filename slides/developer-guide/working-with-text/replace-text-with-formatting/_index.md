---
title: "Replace Text With Formatting"
type: docs
url: /replace-text-with-formatting/
weight: 100
---

## **Introduction**

Using Aspose.Slides Cloud, you can replace all occurrences of text and apply formatting for it. Aspose.Slides Cloud provides you with the following methods for replacing text with formatting.

## **ReplaceTextFormatting**

This method replaces text in a presentation on storage.

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/replaceTextFormatting|POST|Replaces text in a presentation with formatting.|[ReplaceTextFormatting](https://apireference.aspose.cloud/slides/#/Text/ReplaceTextFormatting)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|oldValue|string|query|true|The text string to be replaced.|
|newValue|string|query|true|The text string to replace with.|
|portionFormat|[PortionFormat](https://reference.aspose.cloud/slides/#model-PortionFormat)|body|false|The format of the text. Defaults to the format of the first character of the first occurrence.|
|withMasters|boolean|query|false|Indicates whether the replacement includes master slides. False by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Replace every word **banana** with the word **orange** in the document **MyFolder/MyPresentation.pptx** &amp; format it to orange color.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Replace the Text**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/replaceTextFormatting?oldValue=banana&newValue=orange&folder=MyFolder" \
     -d "@portionFormat.json" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Length: 0"
```

portionFormat.json
```json
{
    "color": "#FFFFA500"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "documentProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties?folder=MyFolder",
        "relation": "self"
    },
    "viewProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/viewProperties?folder=MyFolder",
        "relation": "self"
    },
    "slides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides?folder=MyFolder",
        "relation": "self"
    },
    "images": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images?folder=MyFolder",
        "relation": "self"
    },
    "layoutSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides?folder=MyFolder",
        "relation": "self"
    },
    "masterSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides?folder=MyFolder",
        "relation": "self"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder",
        "relation": "self"
    },
    "alternateLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/odp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Odp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fodp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Fodp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppt?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Ppt"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pdf?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/pdf",
            "title": "Download as Pdf"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/tiff?folder=MyFolder",
            "relation": "alternate",
            "linkType": "image/tiff",
            "title": "Download as Tiff"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/xps?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-xpsdocument",
            "title": "Download as Xps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pps?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppsx?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "title": "Download as Ppsx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pptm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "title": "Download as Pptm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppsm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "title": "Download as Ppsm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pot?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pot"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/potx?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
            "title": "Download as Potx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/potm?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
            "title": "Download as Potm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/otp?folder=MyFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation-template",
            "title": "Download as Otp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/html?folder=MyFolder",
            "relation": "alternate",
            "linkType": "text/html",
            "title": "Download as Html"
        }
    ]
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using System;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Replace the "banana" for "orange", in orange color.
        PortionFormat portionFormat = new PortionFormat { FontColor = "#FFFFA500" };
        slidesApi.ReplaceTextFormatting("MyPresentation.pptx", "banana", "orange", portionFormat, null, null, "MyFolder");
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

        // Replace the "banana" for "orange", in orange color.
        PortionFormat portionFormat = new PortionFormat();
        portionFormat.setFontColor("#FFFFA500");
        slidesApi.replaceTextFormatting("MyPresentation.pptx", "banana", "orange", portionFormat, false, null, "MyFolder", null);
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\PortionFormat;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$api = new SlidesApi(null, $configuration);

// Replace the "banana" for "orange", in orange color.
$portionFormat = new PortionFormat();
$portionFormat->setFontColor("#FFFFA500");

$api->replaceTextFormatting("MyPresentation.pptx", "banana", "orange", $portionFormat, false, null, "MyFolder");
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

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Replace the "banana" for "orange", in orange color.
portion_format = AsposeSlidesCloud::PortionFormat.new
portion_format.font_color = "#FFFFA500"

slides_api.replace_text_formatting("MyPresentation.pptx", "banana", "orange", portion_format, nil, nil, "MyFolder")
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud import PortionFormat
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Replace the "banana" for "orange", in orange color.
portion_format = PortionFormat()
portion_format.font_color = "#FFFFA500"

slides_api.replace_text_formatting("MyPresentation.pptx", "banana", "orange", portion_format, None, None, "MyFolder")
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

// Replace the "banana" for "orange", in orange color.
const portionFormat = new cloud.PortionFormat();
portionFormat.fontColor = "#FFFFA500";
slidesApi.replaceTextFormatting("MyPresentation.pptx", "banana", "orange", portionFormat, null, null, "MyFolder").then(() => {
    console.log("Replaced successfully.");
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Replace the "banana" for "orange", in orange color.
	std::shared_ptr<PortionFormat> portionFormat(new PortionFormat());
	portionFormat->setFontColor(L"#FFFFA500");

    slidesApi->replaceTextFormatting(L"MyPresentation.pptx", L"banana", L"orange", portionFormat, false, L"", L"MyFolder", L"");

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::PortionFormat;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Replace the "banana" for "orange", in orange color.
my $portion_format = AsposeSlidesCloud::Object::PortionFormat->new();
$portion_format->{font_color} = "#FFFFA500";

my %parameters = (name => "MyPresentation.pptx", old_value => "banana", new_value => "orange", portion_format => $portion_format, folder => "MyFolder");
$slides_api->replace_text_formatting(%parameters);
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-go

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

// Replace the "banana" for "orange", in orange color.
portionFormat := asposeslidescloud.NewPortionFormat()
portionFormat.FontColor = "#FFFFA500"

_, _, e := api.SlidesApi.ReplaceTextFormatting("MyPresentation.pptx", "banana", "orange", portionFormat, nil, "MyFolder", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
```

{{< /tab >}}

{{< /tabs >}}

## **ReplaceTextFormattingOnline**

This method replaces text in a presentation provided in request body, and returns the updated presentation in response.

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/replaceTextFormattingOnline|POST|Replaces text in a presentation with formatting.|[ReplaceTextFormattingOnline](https://apireference.aspose.cloud/slides/#/Text/ReplaceTextFormattingOnline)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|document|binary|body|true|The presentation file.|
|oldValue|string|query|true|The text string to be replaced.|
|newValue|string|query|true|The text string to replace with.|
|portionFormat|[PortionFormat](https://reference.aspose.cloud/slides/#model-PortionFormat)|body|false|The format of the text. Defaults to the format of the first character of the first occurrence.|
|withMasters|boolean|query|false|Indicates whether the replacement includes master slides. False by default.|
|password|string|header|false|The password to open the presentation.|

### **Examples**

Replace every word **banana** with the word **orange** on the **second** slide in the uploaded document.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Replace the Text**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/replaceTextFormatting?oldValue=banana&newValue=orange&ignoreCase=false&folder=MyFolder" \
     -F "file=@MyPresentation.pptx"
     -F "data=@portionFormat.json;filename="
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Length: 0"
```

portionFormat.json
```json
{
    "color": "#FFFFA500"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

The updated presentation.

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// Replace the "banana" for "orange", in orange color.
PortionFormat portionFormat = new PortionFormat { FontColor = "#FFFFA500" };
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
using Stream file = File.OpenRead("MyPresentation.pptx");
using Stream result = api.ReplaceTextFormattingOnline(file, "banana", "orange", portionFormat);
using Stream outFile = File.OpenWrite("UpdatedPresentation.pptx");
result.CopyTo(outFile);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// Replace the "banana" for "orange", in orange color.
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontColor("#FFFFA500");
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
File response = api.replaceTextFormattingOnline(file, "banana", "orange", portionFormat, true, null);
System.out.println("The updated file was saved to " + response.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\PortionFormat;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$file = fopen("MyPresentation.pptx", 'r');
$portionFormat = new PortionFormat();
$portionFormat->setFontColor("#FFFFA500");

// Replace the "banana" for "orange", in orange color.
$result = $api->ReplaceTextFormattingOnline($file, "banana", "orange", $portionFormat);
print("The updated file was saved to " . $result->getPathname());
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

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Replace the "banana" for "orange", in orange color.
source = File.binread("MyPresentation.pptx")
portion_format = AsposeSlidesCloud::PortionFormat.new
portion_format.font_color = "#FFFFA500"
result = slides_api.replace_text_formatting_online(source, "banana", "orange", portion_format)
File.binwrite("UpdatedPresentation.pptx", result)

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud import PortionFormat
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Replace the "banana" for "orange", in orange color.
portion_format = PortionFormat()
portion_format.font_color = "#FFFFA500"

with open("MyPresentation.pptx", 'rb') as f:
    input_file = f.read()

result = slides_api.replace_text_formatting_online(input_file, "banana", "orange", portion_format)
print('The updated file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require('fs');

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret")

const portionFormat = new cloud.PortionFormat();
portionFormat.fontColor = "#FFFFA500";
slidesApi.replaceTextFormattingOnline(fs.createReadStream("MyPresentation.pptx"), "banana", "orange", portionFormat).then((response) => {
    fs.writeFile("UpdatedPresentation.pptx", response.body, (err) => {
        if (err) throw err;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Replace the "banana" for "orange", in orange color.
	std::shared_ptr<PortionFormat> portionFormat(new PortionFormat());
	portionFormat->setFontColor(L"#FFFFA500");

	std::shared_ptr<HttpContent> data = std::make_shared<HttpContent>();
	data->setData(std::make_shared<std::ifstream>(L"MyPresentation.pptx", std::ios::binary));

    std::ofstream fs("UpdatedPresentation.pptx", std::ios::binary);
    slidesApi->replaceTextFormattingOnline(data, L"banana", L"orange", portionFormat, false, L"").get().writeTo(fs);

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::PortionFormat;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Replace the "banana" for "orange", in orange color.
my $portion_format = AsposeSlidesCloud::Object::PortionFormat->new();
$portion_format->{font_color} = "#FFFFA500";

my $source = read_file("MyPresentation.pptx", { binmode => ':raw' });
my %parameters = (document => $source, old_value => "banana", new_value => "orange", portion_format => $portion_format);
my $result = $slides_api->replace_text_formatting_online(%parameters);
my $out_path = "UpdatedPresentation.pptx";
open my $fh, '>>', $out_path;
binmode $fh;
print $fh $result;
close $fh;
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-go

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

// Replace the "banana" for "orange", in orange color.
portionFormat := asposeslidescloud.NewPortionFormat()
portionFormat.FontColor = "#FFFFA500"

source, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
response, _, e := api.SlidesApi.ReplaceTextFormattingOnline(source, "banana", "orange", portionFormat, nil, "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The updated file file was saved to  %v.", response.Name())
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
