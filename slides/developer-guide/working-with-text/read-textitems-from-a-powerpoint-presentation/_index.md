---
title: "Read TextItems from a PowerPoint Presentation"
type: docs
url: /read-textitems-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud lets you easily read Text items from a PowerPoint Presentation. Aspose.Slides Cloud provides REST interfaces for reading items from a individual slide or from a presentation as whole.
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/textItems|GET|Read TextItems from a PowerPoint Presentation|[GetSlidesPresentationTextItems](https://apireference.aspose.cloud/slides/#/Text/GetSlidesPresentationTextItems)|
|/slides/{name}/slides/{slideIndex}/textItems|GET|Read TextItems from a slide within a PowerPoint Presentation|[GetSlidesSlideTextItems](https://apireference.aspose.cloud/slides/#/Text/GetSlidesSlideTextItems)|
### **cURL Examples**

You need to get the Authentication Token before using these resources.

**Get Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json" 

```

#### **Reading TextItems from a Presentation**
{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/destination.pptx/textItems" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzA4ODMsImV4cCI6MTU2MDExNzI4MywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.bhURwSdcASMrRj4ukvG5rWTT_O2JpzVKH436ekU1CW6ZO7wOqGnE8wtkMdq6oivVzazs8xwbeuJmluFpHLNBco7A0vU56_UXZ5cIsfNCIpTOp6e_lmeHYgOD1rnW8f6y9jWLRoerup2vzqppjbF-8KXZ2HgCOXpos4lzy7GLqWmElW9TGd2uOd3cFEu1rXmkiJzuyjEi1dFdZtvRPvNyqon5R9ZS5rxQ09GhaiRA6DW4HwFTS-jTAPQo0QGfv87b4Gg_DvnUu_JjWlAhIeqWIM72-xmvFQ_20mk-s6H7foiyvJSC65w-XN5AqUyAyE8rAZduIwcS7BuYiQuOqqen4w" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "items":[

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/shapes/1",

            "relation":"parent"

         },

         "text":"This is a slide"

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/shapes/2",

            "relation":"parent"

         },

         "text":"test"

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/2/shapes/1",

            "relation":"parent"

         },

         "text":"This is a slide"

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/2/shapes/2",

            "relation":"parent"

         },

         "text":"test"

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/textItems",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
#### **Reading TextItems from a Slide**
{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/textItems" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzA4ODMsImV4cCI6MTU2MDExNzI4MywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.bhURwSdcASMrRj4ukvG5rWTT_O2JpzVKH436ekU1CW6ZO7wOqGnE8wtkMdq6oivVzazs8xwbeuJmluFpHLNBco7A0vU56_UXZ5cIsfNCIpTOp6e_lmeHYgOD1rnW8f6y9jWLRoerup2vzqppjbF-8KXZ2HgCOXpos4lzy7GLqWmElW9TGd2uOd3cFEu1rXmkiJzuyjEi1dFdZtvRPvNyqon5R9ZS5rxQ09GhaiRA6DW4HwFTS-jTAPQo0QGfv87b4Gg_DvnUu_JjWlAhIeqWIM72-xmvFQ_20mk-s6H7foiyvJSC65w-XN5AqUyAyE8rAZduIwcS7BuYiQuOqqen4w" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

 {

   "items":[

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/shapes/1",

            "relation":"parent"

         },

         "text":"This is a slide"

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/shapes/2",

            "relation":"parent"

         },

         "text":"test"

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/textItems",

      "relation":"self"

   }

}

```





{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="Perl" tabName9="C++" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
TextItems presentationItems = api.GetPresentationTextItems("destination.pptx");
TextItems firstSlideItems = api.GetSlideTextItems("destination.pptx", 1);
Console.WriteLine(presentationItems.Items.Count);
Console.WriteLine(firstSlideItems.Items.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
TextItems presentationItems = api.getPresentationTextItems("destination.pptx", null, null, null);
TextItems firstSlideItems = api.getSlideTextItems("destination.pptx", 1, null, null, null);
System.out.println(presentationItems.getItems().size());
System.out.println(firstSlideItems.getItems().size());
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
$presentationItems = $api->GetPresentationTextItems("destination.pptx");
$firstSlideItems = $api->GetSlideTextItems("destination.pptx", 1);
print(count($presentationItems->getItems()));
print(count($firstSlideItems->getItems()));
```

{{< /tab >}}

{{< tab tabNum="4" >}}

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

result = api.get_presentation_text_items("destination.pptx")
print(len(result.items))
slide_result = api.get_slide_text_items("destination.pptx", 1)
print(len(slide_result.items))
```

{{< /tab >}}

{{< tab tabNum="6" >}}


```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

api.getPresentationTextItems("destination.pptx").then((result) => {
    console.log(result.body.items.length);
});

api.getSlideTextItems("destination.pptx", 1).then((result) => {
    console.log(result.body.items.length);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

presentationItems, _, e := c.SlidesApi.GetPresentationTextItems("destination.pptx", nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Found %v items.", len(presentationItems.getItems()))

slideItems, _, e := c.SlidesApi.GetSlideTextItems("destination.pptx", 1, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Found %v items.", len(slideItems.getItems()))
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
