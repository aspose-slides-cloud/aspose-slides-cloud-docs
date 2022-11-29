---
title: "Working with View Properties"
type: docs
url: /working-with-view-properties/
weight: 60
---
## **Introduction**
Aspose.Slides Cloud API allows reading and updating view properties of the presentation. 

## **GetViewProperties**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/viewProperties|GET|Read presentation view properties.|[GetViewProperties]()|

### **Examples**
**cURL Example**

The code examples below shows how to retrieve view properties from the presentation. 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/viewProperties" -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Code: 200
Returns view properties data.

```
{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ViewProperties response = api.GetViewProperties("MyPresentation.pptx");

if (response.ShowComments == ViewProperties.ShowCommentsEnum.True)
	Console.WriteLine("Comments enabled.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ViewProperties response = api.getViewProperties("MyPresentation.pptx", null, null, null);

if (response.getShowComments() == ViewProperties.ShowCommentsEnum.TRUE)
	System.out.println("Comments enabled.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ViewProperties;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$result = $api->getViewProperties("MyPresentation.pptx");

if ($result->getShowComments() == 'True')
	print("Comments enabled.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

response = api.get_view_properties("MyPresentation.pptx")

if 	response.show_comments === 'True'
	print "Comments enabled."
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

response = api.get_view_properties("MyPresentation.pptx")
if response.show_comments == 'true':
	print("Comments enabled.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let response = await api.getViewProperties("MyPresentation.pptx");

if (response.body.showComments === CloudSdk.ViewProperties.ShowCommentsEnum.True)
	console.log("Comments enabled.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
response, _, e := api.SlidesApi.GetViewProperties(fileName, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

if response.GetShowComments() == "True" {
    fmt.Printf("Comments enabled.")
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


## **SetViewProperties**

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/viewProperties|PUT|Update presentation view properties.|[SetViewProperties]()|

### **Examples**
**cURL Example**

The code examples below shows how to set view properties of the presentation.

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
  "ShowComments": "False",
  "SlideViewProperties":{
	"Scale": 50
  }
}
```


{{< /tab >}}

{{< tab tabNum="2" >}}


```sh

Code: 200
Returns view properties data.

```
{{< /tab >}}

{{< /tabs >}}


**SDK Examples**

{{< tabs tabTotal="10" tabID="22" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ViewProperties dto = new ViewProperties()
{
	ShowComments = ViewProperties.ShowCommentsEnum.False,
	SlideViewProperties = new CommonSlideViewProperties()
	{
		Scale = 50
	}
};

ViewProperties response = api.SetViewProperties("MyPresentation.pptx", dto);

if (response.ShowComments == ViewProperties.ShowCommentsEnum.False)
	Console.WriteLine("Comments disabled.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

ViewProperties dto = new ViewProperties();
dto.showComments(ViewProperties.ShowCommentsEnum.FALSE);
CommonSlideViewProperties commonProperties = new CommonSlideViewProperties();
commonProperties.setScale(50);
dto.setSlideViewProperties(commonProperties);

ViewProperties response = api.setViewProperties("MyPresentation.pptx", dto, null, null, null);

if (response.getShowComments() == ViewProperties.ShowCommentsEnum.FALSE)
	System.out.println("Comments disabled.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ViewProperties;
use Aspose\Slides\Cloud\Sdk\Model\CommonSlideViewProperties;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$dto = new ViewProperties();
$dto->setShowComments('False');
$slideViewProperties = new CommonSlideViewProperties();
$slideViewProperties->setScale(50);
$dto->setSlideViewProperties($slideViewProperties);

$result = $api->setViewProperties("MyPresentation.pptx", $dto);

if ($result->getShowComments() == 'False')
	print("Comments disabled.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

dto = AsposeSlidesCloud::ViewProperties.new
dto.show_comments = "False"
dto.slide_view_properties = AsposeSlidesCloud::CommonSlideViewProperties.new
dto.slide_view_properties.scale = 50
      
response = api.set_view_properties("MyPresentation.pptx", dto)

if 	response.show_comments === 'False'
	print "Comments disabled."
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.view_properties import ViewProperties
from asposeslidescloud.models.common_slide_view_properties import CommonSlideViewProperties

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

dto = ViewProperties()
dto.show_comments = "False"
dto.slide_view_properties = CommonSlideViewProperties()
dto.slide_view_properties.scale = 50
        
response = api.set_view_properties("MyPresentation.pptx", dto)
if response.show_comments == 'false':
	print("Comments disabled.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const slideViewPropDto = new CloudSdk.CommonSlideViewProperties();
slideViewPropDto.scale = 50;

const dto = new CloudSdk.ViewProperties();
dto.showComments = CloudSdk.ViewProperties.ShowCommentsEnum.False;
dto.slideViewProperties = slideViewPropDto;

let response = await api.setViewProperties("MyPresentation.pptx", dto);

if (response.showComments === CloudSdk.ViewProperties.ShowCommentsEnum.False)
	console.log("Comments disabled.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
dto := asposeslidescloud.NewViewProperties()
dto.SetShowComments("False")
slideViewProperties := asposeslidescloud.NewCommonSlideViewProperties()
slideViewProperties.SetScale(50)
dto.SetSlideViewProperties(slideViewProperties)

response, _, e := api.SlidesApi.SetViewProperties(fileName, dto, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

if response.GetShowComments() == "False" {
    fmt.Printf("Comments disabled.")
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

## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)