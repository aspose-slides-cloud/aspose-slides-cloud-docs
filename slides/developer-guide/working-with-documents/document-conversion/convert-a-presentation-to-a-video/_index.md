---
title: "Convert a Presentation to a Video"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- convert a presentation
- export a presentation
- presentation to video
- PPT to video
- PPT to MPEG-4
type: docs
url: /convert-a-presentation-to-a-video/
weight: 60
---

## **Introduction**
Aspose.Slides Cloud allows you to convert a presentation into a video format. Set **Mpeg4** as a conversion format and specify additional options if needed. Using [VideoExportOptions](/slides/conversion-options/#mpeg4-options) you can set up transition effects, duration, and resolution of the output result.

You may want to check out Aspose free <a href="https://products.aspose.app/slides/video" target="_blank">PPT to Video</a> converter, a live implementation of a popular conversion process.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```sh

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```sh

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/mpeg4" -d @"options.json" -H "Content-Type: text/json" -H "Authorization: Bearer [Access Token]

```
options.json file:
```json
{
	"Format":"mpeg4",
	"SlidesTransitionDuration":5,
	"TransitionType":"Dissolve",
	"TransitionDuration":3,
	"VideoResolutionType":"SD"
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns the document.

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

VideoExportOptions videoExportOptions = new VideoExportOptions()
{
    SlidesTransitionDuration = 5,
    VideoResolutionType = VideoExportOptions.VideoResolutionTypeEnum.SD,
    TransitionType = VideoExportOptions.TransitionTypeEnum.Dissolve,
    TransitionDuration = 3
};

using Stream response = api.DownloadPresentation("MyPresentation.pptx", ExportFormat.Mpeg4, videoExportOptions);
using Stream outFile = File.Create("MyPresentation.mp4");
response.CopyTo(outFile);
```
{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

VideoExportOptions exportOptions = new VideoExportOptions();
exportOptions.setSlidesTransitionDuration(5);
exportOptions.setVideoResolutionType(VideoExportOptions.VideoResolutionTypeEnum.SD);
exportOptions.setTransitionType(VideoExportOptions.TransitionTypeEnum.DISSOLVE);
exportOptions.setTransitionDuration(3);

File response = api.downloadPresentation("MyPresentation.pptx", ExportFormat.MPEG4, exportOptions, null, null, null, null, null);
System.out.println("The converted file was saved to " + response.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;
use Aspose\Slides\Cloud\Sdk\Model\VideoExportOptions;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);


$exportOptions = new VideoExportOptions();
$exportOptions->setSlidesTransitionDuration(5);
$exportOptions->setVideoResolutionType("SD");
$exportOptions->setTransitionType("Dissolve");
$exportOptions->setTransitionDuration(3);

$result = $api->downloadPresentation("MyPresentation.pptx", ExportFormat::MPEG4, $exportOptions);
print("The converted file was saved to " . $result->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

#The example will be completed shortly.

result = api.download_presentation("MyPresentation.pptx", AsposeSlidesCloud::ExportFormat::MPEG4, export_options)
File.binwrite("MyPresentation.zip", result)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.export_format import ExportFormat
from asposeslidescloud.models.video_export_options import VideoExportOptions

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

export_options = VideoExportOptions()
export_options.slides_transition_duration = 5
export_options.video_resolution_type = 'SD'
export_options.transition_type = 'Dissolve'
export_options.transition_duration = 3

result = api.download_presentation("MyPresentation.pptx", ExportFormat.MPEG4, export_options)
print('The converted file was saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const exportOptions = new CloudSdk.VideoExportOptions();
exportOptions.slidesTransitionDuration = 5;
exportOptions.transitionType = CloudSdk.VideoExportOptions.TransitionTypeEnum.Dissolve;
exportOptions.videoResolutionType = CloudSdk.VideoExportOptions.VideoResolutionTypeEnum.SD;
exportOptions.transitionDuration = 3;

api.downloadPresentation("MyPresentation.pptx", "mpeg4", exportOptions).then(response => {
    fs.writeFile("MyPresentation.zip", response.body, (err) => {
        if (err) throw err;
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

exportOptions := asposeslidescloud.NewVideoExportOptions()
exportOptions.SlidesTransitionDuration = 5
exportOptions.VideoResolutionType = "SD"
exportOptions.TransitionType = "Dissolve"
exportOptions.TransitionDuration = 3

result, _, e := api.SlidesApi.DownloadPresentation("MyPresentation.pptx", "mpeg4", exportOptions, "", "", "", "", nil)
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The converted file was saved to  %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::VideoExportOptions;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $exportOptions = AsposeSlidesCloud::Object::VideoExportOptions->new();
my @fontRules = ( $rule1, $rule2 );
$exportOptions->{slides_transition_duration} = 5;
$exportOptions->{video_resolution_type} = "SD";
$exportOptions->{transition_type} = "Dissolve";
$exportOptions->{transition_duration} = 3;

my %params = ('name' => 'MyPresentation.pptx', 'format' => 'mpeg4', 'options' => $exportoptions);
my $result = $api->download_presentation(%params);
my $zip = "MyPresentation.zip";
open my $fh, '>', $zip;
binmode $fh;
print $fh $result;
close $fh;
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
