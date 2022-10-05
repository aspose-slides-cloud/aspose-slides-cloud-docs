---
title: "Reading Animation Information from a PowerPoint Presentation"
type: docs
url: /reading-animation-information-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud allows you to read information from a Power Point Presentation. 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation|GET|Get Animation Information from a PowerPoint Slide|[GetSlideAnimation](https://apireference.aspose.cloud/slides/#/Animation/GetSlideAnimation)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=xxxx&client_secret=xxx-xx" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl -v -X GET "https://api.aspose.cloud/v3.0/slides/animation.pptx/slides/1/animation" -H "Content-Type:application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjEwNjM0NTAsImV4cCI6MTU2MTE0OTg1MCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.XURcZFFwPs__A4GHgzncfsCI5_F6R0NIWrTbdGcQqTKBV24jqbQYwe7POYMU8QT3_CKQ9zrlCX47Gtzx3XZ-1LyZAx3v6e6__r7HG9DsVCrzGXxzcIaYBwo9XohkfO5At9XcmXMqw1YoZvWskHUjhIAXzlg6Kt-k1hIPCL-0A1A0WkbdtWOJtWpTEVnIR2kBfXkUcNHLREq3S4JVshLmnjdPF6YViBM5AkV91diC33yj2Fwz-j572SjgwEuHkKNRLTngwsnu9DFEtfiN6bCCPBhulq6XG4DuqLrAtxyodD0Et5Y0YegUHUWOvf4-ZFbUd1ZHzU_rQ06dXzP6SDzMjg" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "mainSequence":[

      {

         "type":"Appear",

         "subtype":"None",

         "presetClassType":"Entrance",

         "shapeIndex":1,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      },

      {

         "type":"Bounce",

         "subtype":"None",

         "presetClassType":"Entrance",

         "shapeIndex":2,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      },

      {

         "type":"Fly",

         "subtype":"Bottom",

         "presetClassType":"Entrance",

         "shapeIndex":3,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      }

   ],

   "interactiveSequences":[

      {

         "effects":[

            {

               "type":"Fly",

               "subtype":"Bottom",

               "presetClassType":"Entrance",

               "shapeIndex":5,

               "triggerType":"OnClick",

               "triggerDelayTime":0.0

            }

         ],

         "triggerShapeIndex":1

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/animation.pptx/slides/1/animation",

      "relation":"self"

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
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
SlideAnimation response = api.GetAnimation("myPresentation.pptx", 1);
foreach (Effect effect in response.MainSequence)
{
    Console.WriteLine(effect.Type);
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
SlideAnimation response = api.getAnimation("myPresentation.pptx", 1, null, null, null, null, null);
for (Effect effect : response.getMainSequence()) {
    System.out.println(effect.getType());
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$result = $api->GetAnimation("MyPresentation.pptx", 1);
foreach ($result->getMainSequence() as $effect)
{
    print($effect->getType());
}
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

result = api.get_animation("MyPresentation.pptx", 1)
for effect in result.main_sequence:
    print(effect.type)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

api.getAnimation("MyPresentation.pptx", 1).then((result) => {
    result.body.mainSequence.forEach((effect) => { console.log(effect.type); });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)
animation, _, e := api.SlidesApi.GetAnimation("MyPresentation.pptx", 1, "masterSlide", nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
} else {
    for i, effect := range animation.getMainSequence() {
        fmt.Printf("Effect %v: %v.", i + 1, effect.getType())
    }
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
