---
title: "Working with Slide Show Properties"
keywords: "PowerPoint, presentation, REST API, Cloud API, slide, slide show, slide show properties"
type: docs
url: /working-with-slide-show-properties/
weight: 70
---
## **Introduction**
Aspose.Slides Cloud API allows reading and updating slide show properties of a presentation. 

## **GetSlideShowProperties**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slideShowProperties|GET|Read presentation slide show properties.|[GetSlideShowProperties]()|

### **Examples**
**cURL Example**

The code examples below shows how to retrieve slide show properties from the presentation. 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slideShowProperties" -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Code: 200
Returns slide show properties data.

```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

SlideShowProperties response = api.GetSlideShowProperties("MyPresentation.pptx");

if (response.ShowAnimation == true)
	Console.WriteLine("Animation enabled.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

SlideShowProperties response = api.getSlideShowProperties("MyPresentation.pptx", null, null, null);

if (response.isShowAnimation())
	System.out.println("Animation enabled.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideShowProperties;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$result = $api->getSlideShowProperties("MyPresentation.pptx");

if ($result->getShowAnimation())
	print("Animation enabled.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

response = api.get_slide_show_properties("MyPresentation.pptx")

if response.show_animation
	print "Animation enabled."
end
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

response = api.get_slide_show_properties("MyPresentation.pptx")
if response.show_animation:
	print("Animation enabled.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let response = await api.getSlideShowProperties("MyPresentation.pptx");

if (response.body.showAnimation)
	console.log("Animation enabled.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
response, _, e := api.SlidesApi.GetSlideShowProperties(fileName, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

if response.GetShowAnimation() {
    fmt.Printf("Animation enabled.")
}
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

#Code example will be added soon.
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}


## **SetSlideShowProperties**

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slideShowProperties|PUT|Update presentation slide show properties.|[SetSlideShowProperties]()|

### **Examples**
**cURL Example**

The code examples below shows how to set slide show properties of the presentation.

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slideShowProperties" \
-H "Authorization: Bearer [Access Token]" \
-H "Content-Type: application/json" \
-d @request_data.json
```

request_data.json content:

```json
{
  "Loop": false,
  "useTimings": false,
  "slideShowType": "PresentedBySpeaker"
}
```


{{< /tab >}}

{{< tab tabNum="2" >}}


```sh

Code: 200
Returns slide show properties data.

```
{{< /tab >}}

{{< /tabs >}}


**SDK Examples**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

SlideShowProperties properties = new SlideShowProperties()
{
	Loop = true,
	UseTimings = true,
	SlideShowType = SlideShowProperties.SlideShowTypeEnum.PresentedBySpeaker
};

SlideShowProperties response = api.SetSlideShowProperties("MyPresentation.pptx", properties);

Console.WriteLine("Slide show properties were successfully set.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

SlideShowProperties dto = new SlideShowProperties();
dto.setLoop(true);
dto.setUseTimings(true);
dto.slideShowType(SlideShowProperties.SlideShowTypeEnum.PRESENTEDBYSPEAKER);

SlideShowProperties response = api.setSlideShowProperties("MyPresentation.pptx", dto, null, null, null);

System.out.println("Slide show properties were successfully set.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideShowProperties;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new SlideShowProperties();
$dto->setLoop(true);
$dto->setUseTimings(true);
$dto->setSlideShowType('PresentedBySpeaker');

$result = $api->setSlideShowProperties("MyPresentation.pptx", $dto);

print("Slide show properties were successfully set.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

dto = AsposeSlidesCloud::SlideShowProperties.new
dto.loop = true
dto.slide_show_type = "PresentedBySpeaker"
      
response = api.set_slide_show_properties("MyPresentation.pptx", dto)

print "Slide show properties were successfully set."
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.slide_show_properties import SlideShowProperties

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = SlideShowProperties()
dto.loop = True
dto.use_timings = True
dto.slide_show_type = "PresentedBySpeaker"
        
response = api.set_slide_show_properties("MyPresentation.pptx", dto)

print("Slide show properties were successfully set.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const dto = new CloudSdk.SlideShowProperties();
dto.loop = true;
dto.useTimings = true;
dto.slideShowType = CloudSdk.SlideShowProperties.SlideShowTypeEnum.PresentedBySpeaker;
            
let result = await api.setSlideShowProperties("MyPresentation.pptx", dto);

console.log("Slide show properties were successfully set.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
dto := asposeslidescloud.NewSlideShowProperties()
dto.SetLoop(true)
dto.SetUseTimings(true)
dto.SetSlideShowType("PresentedBySpeaker")


_, _, e := api.SlidesApi.SetSlideShowProperties(fileName, dto, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("Slide show properties were successfully set.")

```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

#Code example will be added soon.
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)